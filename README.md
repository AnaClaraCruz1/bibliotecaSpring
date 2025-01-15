# Catálogo de Livros

Este é um projeto de um catálogo de livros que utiliza Java, Spring Boot e PostgreSQL para consumir a API Gutendex e armazenar informações relevantes sobre livros em um banco de dados relacional. O objetivo é praticar o consumo de APIs e a persistência de dados, bem como fornecer uma interface textual para interação.

---

## Tecnologias Utilizadas

- **Linguagem de programação**: Java 17
- **Framework**: Spring Boot
- **Banco de dados**: PostgreSQL
- **Dependências**:
  - Spring Data JPA
  - Driver PostgreSQL
  - RestTemplate
  - JSON (org.json)

---

## Funcionalidades

1. **Buscar livro pelo título**
   - Consulta diretamente a API Gutendex e armazena o livro no banco de dados.
   - Dados armazenados: título, autor(es), idioma e número de downloads.

2. **Listar livros registrados**
   - Retorna todos os livros registrados no banco de dados.

3. **Listar autores registrados**
   - Retorna todos os autores registrados no banco de dados.

4. **Listar autores em determinado ano**
   - Filtra autores que estavam vivos em um ano específico.

5. **Listar livros por idioma**
   - Filtra livros registrados por idioma.

---

## Estrutura do Projeto

```
BookCatalog/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   ├── com/example/bookcatalog/
│   │   │   │   ├── BookCatalogApplication.java
│   │   │   │   ├── controller/
│   │   │   │   │   ├── BookController.java
│   │   │   │   ├── model/
│   │   │   │   │   ├── Book.java
│   │   │   │   ├── repository/
│   │   │   │   │   ├── BookRepository.java
│   │   │   │   ├── service/
│   │   │   │   │   ├── BookService.java
│   │   ├── resources/
│   │   │   ├── application.properties
│   ├── test/
│       ├── java/
│           ├── com/example/bookcatalog/
│               ├── BookCatalogApplicationTests.java
```

---

## Configurações do Projeto

### 1. Configuração do Banco de Dados

Certifique-se de que o PostgreSQL esteja instalado e configurado. Crie um banco de dados chamado `bookcatalog`.

Configure as credenciais no arquivo `application.properties`:

```
spring.datasource.url=jdbc:postgresql://localhost:5432/bookcatalog
spring.datasource.username=seu_usuario
spring.datasource.password=sua_senha
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```

### 2. Dependências Necessárias

As dependências do projeto estão configuradas no arquivo `pom.xml` (Maven):

- **Spring Boot Starter Web**
- **Spring Boot Starter Data JPA**
- **PostgreSQL Driver**
- **JSON (org.json)**

### 3. Execução do Projeto

1. Clone este repositório:
   ```
   git clone <URL_DO_REPOSITORIO>
   ```

2. Importe o projeto em sua IDE (recomenda-se o IntelliJ IDEA).

3. Execute o arquivo `BookCatalogApplication.java`.

4. O projeto estará acessível no endpoint: `http://localhost:8080/books`.

---

## Exemplos de Uso

### 1. Buscar Livro pelo Título
- **Endpoint**: `GET /books/search?title=<título>`
- Exemplo:
  ```
  GET /books/search?title=Dom%20Casmurro
  ```

### 2. Listar Livros Registrados
- **Endpoint**: `GET /books`
- Exemplo de Resposta:
  ```json
  [
    {
      "id": 1,
      "title": "Dom Casmurro",
      "author": "Machado de Assis",
      "language": "pt",
      "downloads": 1023
    }
  ]
  ```

### 3. Listar Autores Registrados
- **Endpoint**: `GET /books/authors`

### 4. Listar Livros por Idioma
- **Endpoint**: `GET /books/language?language=<código-do-idioma>`
- Exemplo:
  ```
  GET /books/language?language=pt
  ```

---

## Possíveis Melhorias

- Adicionar paginação e ordenação nos endpoints.
- Criar estatísticas (ex.: top 10 livros mais baixados).
- Implementar autenticação e autorização.
- Expandir os filtros e consultas de livros e autores.

---

## Licença

Este projeto está sob a licença MIT. Consulte o arquivo `LICENSE` para mais detalhes.


