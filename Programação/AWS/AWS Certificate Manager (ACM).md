O **AWS Certificate Manager (ACM)** é um serviço da AWS que facilita a criação, gerenciamento e implantação de certificados SSL/TLS para proteger conexões de rede e sites na AWS. Com ele, você pode emitir certificados públicos e privados de forma gratuita (para certificados públicos), além de configurar e renovar automaticamente esses certificados em seus recursos da AWS, como Load Balancers, CloudFront e APIs no [[AWS API Gateway|API Gateway]] (veja também o [[Guia AWS - Conceitos de Escalabilidade, Elasticidade, Disponibilidade, Auto Scaling, ELB e ALB|guia de ELB/ALB e Auto Scaling]]).

### Principais Funcionalidades do AWS Certificate Manager

1. **Emissão de Certificados SSL/TLS**:
    
    - O ACM permite a emissão de certificados SSL/TLS públicos para proteger a comunicação entre usuários e recursos públicos da AWS. Esses certificados ajudam a assegurar que a conexão com seu site ou aplicação é segura.
2. **Gerenciamento Automático de Certificados**:
    
    - O ACM gerencia automaticamente a renovação dos certificados, evitando problemas de expiração. Esse gerenciamento automático é especialmente útil para certificados públicos, que o ACM renova sem custos adicionais.
3. **Certificados Privados**:
    
    - Além de certificados públicos, o ACM também oferece suporte à emissão de certificados privados para uso interno, em conjunto com o **AWS Private Certificate Authority (AWS Private CA)**. Esses certificados podem proteger conexões internas em ambientes corporativos, como entre serviços da AWS ou com aplicativos hospedados on-premises.
4. **Implantação Facilitada**:
    
    - O ACM facilita a implantação de certificados diretamente em serviços como Elastic Load Balancing, Amazon CloudFront e API Gateway, permitindo a proteção das conexões SSL/TLS sem necessidade de manipular chaves privadas.
5. **Compatibilidade com Outras Regiões**:
    
    - Certificados públicos emitidos pelo ACM são regionais, mas é possível configurá-los para serem usados em várias regiões, o que é particularmente útil para aplicações distribuídas.
6. **Integração com Outros Serviços da AWS**:
    
    - O ACM se integra com o AWS CloudFormation, permitindo que você defina certificados como parte de seus templates de infraestrutura, além de funcionar bem com o AWS Identity and Access Management (IAM) para controle de acesso.

### Como Usar o AWS Certificate Manager

1. **Solicitar um Certificado**:
    
    - No console do ACM, você solicita um novo certificado. Basta informar o nome de domínio (ou domínios) que deseja proteger. O ACM valida a propriedade do domínio usando métodos como validação por e-mail ou DNS.
2. **Validar o Certificado**:
    
    - Após a solicitação, você precisa validar a propriedade do domínio. Com validação via DNS, o ACM fornecerá um registro CNAME que você deve adicionar às configurações de DNS do domínio. Assim que a propriedade é validada, o certificado é emitido.
3. **Implantar o Certificado**:
    
    - Uma vez emitido, você pode associar o certificado aos serviços da AWS compatíveis, como Application Load Balancer, CloudFront e API Gateway, para habilitar a comunicação segura.
4. **Gerenciar e Renovar o Certificado**:
    
    - Para certificados públicos, o ACM lida automaticamente com a renovação. Certificados privados também podem ser renovados automaticamente, mas podem incorrer em custos adicionais se forem emitidos via AWS Private CA.

### Exemplo de Uso do AWS Certificate Manager

Imagine que você tenha um site hospedado em uma aplicação servida por um **Application Load Balancer (ALB)**. Para proteger o tráfego entre os usuários e o ALB com HTTPS, você poderia seguir estes passos:

1. **Solicitar um Certificado** no ACM para o domínio do site, por exemplo, `meusite.com`.
2. **Validar o Domínio** adicionando o registro CNAME fornecido pelo ACM no seu provedor de DNS.
3. **Associar o Certificado** ao ALB. No console do ALB, basta selecionar o certificado do ACM e configurar o listener HTTPS, garantindo uma conexão segura para os visitantes.

### Resumo

O **AWS Certificate Manager** é uma solução prática e automatizada para gerenciar certificados SSL/TLS, que facilita a proteção de sites e aplicações com segurança ro