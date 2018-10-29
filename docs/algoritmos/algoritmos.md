# Algoritmos

## Introdução

Considere o seguinte problema: descobrir a altura da pessoa mais alta de um grupo de pessoas e suponha que estas
pessoas estão em fila. Como devemos resolver este problema? 

![Fila de Pessoas](../images/algoritmos/fila_pessoas.png)
*Fila de Pessoas.*

Primeiro deve-se elaborar uma estratégia/procedimento para resolver este problema. Uma possivel estratégia simples seria fazer o seguinte:

1. Obter a altura da primeira pessoa e guarda-la como altura máxima até ao momento. 
1. Percorrer cada pessoa da fila apartir da segunda pessoa e fazer os seguintes passos:
    1. Obter a altura da pessoa actual. Esta será a altura actual.
    1. Comparar a altura actual com a altura máxima do momento. Esta comparação pode resultar em 3 possibilidades: a altura actual é menos, é igual ou é maior.
    1. Se a altura actual for maios, então o valor da altura máxima passa a ser igual à altura actual.
    
Nesta estratégia temos que percorrer todas as pessoas da fila até se ter a certeza que foi encontrada a pessoas mais alta da fila, porque a unica invariante que se tem a cada passo, é que até ao momento todas as pessoas percorridas tem altura igual ou menor que um determinado número.

Mas será que esta estratégia é a melhor? Caso as pessoas tivessem organizadas de uma forma especial, era possivel criar alguma estratégia melhor? 

## Noção Formal de Algoritmo 

A noção de algoritmo surgiu pela primeira vez através de um matemático
árabe [Muḥammad ibn Mūsā al-Khwārizmī](https://pt.wikipedia.org/wiki/Al-Khw%C4%81rizm%C4%AB), que associou este termo à capacidade de um computador executar procedimentos para a resolução de problemas. Na área das
ciências da computação, a palavra ‘algoritmo’ refere-se a um procedimento
que pode ser implementado e executado por um programa de
computador.
Um algoritmo representa uma sequência finita e não ambígua de instruções elementares bem definidas, conducente à solução de um determinado problema, cada uma das quais pode ser executada mecanicamente
numa quantidade finita de tempo. Neste sentido, um algoritmo é um conjunto de instruções que podem ser mecanicamente executadas num período de tempo, de modo a resolver um determinado problema.
Um programa de computador envolve a definição de um algoritmo para a resolução de um problema. Um algoritmo é representado através de expressões simbólicas que utilizam estruturas de dados de modo a descrever
e a encontrar a solução de problemas do mundo real. As estruturas de dados representam de modo simbólico entidades e objectos do mundo real e definem a parte estática de um algoritmo. A manipulação
das estruturas de dados através de declarações e instruções precisas de controlo definem a parte dinâmica de um algoritmo. Este conjunto de estruturas de dados e de controlo constituem formalmente um algoritmo para a resolução de problemas.


## Algoritmo Recursivo

Um objeto é denominado recursivo quando sua definição é parcialmente feita em termos dele próprio.  
A recursividade (ou recursão) é encontrada principalmente na matemática, mas encontra-se presente em algumas situações do quotidiano. Por exemplo, quando um objeto é colocado entre dois espelhos planos paralelos e frente a frente surge uma imagem recursiva, porque a imagem do objeto que está refletida num espelho passa a ser o mesmo objeto a ser refletido no outro espelho e, assim, sucessivamente.  
Em programação, a recursividade é um mecanismo útil e poderoso que permite a uma função chamar a si própria directamente ou indiretamente, ou seja, uma função é dita recursiva se ela contém pelo menos uma chamada explícita ou implícita a si própria.  
A idéia básica de um algoritmo recursivo consiste em diminuir sucessivamente o problema em um sub-problema menor ou  simples, até que o tamanho ou a simplicidade do problema reduzido permita solucioná-lo de forma direta, sem recorrer a si mesmo. Quando isso ocorre, diz que o algoritmo atingiu uma condição de paragem, a qual deve estar presente em pelo menos um local dentro algoritmo. Sem esta condição o algoritmo não pára de invocar-se a si próprio, até dar um error de execução.    
Para todo o algoritmo recursivos existe um outro correspondente iterativo (não recursivo), que executa a mesma tarefa. Implementar um algoritmo recursivo (partindo de uma definição recursiva do problema) em uma linguagem de programação de alto nível como Java é simples e quase imediato, pois o seu código é praticamente transcrito para a sintaxe da linguagem.   
Por essa razão,em geral, os algoritmos recursivos possuem código mais claro (legível) e mais compacto do que oscorrespondentes iterativos.  
Entretanto, também há desvantagens: i) algoritmos recursivos normalmente  consomem mais recursos (especialmente memória) do computador, logo tem tendencia de apresentar um desempenho inferior aos iterativos; e ii) algoritmos recursivos são mais difíceis de serem fazer degub, especialmente quando existem muitas chamadas em espera na fila de execução.


```.java

static void funcRecursiva() 
{
    if (<condição_de_paragem>)
        return <resposta>;
    else 
        return funcRecursiva(); 
}
```

### Exemplo: Função Factorial

O factorial de 3 e 6 podem ser calculados da seuinte forma:
 
 *  **3! = 3x2x1 = 6**
 * **6! = 6x5x4x3x2x1 = 720**
 
 Da forma genérica, podemos calcular o factorial : **n!=nx(n-1)x(n-2)x...x1**
 
```.java

public class app 
{
    static long factorial(long n) 
    {
        long fat = 1;
        for(long i = n; i > 1; i--) 
        {
            fat *= i; 
        }
        return fat; 
    }

    public static void main(String s[]) 
    {
        System.out.println(factorial(3)); 
        System.out.println(factorial(6)); 
        System.out.println(factorial(10)); 
    } 

}

```

Uma outra forma de calcular o factorial é:

*  **3! = 3x2!= 6**
* **6! = 6x5! = 720**

Da forma genérica, podemos calcular o factorial : **n!=nx(n-1)!**

Pela equação anterior, pode-se deduzir que qualquer factorial pode ser calcualdo com o seu valor multiplicado pelo factorial do seu valor subtraido por um, ou seja, pode-se mudar a função anterior **factorial** em java para a seguinte:

```.java

public class app 
{
    static long factorial(long n) 
    {
        return n * (n-1)!;
    }
}

```

Claro que caso se pretenda compilar esta nova função, vai dar erro, porque não existe em Java **(n-1)!**. Por isso como podemos calcular o **(n-1)!**? A função anterior não tem esse objectivo? Então podemos utilizar ela propria para calcular **(n-1)!**.

```.java

public class app 
{
    static long factorial(long n) 
    {
        return n * factorial(n-1);
    }
}

```

**MAS** temos um erro grave nesta nova função: se a função esta invokar ela proria, quando é que ela termina e retorna o resultado?  
Como foi explicado anteriormente, toda a função recursiva necessita de uma condição de paragem, por isso é necessario adicionar essa condição à função de factorial.

```.java

public class app 
{
    static long factorial(long n) 
    {
        if(n <= 1)
            return 1;
        else
            return n * factorial(n-1);
    }

}

```
