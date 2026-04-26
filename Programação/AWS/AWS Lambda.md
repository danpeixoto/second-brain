# AWS Lambda

AWS Lambda é um serviço de computação sem servidor que permite executar código em resposta a eventos, sem a necessidade de provisionar ou gerenciar servidores. Ele é projetado para tornar a construção de aplicações escaláveis e responsivas mais fácil, permitindo que os desenvolvedores se concentrem na lógica do aplicativo em vez de se preocupar com a infraestrutura.

## Características principais
- **Execução sob demanda**: O código é executado apenas quando um evento é acionado, como mudanças em dados em um bucket do Amazon S3, atualizações em um banco de dados ou chamadas de API.
- **Suporte a várias linguagens**: Lambda suporta várias linguagens de programação, incluindo Node.js, Python, Java, Go, Ruby, .NET e mais, permitindo que os desenvolvedores usem a linguagem com a qual estão mais confortáveis.
- **Escalabilidade automática**: O serviço escala automaticamente em resposta ao volume de eventos, permitindo que você execute milhares de funções simultaneamente sem esforço adicional.
- **Integração com outros serviços da AWS**: Lambda se integra facilmente com outros serviços da AWS, como Amazon S3, Amazon DynamoDB, Amazon Kinesis e Amazon API Gateway, permitindo a criação de aplicações complexas com facilidade.

## Casos de uso
- **Processamento de dados**: Pode ser usado para processar dados em tempo real, como transformar dados de fluxo com o Amazon Kinesis ou processar arquivos carregados no S3.
- **Desenvolvimento de APIs**: Lambda é frequentemente utilizado em conjunto com o Amazon API Gateway para criar APIs RESTful que respondem a solicitações HTTP.
- **Automação de tarefas**: Permite a automação de tarefas administrativas, como backups automáticos, manipulação de dados e notificações.

## Benefícios
- **Custo-efetivo**: Você paga apenas pelo tempo de execução e pela quantidade de memória utilizada, eliminando custos fixos associados a servidores provisionados.
- **Agilidade no desenvolvimento**: Permite que os desenvolvedores se concentrem na escrita do código, acelerando o ciclo de desenvolvimento e implantação.
- **Gerenciamento simplificado**: Como um serviço gerenciado, o Lambda cuida da infraestrutura subjacente, permitindo que você se concentre em escrever e testar seu código.

## Integração com outros serviços da AWS
- **[[Guia AWS - Amazon S3 (Simple Storage Service)|AWS S3]]**: Lambda pode ser acionado por eventos, como o upload de um arquivo em um bucket do S3.
- **[[Guia AWS - Bancos de Dados na AWS#4. Amazon DynamoDB|AWS DynamoDB]]**: Você pode usar Lambda para processar eventos de alteração em tabelas do DynamoDB, como inserções ou atualizações.
- **[[AWS API Gateway]]**: Permite criar APIs RESTful que invocam funções Lambda em resposta a chamadas de API.

---

**Links úteis:**
- [Página oficial do AWS Lambda](https://aws.amazon.com/lambda/)