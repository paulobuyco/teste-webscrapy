# Teste para Web Scrapy

Este teste é apresentado aos candidatos as vagas de desenvolvimento back-end, o objetivo é avaliar suas habilidades de desenvolvimento e boas práticas.

**Desafio:**

O objetivo desse trabalho é criar um servidor local que realiza scrapy. Nesse servidor tem apenas um método que é o GET e recebe-se o parâmetro com código do ativo.

```
localhost:8080/{ativo}
```

Ex.:

```
localhost:8080/VALE3
```

O servido retorna um *json* com as seguintes informações:
```
{
    "statusCode": 200,
    "body": {
        "name": "VALE ON NM",
        "type": "ON NM",
        "sector": "Mineração",
        "subsector": "Minerais Metálicos",
        "marketvalue": {
            "today": 599577000000,
            "min": 239756403900,
            "max": 627372278400
        },
        "margin":{
            "gross": 0.575,
            "ebit": 0.563,
            "net": 0.221
        },
        "results": {
            "year":{
                "revenue": 246579000000,
                "ebit": 138910000000,
                "net": 56292600000
            },
            "recent":{
                "revenue": 69301200000,
                "ebit": 43326600000,
                "net": 30564200000
            }
        }
    }
}
```

Para resolver, realize scrapy no site http://fundamentus.com.br

Pontos extra:

No corpo de resposta traga também os dados do balanço patrimonial:

 - Ativo
 - Disponibilidades
 - Ativo Circulante
 - Dívida Bruta
 - Patrimônio Líquido

 E se conseguir, trazer os proventos desses ativos organizados por ano. Ex:

 ```
 {
     "earnings": {
         "2021": 4.2616
     }
 }
 ```

 ## Explicação

 ### Calculando o valor da empresa

 Para calcular o valor máximo e o valor mínimo da empresa, deve-se pegar o Valor da Ação mínimo em 52 semanas e multiplicar pelo Número de ações, da mesma forma o valor máximo.

### Servidor em Python

Para criar um servidor em python recomenda-se o uso do Flask, que facilita a construção.
