# Data Manipulation Language (Linguagem de Manipulação de Dados) - DML

O subjconjunto da linguagem SQL que permite a manipulação, ou seja, a inserção (*INSERT*), o apagamento (*DELETE*) e a atualização (*UPDATE*) dos registros das tabelas dos bancos de dados, é denominado DML (*Data Manipualtion Language*).

> O texto apresenta os comandos do SGBD [MariaDB](https://mariadb.org/)

## INSERT

Insere um registro na tabela. Para inserir os registros fora da ordem natural dos campos (ordem especificada na criação da tabela) ou deixar alguns campos nulos (ou com valor padrão), é necessário especificar os campos explicitamente.

### **[Sintaxe básica](https://mariadb.com/kb/en/insert/)**

```
INSERT INTO nome_da_tabela [(col, ...)] VALUES (expr)
```

### Exemplos

```
INSERT INTO pessoa
	VALUES ("João", "da Silva", "15925812311"),
	       ("Maria", "Santos", "00598219213");

INSERT INTO pessoa (sobrenome, nome, CPF) 
	VALUES ("da Silva", "João", "15925812311"),
	       ("Santos", "Maria", "00598219213");
```


