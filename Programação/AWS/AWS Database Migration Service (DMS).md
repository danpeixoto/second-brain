O **AWS Database Migration Service (DMS)** é um serviço da Amazon Web Services que facilita a **migração e replicação de dados entre bancos de dados**, em linha com os motores e padrões descritos em **[[Guia AWS - Bancos de Dados na AWS|Bancos de Dados na AWS]]**. Ele permite transferir dados de um banco de dados de origem (que pode ser local ou na nuvem) para um banco de dados de destino na AWS, com o mínimo de tempo de inatividade. O DMS é altamente útil para quem precisa migrar dados para a nuvem, atualizar versões de bancos de dados ou manter dados sincronizados entre várias bases de dados.

### Principais Funcionalidades do AWS DMS

1. **Migração de Bancos de Dados com Pouco ou Nenhum Downtime**:
    
    - O DMS foi projetado para migrar dados enquanto mantém o banco de dados de origem ativo, permitindo que aplicativos continuem funcionando. Ele é ideal para migrações que precisam ocorrer sem interrupção dos serviços.
2. **Suporte para Bancos de Dados Heterogêneos e Homogêneos**:
    
    - **Migrações Homogêneas**: Quando a origem e o destino usam o mesmo tipo de banco de dados (ex.: MySQL para MySQL).
    - **Migrações Heterogêneas**: Quando a origem e o destino são diferentes (ex.: Oracle para Amazon Aurora). Nesse caso, o DMS pode ser usado junto com o **AWS Schema Conversion Tool (SCT)**, que converte o esquema e objetos de banco de dados para o novo sistema.
3. **Replicação Contínua de Dados**:
    
    - Além de migrações pontuais, o DMS pode realizar **replicação contínua** de dados. Isso é útil para manter uma base de dados de backup ou sincronizar dados em tempo real entre diferentes sistemas.
4. **Compatibilidade com Vários Tipos de Bancos de Dados**:
    
    - O DMS é compatível com vários bancos de dados, como:
        - Relacionais: **Amazon RDS, Aurora, MySQL, PostgreSQL, Oracle, SQL Server, MariaDB**.
        - Não relacionais: **Amazon DynamoDB, MongoDB**.
        - Bancos de dados em nuvem e locais (on-premises).
    - Isso permite migrações entre diferentes tipos de bancos, como de um banco relacional para um banco NoSQL, facilitando arquiteturas híbridas e flexíveis.
5. **Facilidade de Uso e Gerenciamento**:
    
    - O DMS é um serviço gerenciado, o que significa que a AWS cuida do gerenciamento de servidores e da escalabilidade.
    - No console do AWS DMS, você define o banco de dados de origem, o destino e configura as opções de replicação, e o serviço gerencia o restante do processo.

### Casos de Uso Comuns

1. **Migração para a Nuvem**:
    
    - Migrar bancos de dados locais ou de outras nuvens para a AWS com interrupção mínima, ideal para organizações que querem se beneficiar dos recursos de banco de dados gerenciados na AWS.
2. **Atualizações de Versão e Modernização de Bancos de Dados**:
    
    - Migrar para uma versão mais recente de um banco de dados ou mover dados para bancos de dados otimizados para a nuvem, como Amazon Aurora, que são mais escaláveis e custam menos para operar.
3. **Replicação Contínua e Backup**:
    
    - Manter uma cópia de um banco de dados de produção em tempo real em outra região ou conta para backup e recuperação de desastres.
4. **Sincronização entre Ambientes Híbridos**:
    
    - Manter um banco de dados local sincronizado com a nuvem para uso em arquiteturas híbridas, permitindo acesso a dados em tempo real em ambos os ambientes.

### Como Funciona o AWS DMS?

1. **Configuração da Tarefa de Migração**:
    
    - No console do DMS, você cria uma **tarefa de migração**, onde especifica o banco de dados de origem e o de destino, além das configurações de replicação.
2. **Execução e Monitoramento**:
    
    - O DMS copia os dados de forma eficiente, lidando automaticamente com desafios de rede e ajustando a taxa de transferência para otimizar o desempenho.
    - Durante a migração, você pode monitorar o progresso no console e no **Amazon CloudWatch**, que fornece métricas em tempo real.
3. **Conversão de Esquema (para Migrações Heterogêneas)**:
    
    - Para migrações onde o banco de dados de origem e o de destino são diferentes, o **AWS Schema Conversion Tool (SCT)** converte o esquema do banco de dados de origem para o novo sistema de destino.

### Resumo

O **AWS DMS** é uma solução poderosa para quem precisa migrar, replicar ou sincronizar dados de bancos de dados. Ele oferece flexibilidade para trabalhar com diferentes tipos de bancos de dados, tanto relacionais quanto não relacionais, e possibilita migrações com interrupção mínima. Isso facilita a modernização e a adaptação da infraestrutura de dados para ambientes na nuvem de forma prática e segura.