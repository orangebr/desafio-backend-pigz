# estagio-pigz
Desafio para estágio como desenvolvedor back-end na Pigz. 

# Regras básicas
1. Você deverá subir este desafio em um repositório público no seu github pessoal.
2. Você tem até quarta (dia 24) para nos enviar o link do seu repositório.
3. Caso não consiga concluir todos os passos, não se preocupe, nos envie mesmo assim o que você fez para que possamos avaliar.

# O Desafio

Vamos lá:
1) Criar as seguintes entidades
1.1) Cliente
1.2) Telefone

2) A relação entre as entidades será:
2.1) Um cliente pode ter vários telefones

3) Nas entidades devem conter pelo menos os seguintes campos:
3.1) Na entidade Cliente deverá conter o campo "nome" e "cpf"
3.2) Na entidade Telefone deverá conter o campo "ddd" e "número"

4) Agora você deverá criar um endpoint a seguinte estrutura:
4.1) Deverá retornar em json todos os clientes cadastrado com seus dados, por exemplo:

```http
POST /api/clients
Content-Type: application/json
{
    "clients": [    
        {
            "id": 1,
            "nome": "Fulano da Silva",
            "cpf": "11111111111",
            "telefone": [
                {
                    "id": 1,
                    "ddd": "95",
                    "numero": "999999990"
                },
                {
                    "id": 2,
                    "ddd": "95",
                    "numero": "999999991"
                }
            ],
        },
        {
            "id": 2,
            "nome": "João da Silva",
            "cpf": "22222222222",
            "telefone": [
                {
                    "id": 3,
                    "ddd": "95",
                    "numero": "999999992"
                },
                {
                    "id": 4,
                    "ddd": "95",
                    "numero": "999999994"
                }
            ]
        }
    ]
}
```

4.2) Deverá retornar em json o cliente passado no parâmetro id, por exemplo:

```http
GET /api/client/{id}
Content-Type: application/json
{
    "id": 1,
    "nome": "Fulano da Silva",
    "cpf": "11111111111",
    "telefone": [
        {
            "id": 1,
            "ddd": "95",
            "numero": "999999990"
        },
        {
            "id": 2,
            "ddd": "95",
            "numero": "999999991"
        }
    ]
}
```
