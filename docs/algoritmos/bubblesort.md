# Bubble Sort - Algoritmo de ordenação por troca

## Versão Não Melhorada

Este algoritmo de ordenação são efectuadas comparações entre os dados armazenados num array/vector de têm tamanho **N**. 
Cada elemento que se encontra na posição **i** será comparado com o elemento da posição **i+1**, e quando é encontrada a ordenação que se pretende (crescente ou decrescente) é efectuada a troca de posições dos elementos.




```pseudocode
inicio_algoritmo
declaro X[N],n,i,aux como valores numericos // N é o numero de elementos de estão armazenados
para n <- 1 até N faz // Isto é um For
inicio
    para i<- 0 até n-1 faz // Isto é um For
    inicio
        se (X[i] > X[i+1])
        então inicio
            aux <- X[i]
            X[i]<- X[i+1]
            X[i+1]<- aux
        fim
    fim
fim
fim_algoritmo
```

```java

import java.util.*;

public class BubbleSortNaoMelhorada
{

    public static void main(String [] args)
    {
        int [] X = new int[5];
        int aux;
        Scanner sc = new Scanner(System.in);
        
        //obter os numeros para introduzir no array/vector
        for(int i=0;i<X.length;i++)
        {
            X[i] = sc.nextInt();
        }
        
        // ordenar o array em forma crescente
        // Percorrer os elementos do array desde da posicao 1 até à sua ultima posicao
        for(int n=1;n<X.length;n++)
        {
            //Percorrer desde a primeira posicao até a penultima posicao do array
            for(int i=0;i<=X.length-2;i++)
            {
                if(X[i]>X[i+1])
                {
                    aux = X[i];
                    X[i] = X[i+1];
                    X[i+1] = aux;
                }
                }
        }
        
        //Mostrar os elementos do array ordenados em forma crescente
        for(int i = 0; i<X.length; i++)
        {
            System.out.println((i+1) + "º numero: " + X[i]);
        }
    }
    
}

```

As ilustrações seguintes demonstram a execução do algoritmo **Buuble Sort** para uma ordenação crescente de um array com __5__ elementos.

1. **1ª execução do FOR (n=1)**
![1_iteração](../images/algoritmos/bubble_sort_1_iteração.png)

1. **2ª execução do FOR (n=2)**
![2_iteração](../images/algoritmos/bubble_sort_2_iteração.png)

1. **3ª execução do FOR (n=3)**
![3_iteração](../images/algoritmos/bubble_sort_3_iteração.png)

1. **4ª execução do FOR (n=3)**
![4_iteração](../images/algoritmos/bubble_sort_4_iteração.png)

1. **5ª execução do FOR (n=3)** - Apesar do array já se encontra ordenado é sempre realizada a última ordenação.

![5_iteração](../images/algoritmos/bubble_sort_5_iteração.png)

## 1ª Versão Melhorada

Este algoritmo de ordenação são efectuadas comparações entre os dados armazenados num array/vector de têm tamanho **N**. 
Cada elemento que se encontra na posição **i** será comparado com o elemento da posição **i-1**, e quando é encontrada a ordenação que se pretende (crescente ou decrescente) é efectuada a troca de posições dos elementos. 
O primeiro ciclo percorre a quantidade de elementos menos um do array e dentro deste existe outro ciclo que percorre desde a ultima posição do array até à posição actual que encontra do array anterior.
A diferença desta versão para anterior é que as posições já se encontram ordenadas não irão ser percorridas no segundo array.

```pseudocode
inicio_algoritmo
declaro X[N],n,i,aux como valores numericos // N é o numero de elementos de estão armazenados
para n <- 1 até N faz // Isto é um For
inicio
    para i<- n-1 até n faz // Isto é um For
    inicio
        se (X[i] < X[i-1])
        então inicio
            aux <- X[i]
            X[i]<- X[i-1]
            X[i-1]<- aux
        fim
    fim
fim
fim_algoritmo
```


