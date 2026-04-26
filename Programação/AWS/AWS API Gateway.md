# Amazon API Gateway

Amazon API Gateway é um serviço gerenciado que facilita a criação, publicação, manutenção, monitoramento e segurança de APIs em escala. Ele permite que os desenvolvedores criem APIs RESTful e WebSocket para conectar aplicações de backend com os clientes, permitindo a comunicação em tempo real e a troca de dados.

## Características principais
- **Criação de APIs**: Permite que os desenvolvedores criem APIs RESTful e WebSocket com facilidade, definindo métodos de solicitação, parâmetros, autenticação e muito mais.
- **Gerenciamento de tráfego**: O API Gateway gerencia automaticamente o tráfego de API, garantindo que as chamadas sejam roteadas para os serviços apropriados e permitindo a implementação de controles de taxa e limites de uso.
- **Integração com AWS Lambda**: O API Gateway se integra perfeitamente com AWS Lambda, permitindo que as funções Lambda sejam acionadas diretamente em resposta a chamadas de API.
- **Segurança**: Oferece recursos de autenticação e autorização, como integração com AWS Identity and Access Management (IAM), Amazon Cognito e chaves de API para proteger as APIs.

## Casos de uso
- **Construção de microserviços**: Facilita a implementação de uma arquitetura de microserviços, permitindo que diferentes serviços se comuniquem por meio de APIs.
- **Criação de backends para aplicações móveis**: Permite que desenvolvedores criem backends escaláveis e gerenciados para aplicações móveis, conectando-se a bancos de dados, serviços e outras APIs.
- **Exposição de serviços existentes**: Torna fácil expor serviços internos como APIs públicas, permitindo acesso seguro a recursos e dados.

## Benefícios
- **Escalabilidade**: O API Gateway é projetado para escalar automaticamente, suportando picos de tráfego sem a necessidade de intervenção manual.
- **Redução de custos**: Os desenvolvedores pagam apenas pelas chamadas de API e pelo tráfego, permitindo uma estrutura de custos eficiente.
- **Monitoramento e análise**: O serviço oferece integrações com Amazon CloudWatch para monitorar métricas, configurar alarmes e visualizar logs, facilitando a detecção de problemas e a otimização de desempenho.

## Integração com outros serviços da AWS
- **[[AWS Lambda]]**: Permite que funções Lambda sejam acionadas diretamente em resposta a solicitações de API.
- **[[Guia AWS - Bancos de Dados na AWS#4. Amazon DynamoDB|AWS DynamoDB]]**: Pode ser usado para conectar a APIs que interagem com dados armazenados no DynamoDB.
---

**Links úteis:**
- [Página oficial do Amazon API Gateway](https://aws.amazon.com/api-gateway/)