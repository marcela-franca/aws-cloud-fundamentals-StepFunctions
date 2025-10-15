# AWS Cloud Fundamentals - Step Functions
Esse projeto tem como objetivo *exemplificar o uso da ferramenta AWS Step Functions, um serviço que facilita a automação de fluxos de trabalho* (Workflows) dentro da plataforma.
Com ele, é possível *orquestrar diferentes serviços da AWS* de forma simples, visual e automatizada, tornando o desenvolvimento de processos complexos mais rápido e menos propenso a erros e trazendo coisas abstratas para o visual, o que pode facilitar ainda mais o desenvolvimento de automações.

## Objetivo
Demonstrar, na prática, como orquestrar um *Workflow automatizado* com o serviço Step Functions, integrando diferentes serviços das AWS que aprendi no decorrer do curso de forma ainda mais performática.

## Documentação de Acesso

1. Acesse sua conta [AWS](https://aws.amazon.com/console/).
2. Navegue a buscando pelo serviço "Step-Functions".
3. Selecione o botão, "Get Started' (Comece a Usar) para criar o seu próprio workflow.
4. Escolha entre "Choose a template" (Escolha um template) ou "Create your own" (Crie o seu próprio)
5. Escolha entre criar um *fluxo de trabalho padrão* (Standard) ou *express* (Express).
6. Configure os estados e ações desejadas (por exemplo: executar funções Lambda, armazenar dados no S3, etc).
7. Salve e execute seu workflow para validar a automação.

## Exemplo de Caso de Uso
Imagine um processo que envolva:
1. Realizar um backup de um banco de dados semanalmente.  

Com o Step Functions, podemos *orquestrar essas etapas automaticamente* sem precisar criar código para controlar cada fluxo.

Projeto desenvolvido como parte do desafio da DIO - AWS Cloud Fundamentals.
