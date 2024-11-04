# Terraform

O Terraform é uma ferramenta de *Infrastructure as Code* (IaC) que permite definir, provisionar e gerenciar infraestrutura de TI de forma automatizada e reproduzível. Ele usa arquivos de configuração (em HCL, uma linguagem específica do Terraform) para descrever a infraestrutura desejada, e com esses arquivos, cria e gerencia recursos em provedores de nuvem (como AWS, Azure, Google Cloud) ou em ambientes on-premises.

**Documentação Terraform:**

[Overview - Configuration Language | Terraform | HashiCorp Developer](https://developer.hashicorp.com/terraform/language)

**Documentação Providers:**

[Terraform Registry](https://registry.terraform.io/browse/providers)

**Documentação Registry:** 

[Terraform Registry](https://registry.terraform.io/browse/modules)

- **Tipos de blocos no terraform:**
    - **Terraform →** Esse parâmetro é como uma "configuração geral" do Terraform. Nele, você coloca informações que ajudam o Terraform a funcionar, como qual versão ele deve usar e onde estão os módulos (receitas) que você quer usar. É como dar as instruções básicas para o Terraform se preparar antes de começar a criar tudo.
    - **Providers →** Imagina que você quer construir uma casa, mas precisa escolher a construtora. O `provider` é como a construtora que você escolhe – pode ser a AWS, Google Cloud, Azure, etc. Ele diz ao Terraform onde ele vai criar os recursos.
    - **Resources →** É como o "material de construção" que você vai usar. Pode ser uma máquina virtual, um banco de dados ou uma rede. Com o `resource`, você diz ao Terraform o que você quer criar e onde.
    - **Data →** O `data` é usado para "consultar informações" que já existem, em vez de criar algo novo. Imagina que você precisa saber o nome de um servidor ou o endereço de uma rede que já foram criados antes. Com o `data`, você pode "buscar" essas informações para usar no seu código, sem precisar recriar nada.
    - **Module** → Imagine que você tem uma "receita" pronta para construir várias coisas ao mesmo tempo, como criar uma rede com servidores, banco de dados, etc. O `module` guarda essas "receitas" prontas para que você possa usar várias vezes, sem precisar escrever tudo de novo.
    - **Variable →** Pense numa variável como uma "caixinha" onde você guarda um valor que pode mudar depois. Por exemplo, você pode usar uma `variable` para o nome do servidor, e aí é só trocar esse valor na caixinha quando precisar mudar o nome.
    - **Output →** Depois que você constrói tudo, o `output` mostra as informações que você precisa saber. É como uma "plaquinha de informações" sobre o que foi criado, como o IP de um servidor ou o nome de uma rede.
    - **Locals →** O `locals` é como uma “área de anotações” onde você pode criar valores fixos ou fazer cálculos que serão usados em várias partes do código. É como se fossem “apelidos” para valores que você quer reutilizar. Por exemplo, se você sempre precisa de um nome padrão para servidores ou de uma fórmula para calcular um valor, você cria isso nos `locals` e usa quando precisar. Assim, se precisar mudar, você só altera em um lugar.
- **Tipos de parâmetros:**
    - **required_version**: Esse parâmetro é como dizer "eu só trabalho com essa versão do Terraform". Ele define a versão mínima (ou exata) que o Terraform precisa ter para rodar o código. É como se você estivesse garantindo que todo mundo está usando a ferramenta do mesmo jeito, sem problemas de versão.
    - **required_providers**: Isso é como fazer uma "lista de fornecedores" que o Terraform precisa para construir tudo. Aqui, você lista todos os provedores (AWS, Azure, Google, etc.) que o projeto vai usar e qual a versão mínima de cada um. É uma forma de garantir que o Terraform vai conseguir criar todos os recursos.
    - **backend**: O `backend` é onde o Terraform guarda as “plantas” do que ele construiu (os dados do estado atual). Isso pode ser em um arquivo local ou na nuvem. É como guardar um mapa de tudo o que já foi feito, para o Terraform saber o que mudou quando for rodar de novo.
    - **cloud:** Esse parâmetro permite conectar o Terraform diretamente a uma conta na nuvem (como no Terraform Cloud). Ele ajuda a controlar o que está sendo construído, colaborar com outras pessoas e ter o estado do projeto guardado de forma segura.
    - **experiments:** Esse parâmetro ativa funções novas que o Terraform ainda está testando, como uma "área de experimentos". Ele permite usar funcionalidades que ainda estão sendo aprimoradas, mas que podem ser úteis para testar novas ideias.
    - **provider_meta:** Esse é um parâmetro avançado usado para passar informações específicas para os provedores que não estão no `provider` normal. Ele permite enviar configurações especiais para alguns provedores que precisam de ajustes extras para funcionar bem.
    
- **Main Commands:**
    - **`terraform init`**→ Inicializa o diretório de trabalho, baixando os plugins necessários e preparando o ambiente para rodar os comandos do Terraform.
    - **`terraform validate`**→ Verifica a configuração dos arquivos para garantir que estão escritos corretamente e sem erros de sintaxe.
    - **`terraform plan`**→ Gera um plano de execução mostrando quais recursos serão criados, alterados ou destruídos sem realizar alterações de fato.
    - **`terraform apply`**→ Executa o plano gerado, aplicando as alterações na infraestrutura, criando ou modificando recursos conforme necessário.
    - **`terraform destroy`**→ Remove todos os recursos gerenciados pela configuração do Terraform, destruindo a infraestrutura criada.
    - **`terraform fmt`**→ Formata os arquivos de configuração (.tf) de acordo com o padrão do Terraform, organizando o código.
