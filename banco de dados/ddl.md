# Data Definition Language (Linguagem de Definição de Dados) - DDL

O subconjunto da linguagem SQL que trata dos objetos dos bancos de dados,
especialmente a criação (*CREATE*), alteração (*ALTER*) e remoção (*DROP*)
de tabelas e bases de dados, é chamado de DDL (*Data Definition Language*).

> O texto apresenta os comandos do SGBD [MariaDB](https://mariadb.com)

## CREATE TABLE

Cria uma tabela no banco de dados selecionado.

### **[Sintaxe básica](https://mariadb.com/kb/en/create-table/)**

```
CREATE [TEMPORARY] TABLE [IF NOT EXISTS] tbl_name
    (create_definition,...) [table_options    ]... [partition_options]
```

A definição de colunas e restrições (*create_definition*) tem a seguinte sintaxe básica:

```
nome_da_coluna  tipo_de_dado  restrição
```

```
CONSTRAINT nome_da_restricao RESTRIÇÃO(nome_da_coluna)
```

### Exemplo

```
CREATE TABLE pessoa (
         id            INT AUTO_INCREMENT,
         nome          VARCHAR(30),
         sobrenome     VARCHAR(30),
         cpf           CHAR(11),
         CONSTRAINT pk_pessoa      PRIMARY KEY(id),
         CONSTRAINT uq_pessoa_cpf  UNIQUE(cpf)
);
```
## ALTER TABLE

Altera a especificação da tabela, permitindo adicionar, remover e modificar
colunas, restrições, índices, dentre outras coisas.

### **[Sintaxe básica](https://mariadb.com/kb/en/alter-table/)**

```
ALTER TABLE [IF EXISTS] tbl_name
  alter_specification
```

A especificação de alteração (*alter_specification*) é bastante extensa, mas a
sintaxe básica das operações mais comuns é a seguinte:

```
[ADD|MODIFY|DROP] [COLUMN|CONSTRAINT] [col_name|constraint_name]
create_definition
```

### Exemplo

```
# Restrição de domínio de CPF: 11 dígitos
ALTER TABLE pessoa ADD CONSTRAINT IF NOT EXISTS chk_cpf CHECK(cpf REGEXP '[0-9]{11}');
```

## DROP TABLE

Remove uma tabela do banco de dados.

### [Sintaxe básica](https://mariadb.com/kb/en/drop-table/)

```
DROP [TEMPORARY] TABLE [IF EXISTS] [/*COMMENT TO SAVE*/]
    tbl_name [, tbl_name] ...
    [RESTRICT | CASCADE]
```

O comentário *COMMENT TO SAVE* é armazenado no registro (*log*) do banco de dados.

### Exemplo

```
DROP TABLE IF EXISTS [/*Tabela Obsoleta*/] pessoa
``` 


