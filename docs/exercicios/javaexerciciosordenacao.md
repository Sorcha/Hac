# Exercicios de Ordenação em Java 

Nesta secção iremos apresentar exercicios de algoritmos de ordenação:

## Ordenação de inteiros

### Problema 1 

Dada a sequência de números: 3 4 9 2 5 8 2 1 7 4 6 2 9 8 5 1, ordene-a em forma
decrescente segundo os seguintes algoritmos, apresentando a sequência obtida após
cada passo do algoritmo:
1. Selection Sort 
1. Bubble Sort

<details>
<summary>Solução do exercicio para SelectionSort</summary>

```.java

import java.util.*;

public class Exercicio1
{

    public static void main(String [] args)
    {
        int[] intArray = new int[] {3,4,9,2,5,8,2,1,7,4,6,2,9,8,5,1};
        int indiceDoArray,j, eleito, maior, pos;
        
        // ordenar o array em forma decrescente
        // Percorrer desde a primeira posicao à penultima posicao do array
        // elegendo um numero para ser comparado
        for(indiceDoArray=0;indiceDoArray < intArray.length - 1;indiceDoArray++)
        {
            eleito = intArray[indiceDoArray];
            
            // encontrar o menor numero à direita do eleito com a sua posicao
            maior = intArray[indiceDoArray + 1];
            pos = indiceDoArray + 1;
            
            // Percorrer os elementos que estao a direita do eleito
            // retornando o maior numero a sua direita e a sua posicao
            for(j=indiceDoArray+2;j<=intArray.length - 1; j++)
            {
                if(intArray[j] > maior)
                {
                    maior = intArray[j];
                    pos = j;
                }
            }
        
            // trocar o numero eleito com o numero da posicao pos
            // o numero da posicao pos e maior numero a direita do eleito
            if(maior > eleito)
            {
                intArray[indiceDoArray] = intArray[pos];
                intArray[pos] = eleito;
            }
        }
        
        //Mostrar os elementos do array ordenados em forma decrescente
        for(int i = 0; i<intArray.length; i++)
        {
            System.out.println((i+1) + "º numero: " + intArray[i]);
        }
    }
}


```



</details>

<details>
<summary>Solução do exercicio para BubbleSort</summary>

```.java

import java.util.*;

public class Exercicio1
{

    public static void main(String [] args)
    {
        int [] sequencia = new int[]{3,4,9,2,5,8,2,1,7,4,6,2,9,8,5,1};
        int indiceCurrente, variavelAuxiliar, troca;
        
        // ordenar o array em forma Decrescente
        // Percorrer os elementos do array enquanto existir trocas de posicoes
        indiceCurrente=1;
        troca = 1;
        while(indiceCurrente<=sequencia.length && troca == 1)
        {
            troca = 0;
            //Percorrer o array ate a penultima posicao
            for(int i=0;i<=sequencia.length-2;i++)
            {
                if(sequencia[i]<sequencia[i+1])
                {
                    troca = 1;
                    variavelAuxiliar = sequencia[i];
                    sequencia[i]=sequencia[i+1];
                    sequencia[i+1] = variavelAuxiliar;
                }
            }
            indiceCurrente += 1;
        }
        
        
        //Mostrar os elementos do array ordenados em forma decrescente
        for(int i = 0; i<sequencia.length; i++)
        {
            System.out.println((i+1) + "º numero: " + sequencia[i]);
        }
    
    }

}


```



</details>

### Problema 2

Cria um programa que leia **n** inteiro inserindo-os em num array de forma ordenada crescente utilizando o algoritmo da **Insertion sort**. No final, imprimir os numeros ordenados.

<details>
<summary>Solução do exercicio</summary>

```.java

import java.util.*;

public class Exercicio2
{

    public static void main(String [] args)
    {
        int indiceDoArray,j, eleito;
        Scanner sc = new Scanner(System.in);
        
        System.out.println("Introduza o numero de valores que pretende utilizar");
        int n = sc.nextInt();
        int [] valores = new int[n];
        
        //obter os numeros para introduzir no array/vector
        for(int i=0;i<n;i++)
        {
            System.out.println("Introduza o " + (i+1) + "º valor.");
            valores[i] = sc.nextInt();
        }
        
        // ordenar o array em forma crescente
        // Percorrer os elementos do array desde da posicao 1 até à sua ultima posicao
        for(int i = 1;i<=valores.length-1;i++)
        {
            eleito = valores[i];
            j = i - 1;
            // percorrer os elementos que estão à esquerda do eleito ou até encontrar
            // a posição para recolocacao do eleito respeitando a ordenação que pretende
            while(j>=0 && valores[j] > eleito)
            {
                valores[j+1] = valores[j];
                j = j-1;
            }
            valores[j+1] = eleito;
        }
        
        //Mostrar os elementos do array ordenados em forma crescente
        for(int i = 0; i<valores.length; i++)
        {
            System.out.println((i+1) + "º numero: " + valores[i]);
        }
    }

}



```



