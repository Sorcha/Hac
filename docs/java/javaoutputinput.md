# Output e Input no Jana

## Input no Java

Para ler valores da consola, é necessario utilizar a classe **Scanner** que tem a funcionalidade de facilitar a entrada de dados no modo *Consola*.

A classe **Scanner** tem como objetivo separar o texto que se encontra na consola em blocos, gerando os conhecidos tokens, que são sequências de caracteres separados por delimitadores que por padrão correspondem aos espaços em branco, tabulações e mudança de linha.

#### Modo de uso da classe **Scanner**

1. 1º Passo - Importar a class **Scanner**

Quando pretende-se  usar esta classe é necessario avisar ao compilador onde esta se encontra, por isso é necessario introduzir a sua importação __import java.util.Scanner;__ no inicio do ficheiro **.java**.

``` .java

//Importação da classe Scanner
import java.util.Scanner;

public class TestScanner 
{
    public static void main(String[] args) 
    {
        //programa
    }
}

```

1. 2º ª Passo - Para a utilizar as funcionalidades da classe **Scanner** é necessario criar um objecto desta classe e passar como argumento __System.in__  que faz a leitura do que se escreve no teclado. 

``` .java

import java.util.Scanner;

public class TestScanner 
{
    public static void main(String[] args) 
    {
        /Lê a partir da linha de comando
        Scanner sc1 = new Scanner(System.in); 
    }
}

```

No exemplo que se encontra abaixo, demontra como são invocados alguns dos métodos principais que correspondem com a assinatura que retorna um valor do tipo que foi invocado. Ou seja, para cada um dos primitivos existe uma chamada do método para retornar o valor especificado na entrada de dados, sempre seguindo o formato __nextTipoDado()__.

``` .java

Scanner sc = new Scanner(System.in);

float numF = sc.nextFloat();
int num1 = sc.nextInt();
byte byte1 = sc.nextByte();
long lg1 = sc.nextLong();
boolean b1 = sc.nextBoolean();
double num2 = sc.nextDouble();
String nome = sc.nextLine();

```

## Output no Java


O objeto **System.out ** é o modo de saída padrão, que permite exibir as Strings na consola de comando quando o programa  Java é executado. Dentro desse objeto existem métodos para gerar saídas de Strings, entre elas são: println e print.


### Modo System.out.println

A instrução **System.out.println()**, gera uma saída de texto entre aspas duplas significando uma String e passa para a proxima linha("enter");

``` .java

public class Texto_Simples 
{
    public static void main(String[] args)
    {
        System.out.println(“O texto é inserido aqui, entre aspas duplas”);
    }
}

```

``` .java

public class Texto_Simples 
{
    public static void main(String[] args)
    {
        int numero = 10
        System.out.println(10);
    }
}

```

### Modo System.out.print

O método com **print**, exibe uma String sem criar uma nova linha e deixa o  cursor na mesma linha.

``` .java

public class Texto_Simples 
{
    public static void main(String[] args)
    {
        System.out.print(“José”);
        System.out.print(“Silva Moraes”);
    }
}

```
