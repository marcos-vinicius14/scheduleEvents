# Schedule Events API

## Visão Geral

O **Schedule Events** é um projeto que simula uma API para um sistema de agendamento de eventos. Ele foi desenvolvido com o intuito principal de aplicar e praticar os conceitos da Clean Architecture, buscando uma estrutura de software modular, testável e de fácil manutenção.

## Objetivo Principal

O foco deste projeto é o aprendizado e a demonstração prática dos princípios da **Clean Architecture** em um contexto de desenvolvimento de API com tecnologias modernas.

## Tecnologias Utilizadas

O projeto foi construído utilizando as seguintes tecnologias e ferramentas:

* **Linguagem:** Java (Versão específica, ex: 17)
* **Framework:** Spring Boot (Versão específica, ex: 3.x.x)
* **Banco de Dados:** PostgreSQL
* **Migrations:** Flyway
* **Containerização:** Docker e Docker Compose
* **Arquitetura:** Clean Architecture

## Pré-requisitos

Antes de iniciar, certifique-se de ter as seguintes ferramentas instaladas em seu ambiente de desenvolvimento:

* Java JDK (Versão correspondente à do projeto, ex: 17 ou superior)
* Maven ou Gradle (Dependendo do gerenciador de dependências do projeto)
* Docker
* Docker Compose
* Um cliente SQL de sua preferência para interagir com o Postgres (opcional, ex: DBeaver, pgAdmin)

## Como Executar o Projeto

1.  **Clone o Repositório:**
    ```bash
    git clone <URL_DO_SEU_REPOSITORIO>
    cd schedule-events
    ```

2.  **Configuração do Banco de Dados (via Docker Compose):**
    O projeto utiliza Docker Compose para facilitar a configuração do ambiente, incluindo o banco de dados PostgreSQL e a execução das migrations com Flyway.

    Na raiz do projeto, execute:
    ```bash
    docker-compose up -d
    ```
    Este comando irá baixar a imagem do Postgres (se ainda não existir localmente), criar um container para o banco de dados e aplicar as migrations definidas com o Flyway.

3.  **Execute a Aplicação Spring Boot:**

    * **Via IDE:** Importe o projeto em sua IDE de preferência (IntelliJ IDEA, Eclipse, VS Code com extensões Java) e execute a classe principal da aplicação (geralmente anotada com `@SpringBootApplication`).
    * **Via Linha de Comando (Maven):**
        ```bash
        ./mvnw spring-boot:run
        ```
    * **Via Linha de Comando (Gradle):**
        ```bash
        ./gradlew bootRun
        ```

4.  **Acesso à API:**
    Após a inicialização bem-sucedida, a API estará disponível em `http://localhost:8080` (ou a porta configurada no `application.properties`/`application.yml`).

    Você pode utilizar ferramentas como Postman, Insomnia ou `curl` para interagir com os endpoints da API.

## Estrutura do Projeto (Clean Architecture)

O projeto segue os princípios da Clean Architecture, dividindo as responsabilidades em camadas distintas:

* **Domain (Domínio):** Contém as entidades, casos de uso e regras de negócio centrais da aplicação. É o coração do sistema e não depende de frameworks ou detalhes de infraestrutura.
* **Application (Aplicação):** Orquestra os casos de uso, atuando como uma ponte entre a camada de domínio e as camadas externas. Define interfaces para as dependências externas (como repositórios).
* **Infrastructure (Infraestrutura):** Contém as implementações concretas das interfaces definidas na camada de aplicação, como acesso a banco de dados (repositórios), frameworks web (controllers), e outros serviços externos.
    * **Adapters/Web:** Controladores REST, DTOs (Data Transfer Objects) para a comunicação HTTP.
    * **Adapters/Persistence:** Implementações dos repositórios utilizando Spring Data JPA, configuração do Flyway.
    * **Configuration:** Configurações do Spring Boot, segurança, etc.

*(Esta é uma sugestão de estrutura. Adapte conforme a sua implementação específica da Clean Architecture.)*

## Endpoints da API (Exemplo)

Aqui você pode listar os principais endpoints da sua API. Por exemplo:

* `POST /events` - Cria um novo evento.
* `GET /events` - Lista todos os eventos.
* `GET /events/{id}` - Busca um evento pelo ID.
* `PUT /events/{id}` - Atualiza um evento existente.
* `DELETE /events/{id}` - Deleta um evento.

*(Lembre-se de documentar os corpos das requisições e respostas esperadas, talvez utilizando Swagger/OpenAPI).*

a estrutura de pastas e endpoints conforme o seu projeto real.*
