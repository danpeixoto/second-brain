# AWS VPC (Virtual Private Cloud)

## O que é o AWS VPC?

O **AWS VPC (Virtual Private Cloud)** permite criar uma rede virtual privada dentro da infraestrutura da AWS, onde você pode isolar e gerenciar recursos de rede. O VPC oferece controle granular sobre endereços IP, sub-redes, roteamento, gateways, e segurança, permitindo configurar redes de acordo com as necessidades específicas dos seus workloads.

### Principais Recursos do VPC

1. **Sub-redes**: Dividem a rede em segmentos públicos e privados, onde:
    
    - Sub-redes públicas podem ser acessadas diretamente pela Internet.
    - Sub-redes privadas são isoladas e acessíveis apenas dentro do VPC.
2. **Roteamento**: Controla o fluxo de tráfego entre sub-redes e com a Internet usando tabelas de roteamento e gateways de Internet (IGW).
    
3. **Security Groups e NACLs (Network Access Control Lists)**:
    
    - Security Groups controlam o acesso a nível de instância, permitindo ou bloqueando tráfego.
    - NACLs controlam o tráfego em um nível de sub-rede, proporcionando uma camada adicional de segurança.
4. **Gateways**:
    
    - **Internet Gateway (IGW)**: Permite que recursos em sub-redes públicas se conectem à Internet.
    - **NAT Gateway**: Permite que instâncias em sub-redes privadas façam solicitações de saída para a Internet enquanto permanecem inacessíveis externamente.

## Integração com Outros Serviços AWS

- **[[AWS EC2]]**: EC2 executa instâncias em sub-redes do VPC. Com o VPC, você pode configurar o acesso de instâncias EC2 à Internet e entre sub-redes. EC2 permite configurações detalhadas de segurança com Security Groups e NACLs para gerenciar tráfego.
    
- **[[AWS ECS]]**: ECS usa VPCs para implantar e escalar contêineres. Ao configurar clusters do ECS, você define sub-redes e configurações de segurança para garantir que as tarefas ECS estejam protegidas e acessíveis conforme necessário.
    
- **[[AWS EKS]]**: Clusters EKS são executados em sub-redes dentro do VPC, permitindo controle sobre o tráfego de rede para contêineres e conectividade com recursos externos.
    
- **[[AWS Lambda]]**: Funções Lambda podem ser configuradas para rodar em um VPC, o que é útil para acessar recursos privados ou bancos de dados que estão em sub-redes privadas. Para que uma função Lambda em um VPC tenha acesso à Internet, você deve configurá-la com um NAT Gateway ou VPC Endpoint.
    

## VPC e Segurança

O VPC oferece uma abordagem robusta de segurança, onde cada recurso em sua rede pode ser protegido com Security Groups e NACLs. Esses controles são essenciais para proteger dados e controlar o acesso entre componentes do seu ambiente na AWS.

### Casos de uso comuns

- **Isolamento de Ambientes**: Criar múltiplos VPCs para separar ambientes de desenvolvimento, teste e produção.
- **Redes Híbridas**: Usar VPC para integrar redes locais com a AWS, facilitando o uso do Direct Connect ou VPN para conexões privadas e seguras.
- **Acesso Seguro a Serviços AWS**: Configurar VPC Endpoints para acessar serviços como S3 e DynamoDB sem usar a Internet.