O **AWS Shield** é um serviço de proteção contra ataques de **Distributed Denial of Service (DDoS)** que visa proteger aplicativos e infraestruturas hospedadas na AWS. Ele oferece duas camadas de proteção – **AWS Shield Standard** e **AWS Shield Advanced** – que ajudam a garantir a continuidade e disponibilidade dos serviços mesmo durante ataques DDoS.

### Principais Características do AWS Shield

1. **AWS Shield Standard**:
    
    - **Gratuito** e habilitado automaticamente para todos os clientes da AWS.
    - Protege contra ataques DDoS comuns na camada de rede e de transporte, como ataques de SYN/ACK floods e reflexões de UDP.
    - Defende serviços como Amazon CloudFront, Route 53, Elastic Load Balancing (ELB), e outros serviços expostos publicamente.
2. **AWS Shield Advanced**:
    
    - **Serviço pago**, com proteção mais robusta e monitoramento especializado.
    - Fornece proteção contra ataques DDoS mais sofisticados e com maior largura de banda.
    - Inclui **detecção de anomalias** e **mitigação automática** para minimizar o impacto em tempo real, com monitoramento de tráfego de 24 horas.
    - **Suporte de resposta a incidentes**: oferece acesso à equipe de resposta de segurança da AWS (DDoS Response Team, ou DRT) que pode ajudar na análise e resposta durante um ataque.
    - **Cobertura de Custos**: Shield Advanced cobre alguns custos extras que poderiam ser gerados por aumentos no uso de recursos devido a ataques.
    - Proteção para serviços como EC2, Elastic IP, CloudFront, ELB, e Global Accelerator.
3. **Proteção em Camadas**:
    
    - Shield protege em múltiplas camadas do modelo OSI, especialmente as camadas 3 (rede), 4 (transporte) e parcialmente a camada 7 (aplicação), em combinação com o **AWS Web Application Firewall (WAF)** para proteção contra ameaças baseadas em aplicação.

### Como Funciona o AWS Shield?

- **Detecção e Mitigação**: O AWS Shield detecta e responde automaticamente a padrões de tráfego suspeitos que indicam ataques DDoS. Ele utiliza a infraestrutura global da AWS para desviar e mitigar o tráfego malicioso antes que ele alcance o recurso de destino.
    
- **Integração com outros serviços**: Shield trabalha em conjunto com outros serviços, como o CloudFront e o AWS WAF, permitindo criar políticas que bloqueiem tráfego malicioso enquanto permitem o tráfego legítimo.
    
- **Relatórios e Monitoramento**: Com o Shield Advanced, você tem acesso a relatórios detalhados e monitoramento do tráfego durante ataques, e ao AWS CloudWatch para configurar alertas e acompanhar métricas em tempo real.
    

### Casos de Uso do AWS Shield

1. **Sites de E-commerce e Aplicações Sensíveis a Downtime**:
    
    - Protege contra ataques DDoS que visam interromper operações de negócios ou causar indisponibilidade de serviços.
2. **Aplicações com Exposição Global**:
    
    - Aplicações distribuídas em várias regiões, especialmente aquelas usando CloudFront, podem ser protegidas contra ataques que visam diversas localizações geográficas.
3. **Proteção de Infraestrutura Crítica**:
    
    - Organizações que executam infraestrutura crítica, como bancos ou sistemas de saúde, podem usar Shield Advanced para proteção intensiva e suporte especializado em caso de ataques.

### Resumo das Diferenças entre Shield Standard e Advanced

|Característica|AWS Shield Standard|AWS Shield Advanced|
|---|---|---|
|**Preço**|Gratuito|Pago (com base nos recursos protegidos)|
|**Proteção**|Básica contra DDoS de rede e transporte|Proteção avançada e personalizável contra DDoS|
|**Cobertura de Custos**|Não|Sim, cobre custos adicionais causados por ataques|
|**Suporte Especializado**|Não|Sim, acesso à equipe de resposta de DDoS (DRT)|
|**Monitoramento e Relatórios**|Limitado|Detalhado, com relatórios e suporte CloudWatch|
|**Serviços Suportados**|CloudFront, ELB, Route 53|EC2, ELB, CloudFront, Route 53, e mais|

O **AWS Shield** é essencial para proteger a infraestrutura contra ataques DDoS, especialmente para empresas que dependem da alta disponibilidade de suas aplicações.