# Sintaxe da linguagem Java

## Delimitadores em Java

Em um código-fonte Java, alguns símbolos, chamados **delimitadores**,  são utilizados pelo compilador para diferenciar comandos. O Java tem os seguinte delimitadores:
* Comentários;
* Ponto e Vírgual (**;**);
* Blocos de código;
* Espaços em branco;

### Comentários

Comentários servem para identificar a função de um comando, um bloco de código, ou um método.
Além disso, os comentários podem ser utilizados para documentar aspectos de desenvolvimento de um
programa: como a versão do programa, o que um metodo faz, etc. Existem dois tipos de comentário: o simples e o de documentação. O comentário simples é delimitado por duas baras **//** e termina ao final de uma linha.
O comentário de documentação é iniciado pelo símbolo ***/** e encerrado pelo símbolo  ***/**, podendo conter
várias linhas de texto e linhas em branco.

```.java

// comentário simples: não será incluído na documentação
// do programa (note que comentários simples exigem
// um par de barras para cada linha).
/**
HAC - Maria
Exemplo de um comentário de documentação
Pode usar várias linhas com texto ou linhas em branco

Este tipo de comentário pode ser usado para explicar o que o programa faz ou descrever cada passo do programa.
Fim do comentário de documentação.
*/
```

### Ponto e Vírgula (**;**)

Em Java, todo comando é terminado por um ponto e vírgula (;). 

```.java

System.out.println("note o ponto e vírgula no final ? ");
int i = 10; // A declação de uma variavél inteira 

for(int j=0; j<10; i++) // no final do for não é necessario o ponto e virgula
{

}

```

### Bloco de código

Um bloco de codigo é formado por um conjunto de instruções delimitadas por parentes **{}**.
O espaço em branco, quebra de linha e caracteres de tabulação são permitidos em qualquer bloco do
código, devendo ser utilizados para realçar o aspecto visual de seu código.


```.java

/** Exemplo de bloco */
{ // Chamamos essa chave de início de bloco
    int ano; // Note o ponto e vírgula
    ano = 2002; // sempre ao final de um comando Java
} // Chamamos essa chave de final de bloco
```




## Declarar Variavéis em Java


Uma variável é sempre declarada com o seguinte esquema:

**`<tipo>`** + **`<espaço>`** + **`<identificador>`** + **=** + **`<valor>`** ;

ou

**`<tipo>`** + **`<espaço>`** + **`<identificador>`** + **;** ;

onde:

* `<tipo>` é um tipo primitivo de dados ou o nome de uma classe;
* `<identificador>` é o nome da variável;
* `<valor>` é o valor atribuído à variável.

Caso se pretenda declarar uma variavél sem valor de omissão então basta declarar uma variável e não atribuir nenhum
valor, mas **atenção** ela não poderá ser utilizada no código Java sem valor, porque a tentativa de utilizar uma
variável não inicializada em Java gerará um erro de compilação, por isso antes de a utiliar é necessario atribuir um valor. 

Exemplo:

```.java

public class OlaMundo
{
    //Duas barras significam comentários
    /*comentários tambem podem seguir o format /**/ */

    //o método main deve sempre estar presente para que o codigo JAVA possa ser executado
    static public void main(String[] args)
    {
        // Criação de uma variavel sem inicialização
        boolean obrigatorio;
        //Inicializar a variavel obrigatorio com o valor false
        obrigatório = false;
        // Criação de uma variavel com inicialização
        int semestre = 2;
        // Criação de uma variavel sem inicialização
        String mensagem = "Ola mundo.";
        System.out.println(mensagem);
    }
}
```

## Tipos Primitivos em Java

A linguagem Java utiliza oito tipos primitivos de dados e um tipo especial. Esses tipos primitivos podem
ser utilizados para declarar constantes ou variáveis utilizadas em programas Java. Os tipos primitivos
estão divididos em quatro categorias: lógicos, textuais, numéricos inteiros e numéricos de ponto flutuante.