```.java

import java.util.*;

public class BubbleSortMelhorada1
{
    
    public static void main(String [] args)
    {
        int [] X = new int[5];
        int aux;
        Scanner sc = new Scanner(System.in);
    
        //obter os numeros para introduzir no array/vector
        for(int i=0;i<X.length;i++)
        {
            X[i] = sc.nextInt();
        }
    
        // ordenar o array em forma crescente
        // Percorrer os elementos do array desde da posicao 1 até à sua ultima posicao
        for(int j=1;j<=X.length-1;j++)
        {
    
            //Percorrer da ultima posicao à posicao j do vector
            for(int i=X.length-1;i>=j;i--)
            {
                if(X[i]<X[i-1])
                {
                    aux = X[i];
                    X[i] = X[i-1];
                    X[i-1] = aux;
                }
            }
        }
    
        //Mostrar os elementos do array ordenados em forma crescente
        for(int i = 0; i<X.length; i++)
        {
            System.out.println((i+1) + "º numero: " + X[i]);
        }
    
    }

}

```

As ilustrações seguintes demonstram a execução do algoritmo **Buuble Sort** da versão melhorada para uma ordenação crescente de um array com __5__ elementos.

1. **1ª execução do FOR (n=1)**
![1_iteração](../images/algoritmos/bubble_sort_v1_1_iteração.png)

1. **2ª execução do FOR (n=2)**
![2_iteração](../images/algoritmos/bubble_sort_v1_2_iteração.png)

1. **3ª execução do FOR (n=3)**
![3_iteração](../images/algoritmos/bubble_sort_v1_3_iteração.png)

1. **4ª execução do FOR (n=4)** - Apesar do array já se encontra ordenado é sempre realizada a última ordenação.

![4_iteração](../images/algoritmos/bubble_sort_v1_4_iteração.png)

## 2ª Versão Melhorada

Este algoritmo de ordenação são efectuadas comparações entre os dados armazenados num array/vector de têm tamanho **N**. 
Cada elemento que se encontra na posição **i** será comparado com o elemento da posição **i+1**, e quando é encontrada a ordenação que se pretende (crescente ou decrescente) é efectuada a troca de posições dos elementos. 
O primeiro ciclo percorre a quantidade de elementos do array enquanto existir trocas para fazer e dentro deste existe outro ciclo que percorre desde a primeira posição até à penultima posição do array.
A diferença desta versão para anterior é numero de execuções que irão ser realizadas no primeiro ciclo.

```pseudocode
inicio_algoritmo
declaro X[N],n,i, aux, troca como valores numericos // N é o numero de elementos de estão armazenados
n <- 1
troca <- 1
enquanto (n <= N e troca = 1 ) // Isto é um For
inicio
    troca <- 0
    para i<- 0 até n-1 faz // Isto é um For
    inicio
        se (X[i] < X[i+1])
        então inicio
            troca <- 1
            aux <- X[i]
            X[i]<- X[i+1]
            X[i+1]<- aux
        fim
    fim
    n <- n+1
fim
fim_algoritmo
```
```.java

import java.util.*;

public class BubbleSortMelhorada2
{

    public static void main(String [] args)
    {
        int [] X = new int[5];
        int n, aux, troca;
        Scanner sc = new Scanner(System.in);
        
        //obter os numeros para introduzir no array/vector
        for(int i=0;i<X.length;i++)
        {
            X[i] = sc.nextInt();
        }
        
        // ordenar o array em forma Decrescente
        // Percorrer os elementos do array enquanto existir trocas de posicoes
        n=1;
        troca = 1;
        while(n<=X.length && troca == 1)
        {
            troca = 0;
            for(int i=0;i<=X.length-2;i++)
            {
                if(X[i]<X[i+1])
                {
                    troca = 1;
                    aux = X[i];
                    X[i]=X[i+1];
                    X[i+1] = aux;
                }
            }
            n = n + 1;
        }
        
        
        //Mostrar os elementos do array ordenados em forma decrescente
        for(int i = 0; i<X.length; i++)
        {
            System.out.println((i+1) + "º numero: " + X[i]);
        }

    }

}

```

As ilustrações seguintes demonstram a execução do algoritmo **Bubble Sort** da 2ª versão melhorada para uma ordenação decrescente de um array com __5__ elementos.

1. **1ª execução do FOR (n=1 e troca = 1)**
![1_iteração](../images/algoritmos/bubble_sort_v2_1_iteração.png)

1. **2ª execução do FOR (n=2 e troca = 1)**
![2_iteração](../images/algoritmos/bubble_sort_v2_2_iteração.png)
 
