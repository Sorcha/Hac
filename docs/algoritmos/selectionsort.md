# Selection Sort - Algoritmo de ordenação por selecção

Neste algoritmos de ordenação cada elemento que se encontra no array, apartir da primeira posição, será "eleito" e comparado com o menor ou maior, dependo da ordenação que se pretenda, com os elementos que se estão à sua direita. Quando um elemento satifaz a condição de ordenação, este é trocará a posição com o elemento "eleito", e assim todos os elementos que estão à esquerda do eleito ficam sempre ordenado.


```pseudocode
inicio_algoritmo
declaro X[N],j,i,eleito, menor, pos como valores numericos // N é o numero de elementos de estão armazenados
para i <- 0 até N-1 faz // Isto é um For
inicio
    eleito <- X[i] 
    menor <- X[i+1]
    pos <- i+1
    para j <- i+2 até N-1 faz // Isto é um For
    inicio
        se (X[j] < menor)
        então inicio
            menor <- X[j]
            pos <- j
        fim
    fim
    se (menor < eleito)
    entao inicio
        X[i] <- X[pos]
        X[pos] <- eleito
    fim
fim
fim_algoritmo
```
```.java



```

As ilustrações seguintes demonstram a execução do algoritmo **Selection Sort** para uma ordenação crescente de um array com __5__ elementos.

1. **1ª execução do FOR**
![1_iteração](../images/algoritmos/selection_sort_1_iteration.png)

1. **2ª execução do FOR**
![2_iteração](../images/algoritmos/selection_sort_2_iteration.png)

1. **3ª execução do FOR**
![3_iteração](../images/algoritmos/selection_sort_3_iteration.png)

1. **4ª execução do FOR**
![4_iteração](../images/algoritmos/selection_sort_4_iteration.png)

