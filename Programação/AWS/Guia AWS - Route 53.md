
## O que é o Route 53?

- **Amazon Route 53** é um serviço de **Domain Name System (DNS)** da AWS que facilita a resolução de nomes de domínio para endereços IP. Ele ajuda a conectar solicitações de usuários à infraestrutura executada na AWS, como instâncias **[[AWS EC2|EC2]]**, *endpoints* de *bucket* no **[[Guia AWS - Amazon S3 (Simple Storage Service)|S3]]** (site estático) ou até mesmo servidores fora da AWS, tudo isso orquestrado a partir de **[[Guia AWS - Redes na AWS|rede (VPC)]]** na conta.

## Funcionalidades Principais

1. **Registro de Domínios**:
    
    - Permite registrar e gerenciar nomes de domínio diretamente na AWS.
2. **Roteamento DNS**:
    
    - Traduz nomes de domínio (por exemplo, `example.com`) para endereços IP, permitindo que os usuários acessem seus serviços.
3. **Verificação de Saúde (Health Checks)**:
    
    - O Route 53 pode monitorar a integridade dos recursos da AWS, redirecionando o tráfego para instâncias ou serviços saudáveis em caso de falha.

## Tipos de Políticas de Roteamento

- **Simple Routing**: Atribui um único recurso a um nome de domínio.
- **Weighted Routing**: Distribui o tráfego com base em pesos atribuídos aos diferentes recursos.
- **Latency-Based Routing**: Direciona o tráfego para o recurso com a menor latência para o usuário.
- **Failover Routing**: Redireciona o tráfego para um recurso de backup caso o principal esteja indisponível.
- **Geolocation Routing**: Direciona o tráfego com base na localização geográfica do usuário.
- **Geoproximity Routing**: Controla a distribuição do tráfego com base na proximidade geográfica do usuário ao recurso.
- **Multivalue Answer Routing**: Retorna múltiplos endereços IP em resposta a uma única consulta DNS para balanceamento de carga.

## Características Importantes

- **Alta Disponibilidade e Escalabilidade**: Projetado para ser altamente disponível e escalável.
- **Integrado com outros serviços da AWS**: Pode ser facilmente integrado a outras ofertas da AWS, como EC2, S3 e Elastic Load Balancing.
- **Global**: Pode ser usado para configurar e gerenciar configurações de DNS em uma escala global.

## Tipos de Registros DNS no Route 53

1. **Registro A (Address)**:
    
    - Mapeia um nome de domínio para um endereço IPv4 (por exemplo, `192.0.2.1`).
2. **Registro AAAA (Quad A)**:
    
    - Mapeia um nome de domínio para um endereço IPv6 (por exemplo, `2001:0db8:85a3:0000:0000:8a2e:0370:7334`).
3. **Registro CNAME (Canonical Name)**:
    
    - Mapeia um nome de domínio para outro nome de domínio. Usado quando você quer que vários nomes de domínio apontem para o mesmo destino.
    - Não pode ser usado no domínio raiz, apenas em subdomínios.
4. **Registro MX (Mail Exchange)**:
    
    - Especifica os servidores de e-mail responsáveis por receber e-mails para o nome de domínio.
5. **Registro TXT (Text)**:
    
    - Armazena informações de texto para vários propósitos, como verificação de propriedade de domínio e autenticação de e-mail (SPF, DKIM).
6. **Registro NS (Name Server)**:
    
    - Define quais servidores de nomes têm autoridade sobre a zona DNS de um domínio. É usado para delegar um domínio para outros servidores DNS.
7. **Registro SOA (Start of Authority)**:
    
    - Contém informações sobre a zona DNS, como o servidor DNS principal, o responsável pela zona, e os parâmetros de controle de cache.
8. **Registro PTR (Pointer)**:
    
    - Associa um endereço IP a um nome de domínio, sendo o oposto do registro A ou AAAA. É usado para Reverse DNS Lookups (busca reversa de DNS).
9. **Registro SRV (Service)**:
    
    - Especifica informações sobre serviços disponíveis em um domínio, como o número de porta e o protocolo. Muito utilizado por serviços como SIP e LDAP.
10. **Registro SPF (Sender Policy Framework)**:
    
    - Contém informações sobre quais servidores de e-mail estão autorizados a enviar e-mails em nome do domínio. Embora obsoleto em favor do registro TXT, ainda é suportado por muitos serviços.
11. **Registro NAPTR (Naming Authority Pointer)**:
    
    - Usado em conjunto com registros SRV para oferecer suporte à reescrita dinâmica de endereços DNS, comumente em aplicações VoIP.
12. **Registro CAA (Certificate Authority Authorization)**:
    
    - Indica quais Autoridades de Certificação (CAs) têm permissão para emitir certificados SSL/TLS para o domínio, aumentando a segurança do processo de emissão.