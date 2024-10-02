# AWS Step Functions - resumo

Para criar um "Hello World" usando AWS Step Functions e exportar para JSON, é preciso entender alguns conceitos importantes.

1. AWS Step Functions Overview

AWS Step Functions é um serviço que permite orquestrar vários serviços da AWS em fluxos de trabalho chamados state machines. Você pode criar fluxos complexos de processos e automatizar vários serviços em uma sequência lógica.

2. ASL - Amazon States Language

A Amazon States Language (ASL) é o formato JSON utilizado para definir as máquinas de estado (state machines) no AWS Step Functions. Uma definição de state machine em ASL inclui:

States: Representam as etapas do processo.

Transitions: Transições entre esses estados.

Data Handling: Manipulação de dados passando entre as etapas.


3. Criando um "Hello World"

Passos Gerais:

1. Configurar a Máquina de Estado no Console da AWS

Vá ao console do AWS Step Functions.

Clique em "Create state machine".

Escolha entre os modelos pré-definidos ou crie uma nova usando a ASL.



2. Definir a Máquina de Estado usando ASL

Um exemplo simples de máquina de estado "Hello World" em ASL pode ser assim:

{
  "Comment": "A simple AWS Step Functions Hello World example",
  "StartAt": "HelloWorld",
  "States": {
    "HelloWorld": {
      "Type": "Pass",
      "Result": "Hello, World!",
      "End": true
    }
  }
}

Neste exemplo:

StartAt define o estado inicial da máquina.

States contém o estado chamado "HelloWorld", que é do tipo "Pass" (passa dados sem transformá-los).

Result é a mensagem que será retornada.

End indica o final da execução.




3. Exportar para JSON

Após configurar a máquina de estado, você pode visualizar e exportar a definição JSON da máquina diretamente no console do AWS Step Functions.



4. Executar a Máquina de Estado

Depois de configurar, você pode executar a máquina de estado para ver a saída "Hello, World!".

O console fornece uma visualização passo a passo do fluxo de trabalho e permite monitorar a execução.




4. Principais Blocos e Funções de uma State Machine

Task: Executa uma tarefa, como chamar um serviço AWS Lambda ou outro serviço da AWS.

Choice: Executa lógica condicional para direcionar o fluxo de acordo com certas condições.

Parallel: Executa tarefas em paralelo.

Wait: Adiciona uma pausa na execução por um período de tempo ou até um momento específico.

Pass: Passa os dados para frente sem alterá-los (útil para depuração ou roteamento simples).

Fail / Succeed: Indicadores de conclusão da execução com sucesso ou falha.


5. Aprofundando em ASL

ASL é declarativo e se concentra na definição dos estados e no fluxo entre eles.

Você pode adicionar transformações de dados, capturar e manipular exceções, e fazer lógica condicional.
Se for fazer o "Hello World" no AWS Step Functions usando uma abordagem de low-code/no-code diretamente pelo console, aqui estão os passos simplificados:

1. Acessar o Console do AWS Step Functions

Vá para o console da AWS e selecione "Step Functions" no menu de serviços.

Clique em “Create state machine”.



2. Escolher a Opção de Visual Workflow

Escolha a opção “Visual Workflow” para uma abordagem de construção arrastando e soltando (low-code).



3. Selecionar o Modelo de Workflow

Selecione "Author from scratch".

Escolha o tipo de state machine padrão (Standard ou Express) dependendo de sua necessidade (para um "Hello World", qualquer um serve).



4. Adicionar Estados Usando o Construtor Visual

No construtor visual, você pode adicionar estados à sua state machine. Para criar um "Hello World", siga os próximos passos:

Adicionar um Estado "Pass"

Clique no botão “+ Add state”.

Escolha "Pass" como tipo de estado.

Nomeie-o como “HelloWorld”.

Em "Result", coloque a mensagem desejada, como "Hello, World!".

Marque a opção "End state" para indicar que este estado conclui a execução.


Configurar o Estado Inicial

Verifique se o estado “HelloWorld” está marcado como o estado inicial (terá uma estrela ao lado).




5. Visualizar o Fluxo de Trabalho

O console criará automaticamente o fluxo de trabalho com base nas configurações do estado.

Você verá um bloco representando o estado “HelloWorld” que passa os dados e encerra a execução.



6. Salvar e Executar a Máquina de Estado

Clique em “Next”.

Dê um nome à sua state machine.

Escolha uma função IAM para permissões de execução (pode usar uma função padrão ou criar uma nova).

Clique em “Create state machine”.



7. Executar a Máquina de Estado

Uma vez criada, você pode executar a máquina de estado clicando em “Start execution”.

Na execução, verá o estado “HelloWorld” e seu resultado: "Hello, World!".




Resumo do Processo "No-Code/Low-Code":

Visual Workflow: Use o editor visual para adicionar estados.

Pass State: Adicione um estado do tipo "Pass" para retornar a mensagem “Hello, World!”.

End State: Configure-o como estado final.

Salvar e Executar: Salve e execute para ver o fluxo completo e a mensagem de saída.


