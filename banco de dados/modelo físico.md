# Modelo Físico

O modelo físico dos bancos de dados define com mais detalhes as informações
presentes no modelo lógico. Por exemplo, especificam-se os tipos e restrições
dos atributos (colunas) da relação (tabela), de acordo com os seus domínios
(conjunto de valores permitidos para um atributo). Desta maneira, o modelo 
físico permite a implementação real do banco de dados e baseia-se em um
determinado SGBD (Sistema Gerenciador de Banco de Dado).

O modelo físico não se limita, porém, a apenas transformar o modelo lógico em
um projeto que possa ser implementado no SGBD. Deve-se levar em conta o
funcionamento real do banco de dados: o seu propósito, a quantidade e a
frequência das atualizações (operações DML), as consultas mais frequentes e
custosas etc. Assim, pode-se construir um modelo físico que tenha bom
desempenho e seja adequado ao uso dos dados.

## Referências Bibliográficas

ELSMARI, R., NAVATHE, S. B. Fundamentals of Database Systems, 7 ed., p. 32-34.
Boston: Pearson, 2016.

MACHADO, F. N. R. Banco de dados - Projeto e implementação, 4 ed., p. 217-229. São
Paulo: Érica, 2020.