</details>

### Problema 3

Chegou o dia da inauguração da biblioteca da Dona Alexandra. Finalmente! O Gabriel não pensava noutra coisa desde que soube da sua abertura. Podiam pensar que ele é um miúdo mesmo aplicado como tu e eu, mas na verdade ele tem outros interesses...

Acontece que a Dona Alexandra usa uma estratégia incomum para incentivar os mais jovens a ler: aquando a devolução dos livros, o leitor recebe uma quantidade de pontos igual ao número de páginas do livro que leu. Para que servem estes pontos? Podem ser trocados por prémios que a Dona Alexandra achou serem do agrado do público alvo. E acertou em cheio, o Gabriel não consegue tirar os olhos da linda Zbox que está exposta na montra.

No entanto, para evitar que os leitores mais novos se aventurem em obras demasiado "pesadas" para o seu nível, correndo assim o risco de perder o gosto pela leitura, a Dona Alexandra tem uma regra: leitores como o Gabriel só podem ler um determinado livro se já tiverem lido todos os livros mais pequenos que esse (claro que se pode ler o livro mais pequeno da biblioteca sem ter lido nenhum outro).

Por exemplo, se a Dona Alexandra tiver livros com 52, 6, 26, 12 e 13 páginas e se forem necessários 50 pontos para ganhar a Zbox, o Gabriel tem de começar por ler o segundo livro (com 6 páginas), pois é o menor, acumulando 6 pontos. Depois lê o próximo mais pequeno, que é quarto livro, somando mais 12 pontos e ficando com 18 pontos no total. De seguida, tem de ler o quinto, ficando com 31 pontos, o que ainda não é suficiente. Por último, lê o terceiro livro, perfazendo um total de 57 pontos, o que é suficiente para receber o seu prémio.

Para se manter motivado, o Gabriel quer saber qual é a sua meta, ou seja, quantos livros vai ter de ler no mínimo para ganhar a Zbox. Será que pode contar com a tua ajuda?

Dados os **N** livros que constituem o stock da Dona Alexandra e o número de pontos **Z** que a Zbox vale, devolve o número de livros que o Gabriel tem de ler para receber o prémio.

Na primeira linha do input vêm dois inteiros, **N** que representa o número de livros que existem na biblioteca e **Z** que representa o valor da Zbox.

Segue-se uma linha com **N** inteiros **P_i**, que representam o número de páginas do i-ésimo livro.

O output deve conter uma linha com apenas um inteiro, que representa o número mínimo de livros que o Gabriel tem de ler.


```java

import java.util.*;


public class Exercicio3
{
    public static void main(String [] args)
    {
        Scanner sc = new Scanner(System.in);
    
        int numeroLivros = sc.nextInt();
        int numeroDePontos = sc.nextInt();
        
        int [] livros = new int[numeroLivros];
        
        for (int i = 0;i<numeroLivros  ; i++ )
        {
            livros[i]=sc.nextInt();
        }
        
        quicksort(livros,0,numeroLivros-1);
        
        int pontos=0;
        for (int i= 0; i<numeroLivros ;i++ )
        {
            pontos+=livros[i];
            if(pontos>=numeroDePontos)
            {
                System.out.println((i+1));
                break;
            }
    
        }
    }


    public static void quicksort(int [] X, int p, int r)
    {
        int q;
        if(p<r)
        {
            q = particao(X,p,r);
            quicksort(X,p,q-1);
            quicksort(X,q+1,r);
        }
    }

    public static int particao(int [] X, int p, int r)
    {
        int pivot = X[r];
        int i = (p-1);
    
        for (int j = p; j < r; j++) 
        {
            if (X[j] <= pivot)
            {
                i++;
                troca(X,i,j);
            }
        }
    
        troca(X,i+1,r);
        return i+1;
    }
    
    public static void troca(int [] X,int i, int j)
    {
        int aux;
        aux = X[i];
        X[i] = X[j];
        X[j] = aux;
    }

}


```








