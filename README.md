# API: Agenda de Contatos

## Descrição
O `Contato` é um controlador ASP.NET Core responsável por gerenciar operações CRUD (Criar, Ler, Atualizar, Deletar) para a entidade `Contato`. Ele utiliza um banco de dados local chamado **agenda** e interage com uma tabela chamada **contato**.
Você pode fazer todas as operações de um CRUD com seus contatos na agenda.

## Contexto de Banco de Dados

### AgendaContext
- **Descrição:** Classe que representa o contexto do banco de dados.
- **Herança:** `DbContext`
- **Construtor:**
  ```csharp
  public AgendaContext(DbContextOptions<AgendaContext> options) : base(options)
  ```
# Documentação da API: ContatoController

## Propriedades
- **`DbSet<Contato> Contatos`**: Representa a tabela **contato** na base de dados.

## Endpoints

### 1. Criar Contato
- **Método:** `POST /controller`
- **Descrição:** Adiciona um novo contato à base de dados.

#### Request Body
```json
{
  "nome": "string",
  "telefone": "string",
  "ativo": true
}
```

## Endpoints

### 1. Criar Contato
- **Método:** `POST /controller`
- **Descrição:** Adiciona um novo contato à base de dados.

#### Resposta
- **Código:** 201 Created
  - **Descrição:** Contato criado com sucesso.
  - **Body:** Retorna o contato criado.

---

### 2. Obter Contato por ID
- **Método:** `GET /controller/{id}`
- **Descrição:** Retorna um contato pelo seu ID.

#### Parâmetro de Rota
- `id` (int): O ID do contato a ser retornado.

#### Resposta
- **Código:** 200 OK
  - **Descrição:** Contato encontrado.
  - **Body:** Retorna o contato.
- **Código:** 404 Not Found
  - **Descrição:** Contato não encontrado.

---

### 3. Obter Contatos por Nome
- **Método:** `GET /controller/ObterPorNome`
- **Descrição:** Retorna contatos que contêm o nome fornecido.

#### Parâmetro de Query
- `nome` (string): O nome a ser pesquisado nos contatos.

#### Resposta
- **Código:** 200 OK
  - **Descrição:** Lista de contatos encontrados.
  - **Body:** Retorna uma lista de contatos.

---

### 4. Atualizar Contato
- **Método:** `PUT /controller/{id}`
- **Descrição:** Atualiza um contato existente pelo ID.

#### Parâmetro de Rota
- `id` (int): O ID do contato a ser atualizado.

#### Request Body
```json
{
  "nome": "string",
  "telefone": "string",
  "ativo": true
}
```
#### Resposta
- **Código:** 200 OK
  - **Descrição:** Contato atualizado com sucesso.
  - **Body:** Retorna o contato atualizado.
- **Código:** 404 Not Found
  - **Descrição:** Contato não encontrado.

---

### 5. Deletar Contato
- **Método:** `DELETE /controller/{id}`
- **Descrição:** Remove um contato pelo ID.

#### Parâmetro de Rota
- `id` (int): O ID do contato a ser deletado.

#### Resposta
- **Código:** 204 No Content
  - **Descrição:** Contato deletado com sucesso.
- **Código:** 404 Not Found
  - **Descrição:** Contato não encontrado.
