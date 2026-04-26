

## 1. O que é o Amazon S3?

Amazon S3 (Simple Storage Service) é um serviço de armazenamento de objetos altamente escalável, durável e seguro da AWS. Ele permite que você armazene e recupere qualquer quantidade de dados a qualquer momento, de qualquer lugar na web. É amplamente usado para armazenar arquivos, backups, dados de aplicação e outros conteúdos, muito acionado por **[[AWS Lambda|Lambda]]** e padrões de analytics com **[[AWS Athena|Athena]]** e **[[AWS Glue|Glue]]** no *data lake* em **S3** (o próprio tópico desta nota).

### Características principais:
- **Escalabilidade:** O S3 é altamente escalável, permitindo armazenar de megabytes a petabytes de dados.
- **Alta durabilidade:** Oferece 99.999999999% (11 9’s) de durabilidade dos objetos armazenados.
- **Alta disponibilidade:** O S3 garante 99.99% de disponibilidade.

## 2. Estrutura do S3

- **Bucket:** Os dados no S3 são armazenados em "buckets", que são contêineres que podem conter qualquer quantidade de objetos.
- **Objetos:** Os arquivos e seus metadados são chamados de objetos. Cada objeto é identificado por uma chave única dentro de um bucket.
- **Chave:** A chave é o identificador exclusivo do objeto dentro de um bucket. Funciona como o "nome do arquivo".

### Exemplo:
- **Bucket:** `meu-bucket`
- **Objeto:** `meu-documento.pdf`
- **Chave:** `docs/meu-documento.pdf`

## 3. Classes de Armazenamento

O Amazon S3 oferece várias classes de armazenamento, otimizadas para diferentes casos de uso com base na frequência de acesso e no custo. As classes mais comuns são:

### S3 Standard
- **Caso de uso:** Armazenamento de dados que são acessados com frequência.
- **Disponibilidade:** 99.99%
- **Durabilidade:** 99.999999999%
- **Custos:** É a opção mais cara devido à alta disponibilidade e desempenho.

### S3 Standard-IA (Infrequent Access)
- **Caso de uso:** Dados acessados com pouca frequência, mas que ainda precisam estar disponíveis rapidamente quando necessário.
- **Disponibilidade:** 99.9%
- **Durabilidade:** 99.999999999%
- **Custos:** Menor custo de armazenamento, mas cobra pela recuperação dos dados.

### S3 One Zone-IA
- **Caso de uso:** Dados infrequentemente acessados e que podem ser recriados em caso de perda.
- **Disponibilidade:** 99.5%
- **Durabilidade:** 99.999999999% dentro de uma única zona de disponibilidade.
- **Custos:** Mais barato que o Standard-IA, mas menos resiliente.

### S3 Glacier
- **Caso de uso:** Arquivamento de dados de longo prazo que raramente precisam ser acessados.
- **Recuperação:** De minutos a horas.
- **Custos:** Muito baixo para armazenar, mas custos associados à recuperação.

### S3 Glacier Deep Archive
- **Caso de uso:** Arquivamento de longo prazo com recuperação muito esporádica.
- **Recuperação:** Em até 12 horas.
- **Custos:** O mais barato entre todas as classes de armazenamento.

### S3 Intelligent-Tiering
- **Caso de uso:** Para dados com padrões de acesso desconhecidos ou variáveis. O S3 move automaticamente os objetos entre os níveis mais caros e mais baratos com base nos padrões de uso.
- **Custos:** Taxa mensal adicional por objeto, mas pode economizar dinheiro ao longo do tempo.

## 4. Controle de Acesso

Amazon S3 fornece diversas maneiras de controlar o acesso aos seus buckets e objetos:

### 1. **Bucket Policies:**
   - Políticas baseadas em JSON que definem permissões no nível do bucket.
   - Você pode conceder permissões a usuários, contas da AWS ou serviços (como o CloudFront).

### 2. **Access Control Lists (ACLs):**
   - Permitem definir permissões para objetos ou buckets individuais.
   - Mais simples que as bucket policies, mas também menos flexíveis.

### 3. **AWS Identity and Access Management (IAM):**
   - Usa as políticas do IAM para controlar o acesso de usuários e grupos aos recursos do S3.
   - Permite uma administração centralizada de permissões.

### 4. **S3 Block Public Access:**
   - Um recurso para bloquear automaticamente o acesso público a buckets e objetos.
   - Importante para prevenir a exposição acidental de dados.

## 5. Versionamento (Versioning)

O S3 suporta versionamento, que permite que você mantenha várias versões de um objeto no mesmo bucket. Isso é útil para recuperar versões antigas ou excluir permanentemente dados sensíveis.

### Benefícios:
- Proteção contra exclusão acidental.
- Facilidade na restauração de versões anteriores de arquivos.

## 6. Transferência de Dados

### Transfer Acceleration
O **S3 Transfer Acceleration** usa a rede global de borda do Amazon CloudFront para acelerar o upload de objetos para o S3. É especialmente útil para transferir grandes quantidades de dados entre regiões.

### Multipart Upload
O **Multipart Upload** permite o upload de grandes objetos em partes menores e as une no final. Se uma parte falhar, somente aquela parte precisa ser retransmitida, economizando tempo.

## 7. Segurança no S3

### 1. **Criptografia em repouso (Server-Side Encryption):**
   - S3 pode criptografar automaticamente os dados no momento em que eles são armazenados, usando chaves gerenciadas pela AWS (SSE-S3) ou chaves gerenciadas pelo cliente (SSE-C).

### 2. **Criptografia do lado do cliente (Client-Side Encryption):**
   - O cliente pode criptografar os dados antes de enviá-los para o S3 e armazenar a chave localmente.

### 3. **Controle de Acesso (IAM, ACLs e Políticas de Bucket):**
   - Controla quem pode acessar os dados.

### 4. **Logs de Acesso:**
   - É possível habilitar logs detalhados de acesso a buckets e objetos.

## 8. Replicação

### Replicação entre Regiões (Cross-Region Replication - CRR)
Permite replicar automaticamente objetos de um bucket em uma região da AWS para outro bucket em uma região diferente. Isso é útil para:
- Garantir durabilidade e recuperação de desastres.
- Melhorar a latência de leitura ao disponibilizar os dados mais próximos dos usuários finais.

### Replicação dentro da mesma Região (Same-Region Replication - SRR)
Replicação de dados dentro da mesma região da AWS para criar backups ou separar ambientes de desenvolvimento e produção.

## 9. Custos do S3

O modelo de preços do Amazon S3 é baseado nos seguintes fatores:

1. **Armazenamento:** Custo por GB por mês.
2. **Solicitações e recuperação de dados:** Custos para GET, PUT, COPY e LIST, além da taxa para recuperação de dados em classes como Glacier.
3. **Transferência de dados:** A transferência de dados para fora da AWS é cobrada com base na quantidade de dados movidos.
4. **Replicação:** Custos adicionais se você usar CRR ou SRR.

---

## Conclusão

O Amazon S3 é um serviço de armazenamento extremamente versátil e eficiente, capaz de atender a uma ampla variedade de necessidades de armazenamento, desde armazenamento frequente até arquivamento de longo prazo. Entender as classes de armazenamento, controle de acesso, e as opções de segurança é essencial para utilizar o S3 de forma otimizada e segura no seu ambiente AWS.
