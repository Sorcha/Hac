# Fluxo de controle da linguagem Java

## Ramificação **if**, **else**

A sintaxe básica para declarações **if**, **else** é a seguinte:
```
if (expressão_booleana)
{
// bloco de comandos
}
else
{
// bloco alternativo de comandos
}`
```
exemplo:

```
.java

/**
* Utilizando if, else
*/

int maior = 10;
int menor = 5;
if (maior > menor)
{
    // (10 > 5) = true
    System.out.println(maior + ">" + menor);
}
else
{
    // (10 > 5) != true
    System.out.println(menor + ">" + maior);
}

// Lembra-te que o controle de fluxo é feito através
// do valor verdade de uma expressão booleana
boolean verdade = (10 > 5);
if (verdade)
{
    // (10 > 5) = true
    System.out.println(maior + ">" + menor);
}
else
{
    // (10 > 5) != true
    System.out.println(menor + ">" + maior);
}

```

## Ramificação **switch**

**Switch** é uma declaração semelhante ao **if**, mas que usa valores **numericos**(só pode ser usada em
dados dos tipos **short, int, byte ou char**) para a
tomada de decisões ao invés de expressões **booleanas**. 
Se o tipo de dado não for inteiro, o comando switch irá executar uma promoção desse valor ao tipo **int** para
somente depois executar a ramificação .
A sintaxe básica para declarações **switch** é a seguinte:

```
Switch ((int)expressão)
{
    // bloco de comandos
    case ((int) valor_1):
    // bloco de comandos
    break;
    case ((int) valor_2):
    // bloco de comandos
    break;
    default :
    // bloco de comandos padrão.
    // Se nenhum dos valores acima corresponder à
    // expressão definida no comando switch, então
    // o programa executará o bloco de codigo default.
    // o bloco de codigo default é opcional.
    break;
}
```
exemplo:

``` .java

/**
* Utilização do switch
*/
// Considere valorDoTeclado() como um número
// inteiro digitado pelo utilizador
int valor = valorDoTeclado();
switch (valor)
{
    case 0:
        System.out.println("cadastro de produto");
        break;
    case 1:
        System.out.println("emitir nota fiscal");
        break;
    case 2:
        System.out.println("cancelar compra");
        break;
    default:
        System.out.println("efetuar venda");
        break;
}

```

## Repetição **for**

A declaração **for** é utilizada para definir que um bloco de comandos deve ser executado '_n_' vezes, onde '_n_'
é um número inteiro. A sintaxe do comando for é a seguinte:

```
for (int i = 0; i < n; i++)
{
    // bloco de comandos
}
```
exemplo:

``` .java

/**
* repetição de comandos usando FOR
*/
// Calculando o fatorial de um número:
int numero = 10;
int fatorial = 1;
for (int i = numero; i > 0; i--)
{
    fatorial = fatorial * i;
}

System.out.println("fatorial de " + valor + " = " + fatorial);

// Imprimindo os dias do ano:
for (int mes = 1; mes < 12; mes++)
{
    switch (mes)
    {
        case 1:
            System.out.println("janeiro");
            break;
        case 2:
            System.out.println("março");
            break;
        case 3:
            System.out.println("abril");
            break;
            // resto dos meses
    }
}

```

## Repetição **while**

A declaração **while** é utilizada para definir que um bloco de comandos deve ser executado enquanto uma
expressão booleana (condição de paragem) não seja verdade.. A sintaxe do comando while é a seguinte:

```
while (expressão_booleana)
{
    // bloco de comandos executados enquanto a
    // expressão boolena tiver valor verdade = true
}

ou

do
{
    // bloco de comandos executados pelo menos uma vez
} while (expressão_booleana);
```
exemplo:

``` .java

/**
* repetição de comandos usando FOR
*/
// Calculando o fatorial de um número:
int numero = 10;
int fatorial = 1;
int i = numero;
while (i > 0)
{
    fatorial = fatorial * i;
    --;
}

System.out.println("fatorial de " + valor + " = " + fatorial);
// Lendo a condição de parada do teclado:
int numero = 0;
while (número < 10)
{
    numero = valorDoTeclado();
}
System.out.println("utilizador digitou um número maior que 10");

```

## Comandos especiais de controle de fluxo: **break** e **continue** 

Os comandos de repetição em Java suportam dois tipos de desvios: o **break** e o **continue**. O **break** faz
com que um ciclo/repetição seja interrompido, enquanto o continue é usado para "saltar" uma execução e continuar
a partir da próxima.

exemplo:

```
// "saltar" a execução No 10 e parando na No 15
for (int i=0; i<20; i++)
{
    if(i == 10)
    {
    continue;
    }
    else if(i == 15)
    {
    break;
    }
    System.out.println("contador: " + i);
}
```

