## O que é o AWS Config?

O **AWS Config** é um serviço de governança que permite monitorar e registrar alterações de configuração em seus recursos AWS, além de avaliar automaticamente se esses recursos atendem a políticas de conformidade e governança. Com o AWS Config, você pode verificar a conformidade com requisitos internos e regulatórios e responder a mudanças de configuração que possam impactar sua segurança ou eficiência operacional.

## Principais Funcionalidades

1. **Rastreamento de Mudanças de Configuração**:
    
    - O AWS Config monitora e grava continuamente mudanças na configuração dos recursos AWS, como alterações em instâncias [[AWS EC2]], buckets [[Guia AWS - Amazon S3 (Simple Storage Service)|S3]], [[AWS VPC]], etc.
    - Cria uma trilha de auditoria completa, permitindo que você visualize e analise mudanças de configuração ao longo do tempo.
2. **Snapshots de Configuração**:
    
    - Periodicamente, o AWS Config captura snapshots do estado de seus recursos, permitindo uma visão detalhada da configuração em um momento específico.
3. **Regras de Conformidade (Config Rules)**:
    
    - Permite definir **regras de conformidade** personalizadas ou usar regras pré-definidas para avaliar se os recursos atendem a requisitos específicos.
    - Avalia automaticamente os recursos e alerta quando detecta não conformidade.
4. **Alerta de Mudanças e Não Conformidade**:
    
    - Pode ser configurado para enviar notificações via SNS ou para invocar uma função Lambda em resposta a alterações ou não conformidade com regras.
5. **Histórico Completo e Detalhado**:
    
    - Oferece um histórico detalhado de cada alteração nos recursos, permitindo rastrear alterações até os detalhes específicos, como tipo de alteração e valores antigos e novos.

## Casos de Uso Comuns

1. **Auditoria e Governança**:
    
    - Útil para auditorias e certificações de conformidade (como SOC 2, PCI DSS e HIPAA) ao fornecer um histórico de mudanças detalhado e verificações de conformidade em tempo real.
2. **Gerenciamento de Conformidade**:
    
    - Avalia continuamente se os recursos estão em conformidade com políticas internas, como requisitos de criptografia, tags obrigatórias ou configurações de rede seguras.
3. **Resposta a Incidentes**:
    
    - Quando ocorre uma mudança inesperada ou potencialmente prejudicial, o AWS Config permite a detecção rápida e acionamento de ações de correção, como execução de funções Lambda para restaurar a configuração.

## Integração com Outros Serviços AWS

- **[[AWS CloudTrail]]**: O AWS Config trabalha com o AWS CloudTrail para fornecer um histórico completo de eventos e mudanças nos recursos da AWS.
- **[[AWS Lambda]]**: Integre o AWS Config com Lambda para executar ações personalizadas automaticamente em resposta a eventos de não conformidade.
- **[[AWS SNS]]**: Configure alertas e notificações via SNS para ser informado sobre mudanças de configuração ou violações de conformidade.
- **AWS Organizations**: Monitore a conformidade de múltiplas contas em uma organização centralizada.

## Exemplo de Configuração de Regra

Um exemplo de regra do AWS Config é exigir que todos os buckets S3 tenham criptografia habilitada. Você pode definir uma regra personalizada que verifica a configuração de criptografia de cada bucket e alerta caso a regra não seja atendida.

## Resumo

O AWS Config é essencial para empresas que precisam monitorar a conformidade de recursos AWS e manter um histórico completo de alterações. Com regras de conformidade personalizáveis, ele simplifica o monitoramento de configuração e auxilia em auditorias e governança.