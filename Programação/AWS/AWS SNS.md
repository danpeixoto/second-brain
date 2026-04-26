**AWS SNS** é um serviço de mensagens de publicação/assinatura (pub/sub) que permite enviar notificações para múltiplos assinantes, muitas vezes em padrão *fan-out* com **[[AWS SQS|SQS]]** e consumo por **[[AWS Lambda|Lambda]]**; compare padrões em **[[Diferença entre SQS e SNS|SQS vs SNS]]**.

- **Características principais**:
  - Totalmente gerenciado e escalável.
  - Suporta múltiplos protocolos de entrega, como HTTP/HTTPS, e-mail, SMS, e AWS Lambda.
  - Permite a criação de tópicos (topics) para onde as mensagens são publicadas.

- **Casos de uso**:
  - Notificações de aplicações para usuários.
  - Monitoramento de eventos ou alertas em sistemas.
  - Desencadeamento de ações em resposta a eventos de outras aplicações.
