# Lógica de Primeira Ordem

## Axioma x Teorema

Os **axiomas** são as sentenças que definem a informação factual da base de dados e
permitem acarretar conclusões, que podem ser **teoremas**. Por exemplo:

1. ```∀x,y Irmão(x, y) ⇔ x ≠ y ∧ ∃p Pai(p, x) ∧ Pai(p, y)``` é um axioma.
2. ```∀x,y Irmão(x, y) ⇔ Irmão(y, x)``` é um teorema que pode ser acarretado pelo
axioma 1, porque ```x ≠ y``` é equivalente a ```y ≠ x``` e ```Pai(p,x) ∧ Pai(p,y)``` é
equivalente a ```Pai(p, y) ∧ Pai(p, x)```.

As bases de conhecimento geralmente incluem teoremas porque, apesar de não
serem estritamente necessários, tornam mais eficiente o processo de resposta às
consultas.  

