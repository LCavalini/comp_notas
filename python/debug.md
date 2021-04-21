# Depuração em Python

## Pdb

O módulo pdb permite depurar um programa em linha de comando através do
seguinte comando:

```
python -m pdb nome_do_programa.py [arg1] [arg2] [...]
```

É possível inserir pontos de parada no próprio código do programa a ser
depurado usando a função ```breakpoint()``` ou em tempo de execução do
depurador com o comando ```b n_linha```. Para ver o código-fonte, use o comando
```ll```.

O comado ```p expr``` imprime o valor de uma expressão em Python válida,
podendo ser o nome de uma variável. O comandos ```n``` e ```c``` avançam
para a próxima linha e continuam a execução até o próximo ponto de parada,
respectivamente.