### Tipos lógicos: **boolean**

Valores lógicos possuem dois estados, normalmente ditos verdadeiro/falso, sim/não e ligado/ desligado.
Em Java um tipo lógico é definido pela palavra **_boolean_**, e pode assumir dois valores: **true** ou **false**.

```.java 

// Exemplo de variável que suporta valores booleanos
boolean anoBissexto = false;
boolean anoPar = true;
// Apesar de uma variável poder ser declarada
// sem receber um valor, ela só poderá ser usada
// após a atribuição de algum valor a ela.
boolean valido;

```

### Tipos textuais: **char** e **String** 

Caracteres simples são representados pelo tipo **char** e representa um caracter UNICODE, ou
seja, um número inteiro sem sinal de 16 bits, no intervalo de 0 até 2^{16 -1}.  O valor de um literal **char** deve
ser delimitado por aspas simples: **'a'**

```.java 

// Exemplo de representação de caracteres UNICODE
char primeiraLetra = 'a';
// Código UNICODE para o caracter de interrogação
char unicode = '\u0A02';
// Lembra-te: Uma variável só poderá
// ser manipulada após receber um valor.
char inutil; // variável sem utilidade neste momento
inutil = '@'; // variável útil a partir de agora

```

Palavras são representadas por uma sequência de dados do tipo **char**, agrupadas em um tipo especial
de dados: a classe **String**. Apesar de ser uma classe, uma variável do tipo String suporta operações
como se fosse um tipo primitivo de dados. O valor de uma variável String deve ser delimitado por aspas
duplas **"valor"**.

```.java 

// Exemplo de utilização de variáveis do tipo String
String disciplina = "Biologia" ;

// Uma variável pode receber o valor de outra
String outraVariavel = disciplina;

// A concatenação de Strings pode ser feita através do operador de soma (+)
disciplina = "Biologia " + "de 10º Ano";
// Concatenação de String com outro tipo de dados:
disciplina = "Biologia" + 'X';
disciplina = "Biologia" + 1;
// Para comparar duas variáveis do tipo String
// deve-se utilizar o método equals():
// disciplina == "Biologia" ? // esta forma de comparação esta ERRADA
// disciplina.equals("Sistemas orientados...") // esta forma de comparação esta CORRECTA

```

A concatenação de qualquer tipo de dado com um dado do tipo **String** resulta sempre num novo dado do
tipo **String**. 


### Tipos numéricos inteiros: **byte** , **short**, **int** e **long**

Existem quatro tipos primitivos de números em Java. Estes  valores numéricos podem ser
representados de forma **decimal**, **octal** ou **hexadecimal**. Todos os valores numéricos em Java tem sinal positivo ou negativo. 
Exemplo:

* 2 - decimal;
* 077 - um número que começa com zero está representado de forma octal;
* 0xBABE - representação hexadecimal;

Um valor numérico é sempre considerado do tipo **int**, a menos que seja acompanhado do **sufixo L**, que
representa um valor do tipo **long**. A diferença de um inteiro para um longo é a capacidade de dígitos que
podem ser representados.

```.java 

// Valores inteiros representáveis pelos tipos
// numéricos em Java:

byte a = 127; 
short b = 32767; 
int c = 2147483647; 
long d = 9223372036854775807L;

```

### Tipos numéricos decimais: **float** e **double**

Um valor decimal pode ser representado em Java através dos tipos **float** e **double**. A diferença entre
esses dois tipos é o tamanho das casas decimais.
Para um número ser considerado do tipo ponto decimal, é necessário a inclusão de um **ponto**, do
caractere **E** (de expoente) ou do sufixo **D** ou **F**, conforme mostra o exemplo:

```.java 

// Representação de valores numéricos decimais
float pi = 3.141516;
float taxa = 6.02E23;
double valor= 123.4E+306D;

```


