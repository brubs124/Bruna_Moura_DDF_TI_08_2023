# CASE 5

## Criação de tabela para testar o funcionamento de query criada para consultar os usuários que se cadastraram nos últimos 30 dias.

```sql
/* Criei uma tabela para testar o funcionamento da query */

/* Cria a tabela */
CREATE TABLE users_emails (
    /* Define as colunas da tabela */
    id_user INT PRIMARY KEY,
    nome VARCHAR(30),
    data_cadastro DATE
);

/* Aqui serão inseridos os dados na tabela que criei anteriormente.
Cada valor entre parênteses representa um registro na tabela.
Para cada registro, especifiquei valores para as colunas:
"id_user", "nome" e "data_cadastro" */
INSERT INTO users_emails (id_user, nome, data_cadastro)
VALUES
    (1, 'Bruna1', '2023-08-05'),
    (2, 'Bruna2', '2023-08-12'),
    (3, 'Bruna3', '2023-07-25'),
    (4, 'Bruna4', '2023-08-07'),
    (5, 'Bruna5', '2023-07-10');

/* Essa query será usada para selecionar os usuários que se cadastraram nos últimos 30 dias */

/* Seleciona todas as colunas da tabela */
SELECT *

/* Especifica a tabela da qual os dados serão selecionados */
FROM users_emails

/* A cláusula WHERE filtra os resultados com base na data de cadastro */
WHERE data_cadastro >= DATE_SUB(NOW(), INTERVAL 30 DAY);
```
