**AWS SQS** é um serviço de fila que permite desacoplar e escalar componentes de sistemas distribuídos. É ideal para transmitir mensagens entre diferentes serviços de forma assíncrona.

- **Tipos de fila**:
  - **Standard Queue**: Garante entrega de mensagens com alta taxa de transferência, mas não garante ordem e pode haver mensagens duplicadas.
  - **FIFO Queue (First-In-First-Out)**: Garante a ordem e entrega única de mensagens, com menor taxa de transferência comparada à Standard Queue.

- **Características**:
  - Totalmente gerenciado, escalável e pode armazenar mensagens por até 14 dias.
  - Mensagens podem ter até 256 KB de tamanho.
  - Permite que diferentes serviços ou componentes se comuniquem de forma assíncrona.

- **Casos de uso**:
  - Processamento de pedidos de e-commerce.
  - Desacoplar microsserviços em uma arquitetura distribuída.