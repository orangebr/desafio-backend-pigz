## estagio-pigz
Desafio para estágio como desenvolvedor back-end na Pigz. 

## Regras básicas
1. Você deverá subir este desafio em um repositório público no seu github pessoal.
2. Caso não consiga concluir todos os passos, não se preocupe, nos envie mesmo assim o que você fez para que possamos avaliar.

## O Desafio

Vamos lá:
1. Criar as entidades `Client` e `Phone`
2. A relação entre as entidades será: um *client* pode ter vários *phones*

3. Nas entidades devem conter pelo menos os seguintes campos:
- Na entidade Client deverá conter o campo *name* e *doc*
- Na entidade Phone deverá conter o campo *number*

4 Agora você deverá criar quatro endpoints:

- Deverá conter um endpoint para salvar um novo registro de cliente

```http
POST /api/client
Content-Type: application/json
{
    "name": "Fulano da Silva",
    "doc": "11111111111"
}
```

- Crie um endpoint para salvar um novo registro de telefone para um cliente já cadastrado

```http
POST /api/...?
Content-Type: application/json
{
    "number": "95999999999"
}
```

- Deverá retornar em json todos os clientes cadastrado com seus dados, por exemplo:

```http
GET /api/clients
Content-Type: application/json
{
    "clients": [    
        {
            "id": 1,
            "name": "Fulano da Silva",
            "doc": "11111111111",
            "phones": [
                {
                    "id": 1,
                    "number": "95999999990"
                },
                {
                    "id": 2,
                    "number": "95999999991"
                }
            ],
        },
        {
            "id": 2,
            "name": "João da Silva",
            "doc": "22222222222",
            "phones": [
                {
                    "id": 3,
                    "number": "95999999992"
                },
                {
                    "id": 4,
                    "number": "95999999994"
                }
            ]
        }
    ]
}
```

- Deverá retornar em json o cliente passado no parâmetro id, por exemplo:

```http
GET /api/client/{id}
Content-Type: application/json
{
    "id": 1,
    "name": "Fulano da Silva",
    "doc": "11111111111",
    "phones": [
        {
            "id": 1,
            "number": "95999999990"
        },
        {
            "id": 2,
            "number": "95999999991"
        }
    ]
}
```
