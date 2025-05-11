# Schedule Events API

## Visão Geral

O **Schedule Events** é um projeto que simula uma API para um sistema de agendamento de eventos. Ele foi desenvolvido com o intuito principal de aplicar e praticar os conceitos da Clean Architecture, buscando uma estrutura de software modular, testável e de fácil manutenção.

## Objetivo Principal

O foco deste projeto é o aprendizado e a demonstração prática dos princípios da **Clean Architecture** em um contexto de desenvolvimento de API com tecnologias modernas.

## Tecnologias Utilizadas

O projeto foi construído utilizando as seguintes tecnologias e ferramentas:

* **Linguagem:** Java 21
* **Framework:** Spring Boot  3.4.5)
* **Banco de Dados:** PostgreSQL
* **Migrations:** Flyway
* **Containerização:** Docker e Docker Compose
* **Arquitetura:** Clean Architecture


## Estrutura do Projeto (Clean Architecture)

O projeto segue os princípios da Clean Architecture, dividindo as responsabilidades em camadas distintas:

* **Domain (Domínio):** Contém as entidades, casos de uso e regras de negócio centrais da aplicação. É o coração do sistema e não depende de frameworks ou detalhes de infraestrutura.
* **Application (Aplicação):** Orquestra os casos de uso, atuando como uma ponte entre a camada de domínio e as camadas externas. Define interfaces para as dependências externas (como repositórios).
* **Infrastructure (Infraestrutura):** Contém as implementações concretas das interfaces definidas na camada de aplicação, como acesso a banco de dados (repositórios), frameworks web (controllers), e outros serviços externos.
    * **Adapters/Web:** Controladores REST, DTOs (Data Transfer Objects) para a comunicação HTTP.
    * **Adapters/Persistence:** Implementações dos repositórios utilizando Spring Data JPA, configuração do Flyway.
    * **Configuration:** Configurações do Spring Boot, segurança, etc.

## Endpoints da API (Exemplo)

Aqui você pode listar os principais endpoints da sua API. Por exemplo:

* `POST /events` - Cria um novo evento.
* `GET /events` - Lista todos os eventos.
* `GET /events/{id}` - Busca um evento pelo ID.
* `PUT /events/{id}` - Atualiza um evento existente.
* `DELETE /events/{id}` - Deleta um evento.


