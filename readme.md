# API de Consulta de Capitais

API em Node.js, TypeScript e Express que retorna a capital de um estado brasileiro a partir da sigla (UF).

## Como executar

Pré-requisito: Node.js 18 ou superior.

```bash
npm install
npm run dev
```

O servidor sobe em `http://localhost:3000`.

Para compilar e executar a versão de produção:

```bash
npm run build
npm start
```

## Endpoint

`GET /estados/:sigla`

A sigla não diferencia maiúsculas de minúsculas (`SP`, `sp`, `Sp`).

### Exemplos

Requisição: `GET /estados/SP` → **200 OK**

```json
{ "sigla": "SP", "capital": "São Paulo" }
```

Requisição: `GET /estados/XX` → **404 Not Found**

```json
{ "erro": "Estado não encontrado." }
```

## Testes

| Teste | Entrada | Resultado esperado |
|-------|---------|--------------------|
| 1 | SP | São Paulo |
| 2 | RJ | Rio de Janeiro |
| 3 | MG | Belo Horizonte |
| 4 | BA | Salvador |
| 5 | AM | Manaus |
| 6 | df | Brasília |
| 7 | XX | Erro 404 |

As evidências (prints das requisições e respostas) ficam em `docs/testes`.
