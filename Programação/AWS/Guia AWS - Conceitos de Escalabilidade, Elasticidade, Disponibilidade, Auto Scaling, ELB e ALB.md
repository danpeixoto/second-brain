

## 1. Escalabilidade

Escalabilidade refere-se à capacidade de um sistema aumentar ou diminuir recursos de acordo com a demanda. Existem dois tipos principais:

- **Escalabilidade vertical (Scale Up):** Aumenta a capacidade de um único recurso, como adicionar mais memória ou CPU a uma instância **[[AWS EC2|EC2]]**.
- **Escalabilidade horizontal (Scale Out):** Adiciona mais instâncias de recursos, como distribuir a carga entre várias instâncias **[[AWS EC2|EC2]]** atrás de *load balancers* expostos na **[[Guia AWS - Redes na AWS|VPC]]** (ALB/NLB) e, quando a carga muda, **[[Guia AWS - Amazon S3 (Simple Storage Service)|S3]]** e filas/mensageria (por exemplo **[[AWS SQS|SQS]]**) desacoplam picos.

### Benefícios:
- Capacidade de lidar com crescimento repentino de tráfego sem impacto na performance.
- Melhoria na distribuição de carga.

## 2. Elasticidade

Elasticidade é a habilidade de um sistema ajustar automaticamente os recursos provisionados de acordo com a demanda em tempo real, sem intervenção manual. Isso significa que os recursos podem aumentar durante picos de uso e diminuir quando a demanda é baixa, otimizando custos.

### Benefícios:
- Eficiência de custos.
- Resposta rápida a variações de carga.

## 3. Disponibilidade

Disponibilidade refere-se à capacidade de um sistema estar operacional e acessível quando necessário. Na AWS, isso é garantido por zonas de disponibilidade (Availability Zones - AZs) e regiões, permitindo que os serviços sejam replicados geograficamente para evitar downtime.

### Alta Disponibilidade (HA):
- **Alta Disponibilidade** significa que o sistema permanece funcional mesmo em caso de falhas, graças à redundância.
- AWS fornece garantias de SLA (Service Level Agreement) para muitos de seus serviços, como EC2 e RDS.

## 4. Auto Scaling

Auto Scaling é um serviço da AWS que permite aumentar ou diminuir automaticamente a quantidade de instâncias EC2 (ou outros recursos) com base em métricas predefinidas, como CPU, tráfego de rede, etc.

### Como funciona:
- Define-se um grupo de instâncias que pode ser escalado automaticamente.
- As regras de escalabilidade podem ser baseadas em tempo, métricas ou ambas.
- Pode realizar tanto o **Scale Out** (adicionar instâncias) quanto o **Scale In** (remover instâncias).

### Benefícios:
- Ajuste automático de recursos de acordo com a demanda.
- Otimização de custos, pois as instâncias desnecessárias são desligadas.

## 5. Elastic Load Balancing (ELB)

O ELB distribui automaticamente o tráfego de entrada entre várias instâncias EC2 ou outros recursos. Isso garante que nenhuma instância fique sobrecarregada e melhora a resiliência do sistema.

### Tipos de ELB:
- **Application Load Balancer (ALB):** Ideal para tráfego HTTP/HTTPS. Oferece roteamento baseado em conteúdo e permite redirecionar tráfego com base em regras como URL ou parâmetros de cabeçalho.
- **Network Load Balancer (NLB):** Usado para tráfego em nível de transporte (camada 4), ideal para cargas com baixa latência e alto volume de conexões.
- **Classic Load Balancer (CLB):** Uma versão mais antiga, suporta tráfego HTTP/HTTPS e TCP, mas com menos funcionalidades que o ALB e NLB.

### Benefícios:
- Distribuição automática do tráfego de rede.
- Suporte a alta disponibilidade e escalabilidade.
- Capacidade de rotear o tráfego de acordo com regras específicas (no caso do ALB).

## 6. Application Load Balancer (ALB)

O Application Load Balancer (ALB) opera na camada 7 (camada de aplicação) do modelo OSI, o que permite roteamento avançado com base no conteúdo da solicitação HTTP, como caminho de URL, cabeçalhos ou parâmetros.

### Características:
- Suporte nativo a HTTP/2 e WebSockets.
- Roteamento inteligente, como redirecionar tráfego com base no caminho da URL ou parâmetros de cabeçalho.
- Melhor para aplicações web que requerem roteamento dinâmico e granular.
- Integração com serviços como AWS Lambda, ECS e Fargate.

### Benefícios:
- Flexibilidade no roteamento de tráfego com base no conteúdo da solicitação.
- Suporte a microserviços e arquiteturas baseadas em contêineres.
- Roteamento e balanceamento otimizados para tráfego web.

## 7. Elastic Load Balancer x Application Load Balancer

### ELB:
- Distribui tráfego entre várias instâncias EC2.
- Adequado para cargas genéricas e tráfego misto (HTTP/HTTPS/TCP).

### ALB:
- Específico para tráfego HTTP/HTTPS.
- Melhor controle de roteamento, ideal para arquiteturas baseadas em serviços e aplicações modernas.

---

## Conclusão

Esses conceitos são cruciais para criar sistemas resilientes, escaláveis e eficientes em termos de custos na AWS. Escalabilidade e elasticidade permitem que suas aplicações cresçam de forma eficiente, enquanto Auto Scaling e ELB/ALB garantem que você tenha sempre a capacidade necessária, sem pagar por recursos desnecessários.
