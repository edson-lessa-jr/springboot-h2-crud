# Exemplo simples de CRUD com Spring Boot + H2

Este projeto demonstra um CRUD básico de **Produto** usando Spring Boot, Spring Data JPA e banco em memória **H2**.

## Requisitos
- Java 17+
- Maven 3.8+

## Como executar
```bash
mvn spring-boot:run
```
A aplicação subirá em: `http://localhost:8080`  
Console do H2: `http://localhost:8080/h2-console`  
JDBC URL: `jdbc:h2:mem:produtosdb` (usuário: `sa`, senha em branco).

## Endpoints
- `GET /produtos` — lista todos
- `GET /produtos/{id}` — obtém por id
- `POST /produtos` — cria (JSON no corpo)
- `PUT /produtos/{id}` — atualiza (JSON no corpo)
- `DELETE /produtos/{id}` — remove

### Exemplos de cURL
```bash
# Listar
curl -s http://localhost:8080/produtos

# Buscar por id
curl -s http://localhost:8080/produtos/1

# Criar
curl -s -X POST http://localhost:8080/produtos   -H "Content-Type: application/json"   -d '{"nome":"Teclado","preco":199.90}'

# Atualizar
curl -s -X PUT http://localhost:8080/produtos/1   -H "Content-Type: application/json"   -d '{"nome":"Caderno 120 folhas","preco":21.50}'

# Remover
curl -s -X DELETE http://localhost:8080/produtos/1 -i
```

## Modelo de dados
- `Produto` (id, nome, preco)

Dados iniciais são carregados por `data.sql` para facilitar os testes.
