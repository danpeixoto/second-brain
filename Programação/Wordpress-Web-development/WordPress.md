---
tags:
  - tecnologia
  - wordpress
---

## O Que é WordPress 
O WordPress é um sistema de gerenciamento de conteúdo (CMS) de código aberto que permite criar e gerenciar facilmente um site ou blog. Inicialmente lançado em 2003 por Matt Mullenweg e Mike Little, o WordPress cresceu para se tornar uma das plataformas de publicação online mais populares do mundo, alimentando mais de 40% de todos os sites na internet.

## Para que é usado o WordPress?

O WordPress é usado para uma ampla variedade de sites, incluindo:

- Blogs pessoais e profissionais
- Sites de empresas e portfólios
- Lojas online (usando o plugin WooCommerce)
- Fóruns e redes sociais
- Sites de notícias e publicações online

Sua flexibilidade e facilidade de uso tornam o WordPress uma excelente escolha tanto para iniciantes quanto para desenvolvedores web experientes.

## Como instalar o WordPress

A instalação do WordPress pode ser feita tanto localmente, em seu próprio computador, quanto em um servidor remoto. Abaixo estão os passos básicos para ambos os métodos. 

Para conseguir rodá-lo é necessário que o computador possua um servidor web, comumente sendo o apache.

### Instalação Local

1. **Baixe um software de servidor local**: Para rodar o WordPress localmente, você precisará de um software como XAMPP, MAMP ou WAMP. Baixe e instale o software escolhido.
2. **Baixe o WordPress**: Acesse o site oficial do WordPress ([https://wordpress.org](https://wordpress.org)) e baixe a versão mais recente.
3. **Configure o ambiente**: Descompacte o arquivo do WordPress no diretório de documentos do seu servidor local (geralmente `htdocs` ou `www`).
4. **Crie um banco de dados**: Use o phpMyAdmin (incluso na maioria dos softwares de servidor local) para criar um novo banco de dados para o seu site WordPress.
5. **Inicie a instalação**: Abra seu navegador e acesse `localhost/nome_do_seu_site`. Siga o assistente de instalação do WordPress, inserindo os detalhes do banco de dados criado.

### Instalação Remota

1. **Escolha um provedor de hospedagem**: Escolha um provedor de hospedagem que ofereça suporte ao WordPress. Muitos deles oferecem instalação com um clique para o WordPress.
2. **Configure seu domínio e hospedagem**: Compre um domínio e configure sua hospedagem seguindo as instruções do provedor.
3. **Instale o WordPress**: Use o painel de controle do provedor de hospedagem para instalar o WordPress. Isso geralmente envolve apenas alguns cliques e o preenchimento de informações básicas do site.
4. **Acesse o painel do WordPress**: Uma vez instalado, você pode acessar o painel de administração do seu site WordPress digitando `seudomínio.com/wp-admin` no navegador.

## Principais configurações

O WordPress é super customizável, porém há algumas configurações que são essenciais para o seu novo site.

### Habilitar a indexação

É possível desabilitar a indexação do seu site em motores de busca, porém, isso deve estar sempre desligado (só se você realmente não quer que ele apareça). Siga o passo a passo a baixo para habilitar:
1. Entre no admin
2. Procure configurações->leitura
3. Desmarque o checkbox chamado "Visibilidade nos motores de busca"


