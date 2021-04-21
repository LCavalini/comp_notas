# Classificador Naive Bayes

## Fundamento Teórico

O classificador Naive Bayes é um **classificador linear**, ou seja, combina as entradas de maneira linear. Ele se baseia no **Teorema de Bayes**, que define a probabilidade condicional assim ([Prova do Teorema](https://en.wikipedia.org/wiki/Bayes%27_theorem)):

<img src="https://latex.codecogs.com/gif.latex?P(A|B)&space;=&space;\frac{\frac{}{}P(B|A)P(A)}{P(B)}" title="P(A|B) = \frac{\frac{}{}P(B|A)P(A)}{P(B)}" />

É possível aplicar um classificador Naive Bayes à categorização de documentos considerando duas pressuposições:
1. **Bag of words (saco de palavras):** a ordem das palavras não importa;
2. **Naive Bayes:** as características (palavras individuais) de cada documento são independentes entre si.

Desta maneira, a categoria estimada de um documento pode ser calculada assim:

<img src="https://latex.codecogs.com/gif.latex?c_{NB}&space;=&space;argmax_{c&space;\in&space;C&space;}&space;P(c)\prod_{i&space;\in&space;positions}^{}&space;P(w_{i}|c)" title="c_{NB} = argmax_{c \in C } P(c)\prod_{i \in positions}^{} P(w_{i}|c)" />,

sendo *c* uma determinada categoria, *P(c)* a probabilidade *a priori* da categoria *c* e *P(w<sub>i</sub>|c)* a probabilidade condicional da palavra *w<sub>i</sub>* (cada uma das características do documento) dada a categoria *c*.

Para evitar *underflow* e acelerar o processamento (soma é mais rápido do que multiplicação), convertem-se as probabilidades em seus logaritmos:

<img src="https://latex.codecogs.com/gif.latex?c_{NB}&space;=&space;argmax_{c&space;\in&space;C&space;}&space;logP(c)&space;&plus;&space;\sum_{i&space;\in&space;positions}^{}&space;logP(w_{i}|c)" title="c_{NB} = argmax_{c \in C } logP(c) + \sum_{i \in positions}^{} logP(w_{i}|c)" />

## Treino e Teste

O algoritmo de treino consiste, basicamente, em calcular a probabilidade *a
priori* de uma determinada categoria (por exemplo, número de documentos de uma categoria /
número de documentos) e de uma característica específica (por exemplo,
número de ocorrências de uma palavra + *alpha* / número de ocorrência de todas
as palavras em todos os documentos + *alpha* para cada palavra).

O teste é a busca da categoria de maior probabilidade considerado o conjunto de
características de cada elemento do conjunto de teste.

Uma das formas de lidar com palavras do conjunto de teste que nunca apareceram no
conjunto de treino é simplesmente excluí-las.

Especificação dos algoritmos de treino e teste: https://nlp.stanford.edu/IR-book/html/htmledition/naive-bayes-text-classification-1.html. 

## Scikit-learn

A biblioteca *scikit-learn* contém três tipos de classificadores Naive Bayes: *GaussianNB*, *BernoulliNB* e *MultinomialNB*, todos pertencentes ao módulo ```sklearn.naive_bayes```:
1. *GaussianNB* trabalha com dados contínuos;
2. *BernouilliNB* aplica-se a dados binários (duas categorias);
3. *MultinomialNB* é usado para dados de contagem, por exemplo, número de vezes que uma palavra aparece em uma sentença ou documento.
[Exemplo de uso do MultinomialNB](https://scikit-learn.org/stable/auto_examples/text/plot_document_classification_20newsgroups.html#sphx-glr-auto-examples-text-plot-document-classification-20newsgroups-py).

Os classificadores Naive Bayes são semelhantes aos lineares, sendo ainda mais rápidos na fase de treino, porém com menor poder de generalização. Em todos os tipos de classificadores Naive Bayes, há somente um parâmetro que controla a complexidade do modelo: *alpha*. Este parâmetro define o nível de [suavização](https://en.wikipedia.org/wiki/Additive_smoothing) (inserção de valores positivos em características, para evitar a multiplicação de probabilidades por 0): quanto maior o valor de *alpha*, maior a suavização e menor a complexidade do modelo. 

### Referências bibliográficas

JURAFSKY, D.; MARTIN, J. Speech and Language Processing: An Introduction to
Natural Language Processing, Computational Linguistics, and Speech Recognition,
3 ed. Draft. 2019. Disponível em https://web.stanford.edu/~jurafsky/slp3/.
