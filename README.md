# FórumHub API

Uma API REST completa para uma plataforma de fórum, onde os usuários podem gerenciar tópicos de discussão. O projeto foi desenvolvido como parte de um desafio e segue as melhores práticas do ecossistema Spring Boot.

### **Sumário**
- [Descrição](#descrição)
- [Status do Projeto](#status-do-projeto)
- [Funcionalidades](#funcionalidades)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Arquitetura](#arquitetura)
- [Como Executar o Projeto](#como-executar-o-projeto)
- [Endpoints da API](#endpoints-da-api)
- [Autores](#autores)

### **Descrição**
Esta é a API backend do FórumHub. Ela foi projetada para ser o coração de uma plataforma de fórum, fornecendo todos os recursos necessários para a gestão de tópicos e usuários. A API é segura e robusta, com autenticação via token JWT e validações de dados.

### **Status do Projeto**
✅ Concluído

### **Funcionalidades**
- **Autenticação de Usuário:** Endpoint de login para autenticação com usuário e senha, retornando um token JWT.
- **CRUD de Tópicos:**
    - Criar (POST) novos tópicos com título, mensagem, autor e curso.
    - Listar (GET) todos os tópicos existentes, com paginação.
    - Detalhar (GET) um tópico específico pelo seu ID.
    - Atualizar (PUT) as informações de um tópico existente.
    - Excluir (DELETE) um tópico pelo seu ID.
- **Validação de Negócio:** Impede a criação de tópicos duplicados (mesmo título e mensagem).
- **Segurança:** Todas as rotas, exceto a de login, exigem autenticação com um token JWT válido.
- **Persistência de Dados:** Utiliza JPA e Hibernate para mapeamento objeto-relacional com um banco de dados MySQL.
- **Migrações de Banco de Dados:** Gerenciamento do esquema do banco de dados com o Flyway.

### **Tecnologias Utilizadas**
- **Linguagem:** Java 17
- **Framework:** Spring Boot 3
- **Controle de Versão:** Git & GitHub
- **Autenticação:** Spring Security & JWT (com `java-jwt`)
- **Banco de Dados:** MySQL
- **Persistência:** Spring Data JPA & Hibernate
- **Migrações:** Flyway
- **Build Tool:** Maven
- **Outros:** Lombok (para reduzir código boilerplate)

### **Arquitetura**
O projeto segue uma arquitetura baseada em camadas (Layered Architecture), com separação clara de responsabilidades:
- **`controller`**: Camada de entrada, responsável por receber as requisições HTTP e retornar as respostas.
- **`domain`**: A camada de negócio, que contém as entidades, repositórios e DTOs.
- **`infra`**: Camada de infraestrutura, onde ficam as configurações de segurança, filtros e serviços de token.

### **Como Executar o Projeto**
1.  **Clone o repositório:**
    ```sh
    git clone (https://github.com/leonardoferrza/forumHub-api)
    ```
2.  **Configurar o Banco de Dados:**
    * Crie um banco de dados MySQL com o nome `forumhub_api`.
    * Edite o arquivo `src/main/resources/application.properties` com suas credenciais de acesso ao MySQL.
3.  **Iniciar a Aplicação:**
    * Rode a classe `ApiApplication.java` na sua IDE. O Flyway executará as migrações automaticamente.
    * Ou use o Maven: `mvn spring-boot:run`

### **Endpoints da API**

A base URL da API é `http://localhost:8080`.

#### **Autenticação**
`POST /login`
- **Descrição:** Autentica um usuário e retorna um token JWT para acesso.
- **Corpo da Requisição:** `JSON`
  ```json
  {
    "login": "seu_login",
    "senha": "sua_senha"
  }
#### Resposta de Sucesso (200 OK): `JSON`
```json
{
  "token": "seu_token_jwt_aqui..."
}
```
### Tópicos (Requer Token JWT)
Para acessar estes endpoints, inclua o token JWT no cabeçalho `Authorization` da requisição:

# Continua...

## 🧑‍💻 Autor

**Leonardo Ferrza**

* LinkedIn: [leonardoferrza](https://www.linkedin.com/in/leonardoferrza)
* GitHub: [leonardoferrza](https://github.com/leonardoferrza)