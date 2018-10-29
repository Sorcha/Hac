# Expressões da linguagem Java

## Operadores lógicos e aritméticos

A tabela abaixo enumera esses operadores em ordem de precedência:

| Ordem de Leitura     | Operador     | Função     |
|:----------------:    |:--------------------------------------------------:    |:----------------------------------------------------------------------------:    |
| Unário     | ++     | Incrementa o valor da variável em uma unidade. **Exemplo:**,i++; contador++;     |
| Unário     | --     | Diminui o valor da variável em uma unidade. **Exemplo:** i--; contador--;     |
| Unário     | + e -     | Operadores aritméticos;     |
| Unário     | * , / e %     | Multiplicação, divisão e resto;     |
| Unário/Lógico     | <<, >> e >>>     | Operadores de deslocamento aritmético e lógico;     |
| Lógico     | == e !=     | Igualdade e desigualdade;     |
| Unário     | ^     | Potência     |
| Lógico     | &&    | AND   e OR  |
| Lógico     | ?:     | Operador condicional. **Exemplo:** i=0; (i>2?i=0:i --);     |
| Atribuição     | =, *= ,  %= += , -= <<= ,  >>= >>>= , &=  e ^=      | Operadores aplicados sobre a atribuição;     |


## Concatenação de Strings com o operador **+**

Quando o operador **+** é aplicado a dados do tipo **String**, ele cria um novo dado
do tipo **String**, concatenando os dois operandos:

```.java

/**
* Concatenação de Strings
*/
String sigla = "HAC";
String nome = "Maria";
String titulo = sigla + " - " + nome;
// Esse comando imprimirá na consola a frase:
// HAC – Maria
System.out.prinln(titulo);

int i = 10;

String legenda = "valor = ";

// campo é uma variável do tipo String
String campo = legenda + i;

```

Alguns métodos úteis em dados do tipo String:

```.java

/**
* Strin: métodos úteis
*/
String sigla = "HAC";
System.out.println("sigla: " + sigla);
// Obter  um caractere:
System.out.print("primeiro caracter: "); 

//O primeiro caracter de uma String tem o indice 0
System.out.println(sigla.charAt(0));
// O segundo caracter encontra-se no índice 1 e assim por diante
System.out.print("segundo caracter: ");
System.out.println(sigla.charAt(1));

// letra = 's';
char letra = sigle.charAt(2);

// substrings:
System.out.print("primeiras 2 letras: ");
System.out.println(sigla.substring(0, 2));
System.out.print("letras a partir da segunda: ");
System.out.println(sigla.substring(2));

// número de caracteres em uma String:
System.out.print("tamanho da frase: ");

System.out.println(sigla.lenght() + " letras");
// usando os caracteres de tabulação e quebra de linha:
System.out.println("" + disciplina.lenght() + " letras" + " \n" + " Nova linha \ttabulação");

```

### Promoção e Casting

A linguagem Java não suporta atribuições arbitrárias entre variáveis de tipos diferentes. Por exemplo,  não pode-se inicializar uma variável inteira com um valor decimal sem explicitar  através de um processo que
chamamos de **casting**.
Quando atribuímos um valor a uma variável, e esse valor é incompatível com o
tipo de dado definido para essa variável, ocorrerá uma conversão. Em alguns
casos, essa conversão será automática, em outros o programador deve indicar de
que forma o valor será convertido ao tipo de dado da variável.
Quando o processo de conversão for automático, dizemos que ocorreu uma
**promoção**, ou seja, um valor com um tipo de dado foi promovido a outro tipo de
dado. Exemplo:

```.java

//
// Promoção entre valores de tipos de dados distintos
// Apesar 6 ser um inteiro, o valor da variável grande
// continua sendo do tipo long
long grande = 6;
// Uma variável do tipo inteiro não possui
// espaço para armazenar um valor longo.
// A instrução abaixo é errada, e causará um erro de compilação.
int pequeno = 99L;
float a = 12.121F; // correto
float b = 12.121; // 12.121 é um double - incorreto

```

Como se pode observar, algumas conversões não podem ser realizadas de forma
automática, pois o compilador não pode assumir que tipo de conversão ele deve
realizar (o tamanho do tipo de dado a ser recebido por uma variável é maior que o tamanho pré-definido para o tipo dessa variável, logo o compilador não
sabe como "ajustar" os bits excedentes). 
Nesse caso, o programador deve indicar ao compilador que tipo de conversão deverá ocorrer, digitando o tipo
de dado que o valor deverá assumir entre parênteses:

```.java

//
// Casting entre valores de tipos de dados distintos
//
// Apesar 6 ser um inteiro, o valor da variável grande
// continua sendo do tipo long
long grande = 6;
int pequeno = (int)99L; // sem problemas
float a = 12.121F;
float b = (float)a; // sem problemas

```

### Operadores de deslocamento (>>, <<, >>>)

Java provê operadores para a manipulação dos bits em variáveis de tipo numérico: o deslocamento
aritmético **>>** e o deslocamento lógico **>>>**.
O operador de deslocamento aritmético **>>** executa um deslocamento de um bit para a direita de um
número (na prática, o primeiro argumento desse operador é dividido por dois '_n_' vezes – onde _n_ é o
segundo argumento do operador):

```
8 >> 2 = 2
128 >> 1 = 64
256 >> 4 = 16
```

O operador de deslocamento lógico **>>>** executa um deslocamento no padrão dos bits ao invés do
significado aritmético de um valor numérico. Esse operador sempre adiciona o valor **0** ao bit mais
significativo:

```
1010 ... >> 2 = 111010 ...
1010 ... >>> 2 = 001010 ...
```

### Circuitos lógicos

Java possui três operadores básicos para implementar circuitos lógicos :

* NOT: operador !
* AND: operador &&
* OR: operador ||

Esses operadores permitem a representação de expressões booleanas, que formam o argumento para comandos de decisão (IF), seguindo a seguinte tabela:


| AND     | OR     |
|:-----------------------:    |:-----------------------:    |
| true && true = true;     | true || true = true;     |
| true && false = false;     | true || false = true;     |
| false && true = false;     | false || true = true;     |
| false && false = false;     | false || false = false;     |

Os comandos de controle **(if, while, switch)** utilizam o valor de expressões
booleanas para guiar o fluxo de controle de um programa, como no exemplo
abaixo:

```.java

/**
* Comandos de decisão utilizando expressões booleanas
*/
int mes = 2;
if((mes == 12) || (mes == 1))
{
    System.out.println("férias :)" );
}
if((mes > 1) && (mes < 12))
{
    System.out.println("semestre em andamento");
}
if((mes != 2))
{
    System.out.println("não tem carnaval ");
}
```



