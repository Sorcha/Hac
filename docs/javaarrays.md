# Agrupamento de dados em Java (Arrays)

**Arrays** são tipos indexados de dados que permitem a representação de agrupamento de dados como
vetores e matrizes.

## Declarando e criando **Arrays**

Podemos declarar arrays de qualquer tipo de dado suportado em Java (primitivo ou agregado – tipos
agregados de dados iremos abordar para a semana). Essa declaração é feita pela adição do símbolo **[]**
a um tipo de dado, que pode aparecer antes ou após o identificador da variável:

* char[] arrayDeCaracteres;
* String[] arrayDePalavras;
* int números[];

Na memória, um array é um agrupamento de dados, indexados pelo tamanho do tipo de dado que o array
suporta:

O primeiro índice de um array é sempre *0*, e o último índice é o *N-1*, onde *N* é o número de
elementos do array.

Para criar um array, usamos a palavra chave **_new_**:
```
int[] números = new int[50];
```

A quantidade de elementos de um array sempre deve ser um valor inteiro. O comprimento de um array é
dado pelo método length:

``` .java
// Imprimir o comprimento de um array

char [] alfabeto = new char[24];
int tamanhoDoAlfabeto = alfabeto.length;

System.out.println("alfabeto com " + tamanhoDoAlfabeto + " letras");
// Muito importante: um array de 10 elementos tem os índices de 0 a 9
```

## Inicializando os valores de um **Array**

Quando declamos um array de um tipo, o Java insere o valor default em todos as suas posições. Ou seja, se declaramos um array de inteiros com 50 posições:

```
int[] números = new int[50];
```

O Java para as 50 posições insere **0**. Em outros tipos de dados (agregados), um array não será inicializado, ou seja, a declaração apenas criará uma referência a uma área de memória que não conterá valor algum. A **String** é um tipo agregado.\
No exemplo apresentado embaixo, criou-se um array de Strings mas em todas as posições não existe strings ou seja, em todas as posições serão nulas. Quando se pretende-se obter o tamanho da string que se encontra-se na posição 1, o programa deixará de funcionar e na consola irá aparecer a exceção retornada pela o java **_Exception in thread "main" java.lang.NullPointerException_**, porque o array contem nenhuma string na posição **0**.


```
.java

// Essas linhas causarão um erro de execução, pois a posição 0 do array
// contendo as frases não possui nenhum valor (null) e, portanto,
// não pode ser usada como parâmetro para nenhum tipo de operação.

String[] frases = new String[10];
int comprimentoDaPrimeiraFrase = frases[0].length();

//Exception in thread "main" java.lang.NullPointerException

```

Para que possamos usar os dados contidos em um array, precisamos antes inicializá-los, conforme os
exemplos abaixo:

```
.java

// Inicializando arrays
String[] frases = new String[5];
frases[0] = "primeira frase";
frases[1] = frases[0];
frases[2] = frases[0] + frases[1];
frases[3] = "outro texto qualquer";
frases[4] = "último índice do vetor";
// inicialização no momento da declaração de um array:
String[] dias = {"segunda", "terça", "quarta", "quinta", "sexta", "sábado", "domingo" };
int[] meses = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12 };

```


## Array multi-dimensional

Quando declaramos um array através do símbolo **[]**, estamos de fato criando um array unidimensional
(vetor). Além de vetores, a linguagem Java permite a declaração de arrays n-dimensionais, como matrizes, conforme os
exemplos:

``` .java

// array unidimensional (VETOR)
String[] frases = new String[5];

// array bidimensional (MATRIZ)
String[][] tabela = new String[5][15];

// array n-dimensional
double [][][] densidade;
densidade = new double[10][10][10];

// observe que nem todos os valores de um array
// precisam estar preenchidos. Sempre que for
// usar o valor contido em uma posição de um array
// deves ter a certeza que essa posição
// foi inicializada
densidade[0][0][0] = 35.034;
densidade[1][0][0] = 30.876;

System.out.println("densidade na coordenada 1,0,0 = " + densidade[1][0][0]);

// arrays com mais de três dimensões são raramente
// encontrados em programas de computador, mas
// são permitidos em Java

float[][][][][][] espacoHexaDimensional;
int[][][][] quartaDimensao = new int[564][2][200][1];
Ponto[][][][][][][][][][][][] hiperespaco;

```

## Array esparso

Java permite a declaração de estruturas esparsas, ou seja, um agrupamento indexado de dados onde
nem todas as dimensões são iguais:

```
// Matrizes esparsas podem ser representadas em Java
// através de arrays com dimensões heterogêneas:
int[][] esparso = new int[4][];
esparso[0] = new int[10];
esparso[1] = new int[2];
esparso[2] = new int[5];
esparso[3] = new int[1];
// Na memória, o espaço de dados ocupado pelo
// array acima seria aproximadametne assim:
// [ | | | | | | | | | ]
// [ | ]
// [ | | | | ]
// [ ]
```
