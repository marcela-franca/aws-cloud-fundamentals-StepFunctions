# AWS Cloud Fundamentals - Step Functions
Esse projeto tem como objetivo exemplificar o uso da ferramenta AWS Step Functions, um serviço que facilita a automação de fluxos de trabalho (Workflows) dentro da plataforma.
Com ele, é possível *orquestrar diferentes serviços da AWS* de forma simples, visual e automatizada, tornando o desenvolvimento de processos complexos mais rápido e menos propenso a erros e trazendo coisas abstratas para o visual, o que pode facilitar ainda mais o desenvolvimento de automações.

## Objetivo
Demonstrar, na prática, como orquestrar um *Workflow automatizado* com o serviço Step Functions, integrando diferentes serviços das AWS que aprendi no decorrer do curso de forma ainda mais performática.

# Documentação

1. Acesse sua conta [AWS](https://aws.amazon.com/console/).
2. Navegue a buscando pelo serviço "Step-Functions".
   
   <img width="1475" height="597" alt="image" src="https://github.com/user-attachments/assets/c3fcf506-72c4-4a61-ac82-d33d1066990f" />

4. Selecione o botão, "Get Started' (Comece a Usar) para criar o seu próprio workflow.

   <img width="1488" height="594" alt="image" src="https://github.com/user-attachments/assets/28f728fa-6f9b-44d1-9621-65e1a7004c0a" />

6. Escolha entre "Choose a template" (Escolha um template) ou "Create your own" (Crie o seu próprio), como o proposito do meu projeto é desenvolver algo, optei por "Create your own".

    <img width="1481" height="652" alt="image" src="https://github.com/user-attachments/assets/92ce2fdc-1119-4dee-83f1-3ad6116b2793" />
    
7.  Adicione um nome que faça sentido para o projeto a ser criado, algo que seja intuitivo apenas pelo nome.
8. Escolha entre criar um *fluxo de trabalho padrão* (Standard) ou *express* (Express).

  <img width="1471" height="456" alt="image" src="https://github.com/user-attachments/assets/dcb1fbf8-1290-499e-a39a-5411ef6684ad" />

10. Configure os estados e ações desejadas (por exemplo: executar funções Lambda, armazenar dados no S3, etc).
11. Salve e execute seu workflow para validar a automação.

<img width="1543" height="558" alt="image" src="https://github.com/user-attachments/assets/f743f729-ed1c-49ac-91ed-ac0bb7aa326e" />

## Caso de Uso: Sistema de Monitoramento e Alerta de Orçamentos AWS

### Descrição do Fluxo
Este State Machine do AWS Step Functions automatiza o monitoramento proativo de orçamentos AWS, enviando notificações imediatas quando os gastos ultrapassam os limites definidos.

### Arquitetura do Fluxo
- CheckCurrentSpending (Verificação de Gastos Atuais) :
  - Consulta o serviço AWS Budgets para obter dados atualizados do orçamento;
  - Utiliza a API describeBudget com parâmetros dinâmicos (AccountId e BudgetName);
  - Inclui tratamento de erro para falhas na consulta;
    
- EvaluateSpending (Avaliação de Gastos):
  - Estado do tipo Choice que analisa condicionalmente os dados retornados;
  - Verifica se o gasto atual (ActualSpend.Amount) é maior que zero;
  - Encaminha para notificação caso a condição seja atendida;

- SendBudgetAlert (Envio de Alerta):
  - Publica mensagem no Amazon SNS quando o orçamento é ultrapassado;
  - Mensagem contém detalhes específicos: conta, nome do orçamento, gasto atual e limite;
  - Subject padronizado para fácil identificação;
  - Estados de Finalização;

- BudgetWithinLimit: Fluxo silencioso quando dentro do limite:

- HandleError: Tratamento de falhas com mensagem descritiva;

- SuccessState: Finalização bem-sucedida do processo;

## Características Principais

- Monitoramento Contínuo: Verificação automática do status do orçamento;

- Notificação Imediata: Alertas em tempo real via Amazon SNS;

- Customizável: Parâmetros dinâmicos para diferentes orçamentos e contas;

## Cenário de Aplicação

### Ideal para empresas que necessitam de:

- Controle rigoroso de custos na nuvem;

- Alertas proativos sobre gastos não planejados;

- Automação de processos financeiros AWS;

- Compliance com políticas de gastos;

Com o Step Functions, podemos *orquestrar essas etapas automaticamente* sem precisar criar código para controlar cada fluxo.

Projeto desenvolvido como parte do desafio da DIO - AWS Cloud Fundamentals.
