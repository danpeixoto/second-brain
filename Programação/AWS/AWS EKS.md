# EKS - Amazon Elastic Kubernetes Service

## O que é o EKS?

O Amazon Elastic Kubernetes Service (EKS) é um serviço gerenciado de Kubernetes da AWS que permite criar, gerenciar e escalar clusters de contêineres usando Kubernetes.

## Benefícios do EKS

- **Gerenciamento simplificado**: A AWS gerencia a infraestrutura do Kubernetes, facilitando a instalação e a manutenção de clusters.
- **Alta disponibilidade e segurança**: A AWS oferece segurança e resiliência nos clusters, com backups automáticos e integração com outros serviços de segurança da AWS.
- **Integração com outros serviços da AWS**: EKS trabalha bem com EC2, IAM, VPC, e outros serviços que ajudam a configurar e proteger ambientes de contêineres.

## Casos de uso

- **Aplicações escaláveis**: Implementação e gerenciamento de aplicações que precisam escalar com facilidade.
- **Orquestração de contêineres**: Automação do processo de implantação, gerenciamento e dimensionamento de contêineres.

## Conceitos importantes para o exame

1. **Clusters gerenciados**: O EKS gerencia clusters de Kubernetes, oferecendo controle sobre nós (EC2) e facilitando a execução de workloads.
2. **Elasticidade**: Facilita o ajuste de recursos de acordo com as necessidades do aplicativo, escalando automaticamente.
3. **Integração com IAM**: Autenticação e autorização são gerenciadas com o AWS IAM, permitindo controle granular de acesso.
4. **Altos níveis de segurança**: Implementação de políticas de segurança, com criptografia e VPC para isolamento de redes.

## Integração com outros serviços

- **IAM (Identity and Access Management)**: Controle de acesso e permissões para gerenciar os clusters e os nós.
- **VPC (Virtual Private Cloud)**: Isolamento de rede para clusters de Kubernetes.
- **CloudWatch**: Monitoramento e logging de eventos no cluster para acompanhar performance e segurança.