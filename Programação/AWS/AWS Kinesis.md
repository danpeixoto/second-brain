**AWS Kinesis** é um serviço para coletar, processar e analisar grandes volumes de dados em tempo real. É ideal para aplicações que precisam processar dados de streaming em tempo real, como logs, eventos de IoT e cliques em sites, muitas vezes encadeado a processamento com **[[AWS Lambda|Lambda]]** e persistência.

- **Componentes principais**:
  - **Kinesis Data Streams**: Serviço para capturar dados de streaming em tempo real. Útil para processar dados que chegam em alta frequência.
  - **Kinesis Data Firehose**: Para carregar dados de streaming em destinos como **[[Guia AWS - Amazon S3 (Simple Storage Service)|S3]]**, **[[AWS Redshift|Redshift]]**, OpenSearch/[[AWS OpenSearch - ElasticSearch|OpenSearch Service]] ou Splunk, sem a necessidade de gerenciamento de servidores.
  - **Kinesis Data Analytics**: Permite processar e analisar dados de streaming usando SQL em tempo real.

- **Casos de uso**:
  - Análise de logs em tempo real.
  - Processamento de eventos de IoT.
  - Monitoramento de atividades em sites ou aplicativos.
