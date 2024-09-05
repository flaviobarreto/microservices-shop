# Shop Microservices

Este projeto é uma implementação de um shopping online utilizando uma arquitetura de microsserviços em **.NET 6.0**. Ele integra uma série de tecnologias modernas para autenticação, mensageria, roteamento de APIs e documentação, proporcionando uma plataforma robusta, escalável e segura.

## Tecnologias Utilizadas

- **.NET 6.0**: Plataforma de desenvolvimento unificada para a criação de aplicações modernas e de alta performance.
- **ASP.NET Core**: Framework para criação de APIs RESTful com suporte a middlewares, excelente para a construção de microsserviços.
- **Value Object**: Padrão de design para garantir a imutabilidade e consistência de valores no domínio do projeto.
- **OAuth2 & OpenID Connect**: Padrões de autenticação e autorização amplamente usados para garantir segurança em aplicações distribuídas.
- **JWT (JSON Web Tokens)**: Utilizado para autenticação e troca segura de informações entre os microsserviços.
- **Identity Server**: Implementação completa para gerenciar autenticação e autorização com OAuth2 e OpenID Connect.
- **RabbitMQ**: Sistema de mensageria utilizado para comunicação assíncrona entre os microsserviços, garantindo eficiência e escalabilidade.
- **API Gateway (Ocelot)**: Usado para roteamento de APIs, controle de acesso e agregação de microsserviços.
- **Swagger (OpenAPI)**: Ferramenta para documentação e exploração de APIs de forma fácil e interativa.

## Arquitetura do Projeto

Este projeto está organizado em uma arquitetura de microsserviços para garantir escalabilidade, manutenibilidade e independência dos serviços. A comunicação entre os microsserviços é feita de forma assíncrona através do **RabbitMQ** e sincronamente via HTTP quando necessário.

### Principais Microsserviços:

1. **Serviço de Autenticação e Autorização**: Implementado com **Identity Server** utilizando **OAuth2**, **OpenID Connect** e **JWT**, responsável por gerenciar autenticação e tokens de acesso.
2. **Serviço de Produtos**: Gerencia o catálogo de produtos disponíveis no shopping, incluindo detalhes de preços, descrições e categorias.
3. **Serviço de Carrinho de Compras**: Responsável por gerenciar os itens adicionados ao carrinho pelos usuários.
4. **Serviço de Pagamento**: Integração com provedores de pagamento para processar transações e gerar faturas.
5. **Serviço de Pedidos**: Gerencia a criação, atualização e histórico dos pedidos feitos pelos usuários.
6. **API Gateway (Ocelot)**: Centraliza o acesso aos microsserviços, fornecendo um único ponto de entrada para o cliente e agregando as chamadas de API.

### Mensageria

A comunicação assíncrona entre os microsserviços é feita utilizando **RabbitMQ**, garantindo a entrega confiável de mensagens entre os serviços, como eventos de criação de pedidos, notificações de pagamento e atualizações de estoque.

### Segurança

A segurança é garantida através de **OAuth2** e **OpenID Connect** com **Identity Server**, e todos os microsserviços são protegidos por **JWT** para assegurar que apenas usuários autenticados possam acessar os recursos. A comunicação entre serviços e clientes é criptografada.

## Setup do Projeto

### Pré-requisitos

- [.NET 6.0 SDK](https://dotnet.microsoft.com/download)
- [RabbitMQ](https://www.rabbitmq.com/download.html)
- [Docker](https://www.docker.com/) (opcional, para facilitar a execução dos serviços)
- [IdentityServer](https://identityserver4.readthedocs.io/en/latest/) (para autenticação e autorização)

### Instalação

1. Clone o repositório:
    ```bash
    git clone https://github.com/seu-usuario/markebank.git
    ```

2. Navegue até o diretório do projeto:
    ```bash
    cd markebank
    ```

3. Configure as variáveis de ambiente necessárias no arquivo `.env` para o RabbitMQ, Identity Server e outros serviços.

4. Compile o projeto:
    ```bash
    dotnet build
    ```

5. Inicie o projeto:
    ```bash
    dotnet run
    ```

### Documentação da API

Acesse a documentação gerada automaticamente pelo Swagger em `http://localhost:5000/swagger` após iniciar o projeto.

## Contribuições

Contribuições são bem-vindas! Para isso, siga os seguintes passos:

1. Crie um fork do repositório.
2. Crie uma branch para a nova feature: `git checkout -b feature/nova-feature`.
3. Faça commit das alterações: `git commit -m 'Adiciona nova feature'`.
4. Envie para o seu fork: `git push origin feature/nova-feature`.
5. Crie um Pull Request para revisão.

## Licença

Este projeto está licenciado sob a licença MIT. Veja o arquivo [LICENSE](./LICENSE) para mais detalhes.
