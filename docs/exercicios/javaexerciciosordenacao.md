# Exercicios de Ordenação em Java 

Nesta secção iremos apresentar exercicios de algoritmos de ordenação:

## Ordenação de inteiros

### Problema 1 

Dada a sequência de números: 3 4 9 2 5 8 2 1 7 4 6 2 9 8 5 1, ordene-a em forma
decrescente segundo os seguintes algoritmos, apresentando a sequência obtida após
cada passo do algoritmo:
1. Selection Sort 
1. Bubble Sort

### Problema 2

Cria um programa que leia **n** inteiro inserindo-os em num array de forma ordenada crescente utilizando o algoritmo da **Insertion sort**. No final, imprimi os numeros ordenados.

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









