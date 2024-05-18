# Microsserviço de Clientes - Coleção Postman

## Visão Geral
Esta coleção do Postman foi criada para facilitar o desenvolvimento, teste e integração com o microsserviço de clientes. O serviço gerencia clientes e seus endereços, permitindo operações como criação, consulta, e atualização de registros.

## Operações Disponíveis

### 1. Criar Cliente
- **Método e Endpoint:** POST `http://localhost:8080/api/v1/clientes`
- **Descrição:** Registra um novo cliente no sistema com informações detalhadas e múltiplos endereços.
- **Corpo da Requisição:**
  
  ```json
  {
    "nome": "João Silva",
    "email": "joaosilva@example.com",
    "telefone": "(11) 9999-8888",
    "cpf": "76252398454",
    "enderecos": [
      {
        "rua": "Rua das Flores, 123",
        "cidade": "São Paulo",
        "estado": "SP",
        "cep": "01002-001"
      },
      {
        "rua": "Avenida Brasil, 456",
        "cidade": "Rio de Janeiro",
        "estado": "RJ",
        "cep": "22081-000"
      }
    ]
  }

### 2. Consultar por CPF
- **Método e Endpoint:** GET http://localhost:8080/api/v1/clientes/76252398454
- **Descrição:** Retorna os detalhes de um cliente específico, identificado pelo CPF.

### 3. Criar novo endereço para cliente
- **Método e Endpoint:** POST http://localhost:8080/api/v1/enderecos
- **Descrição:** Adiciona um novo endereço para um cliente existente.
- **Corpo da Requisição:**
```json
{
  "rua": "Rua Sanazar Mardiros, 508 - Presidente Altino",
  "cidade": "Osasco",
  "estado": "SP",
  "cep": "06210-010",
  "cpf_cliente": "76252398454"
}
```

### 4. Atualizar endereço para cliente
- **Método e Endpoint:** PATCH http://localhost:8080/api/v1/enderecos/3
- **Descrição:** Atualiza os detalhes de um endereço específico de um cliente.
- **Corpo da Requisição:**

```json
{
  "rua": "Rua Sanazar, 510 - Presidente Altino",
  "cidade": "Osasco",
  "estado": "SP",
  "cep": "06210-010",
  "cpf_cliente": "76252398454"
}
```

## Uso da Coleção
- Importe a coleção JSON no Postman.
- Certifique-se de que o microsserviço de clientes esteja rodando localmente ou em um ambiente acessível.
- Execute as requisições conforme necessário para testar ou integrar com o microsserviço de clientes.
