## Tópicos-Chave para Certificação

### 1. **O que é EC2?**

- **Serviço de computação escalável**: Permite aumentar ou diminuir a capacidade de acordo com a demanda.
- **Instâncias Virtuais**: São servidores virtuais que você pode configurar de acordo com as necessidades.
- **Alta Flexibilidade**: Controle total sobre as instâncias, como SO, armazenamento e networking.

### 2. **Tipos de Instâncias**

EC2 oferece diferentes tipos de instâncias, otimizadas para diferentes casos de uso. São agrupadas em famílias com base no tipo de carga de trabalho que suportam. As principais famílias são:

|Família|Descrição|Exemplos de uso|
|---|---|---|
|**General Purpose**|Balanceia recursos de CPU, memória e rede. Ideal para uma variedade de workloads.|Web servers, dev/test environments. **(Ex: t3, m5)**|
|**Compute Optimized**|Projetado para cargas de trabalho intensivas em processamento.|Machine Learning, análises em tempo real. **(Ex: c5, c6g)**|
|**Memory Optimized**|Alta capacidade de memória, ideal para processar grandes conjuntos de dados.|Bancos de dados em memória, análises de big data. **(Ex: r5, x1)**|
|**Storage Optimized**|Projetado para cargas de trabalho que requerem alto desempenho de I/O de disco.|Aplicações que processam grandes volumes de dados. **(Ex: i3, d2)**|
|**Accelerated Computing**|Usa hardware especializado (GPU, FPGAs) para processamento de cargas de trabalho específicas.|Renderização de gráficos, simulações científicas. **(Ex: p3, g4)**|

> **Nota**: Entender os diferentes tipos de instâncias e suas famílias é importante para otimizar custos e performance em cenários reais.

### 3. **Modelos de Preços do EC2**

|Modelo|Descrição|Quando usar|
|---|---|---|
|**On-Demand**|Pagamento sob demanda por instâncias, sem compromissos de longo prazo.|Workloads de curto prazo ou imprevisíveis.|
|**Reserved Instances**|Desconto significativo para contratos de longo prazo (1 ou 3 anos).|Workloads estáveis e de longo prazo.|
|**Spot Instances**|Compra de capacidade não utilizada com grandes descontos. Interrompíveis a qualquer momento.|Workloads flexíveis, como processamento em lote ou big data.|
|**Savings Plans**|Modelos de pagamento que oferecem descontos para compromissos de uso por um período de tempo.|Para economia em workloads consistentes em execução.|
|**Dedicated Hosts**|Oferecem servidores físicos inteiros para uso exclusivo.|Para conformidade regulatória ou licenciamento de software.|

### 4. **Key Concepts**

- **AMI (Amazon Machine Image)**: Imagem que contém informações sobre a configuração do sistema operacional, software e definições de instâncias.
- **Security Groups**: Atuam como um firewall virtual para controlar o tráfego de entrada e saída das instâncias.
- **Elastic IP**: Endereços IP estáticos que você pode associar e dissociar de instâncias conforme necessário.
- **Auto Scaling**: Ajusta automaticamente o número de instâncias EC2 para lidar com alterações na carga de trabalho.
- **Elastic Load Balancer (ELB)**: Distribui automaticamente o tráfego de entrada por várias instâncias EC2.
- **EBS (Elastic Block Store)**: Fornece armazenamento persistente que pode ser anexado às instâncias EC2.

### 5. **Conceitos de Redundância e Alta Disponibilidade**

- **Zonas de Disponibilidade**: São locais fisicamente separados dentro de uma região AWS, projetados para serem isolados em caso de falhas.
- **Regiões**: Geograficamente distintas, consistem em várias Zonas de Disponibilidade.
- **Auto Scaling Groups**: Mantêm a quantidade correta de instâncias para a carga de trabalho, aumentando ou diminuindo o número de instâncias conforme necessário.

### 6. **Casos de Uso para EC2**

- Hospedagem de sites e aplicativos.
- Computação de alto desempenho.
- Execução de sistemas back-end de empresas.
- Desenvolvimento e testes de software.

