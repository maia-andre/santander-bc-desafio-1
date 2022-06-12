# Introdução ao Kotlin

Curso: Introdução ao Kotlin - DIO - Instrutora Ana Luísa

**Estrutura da Linguagem**

- Não possui ponto e vírgula
- Não possui operador ternário tradicional
- Type safe e null safe
- Inferência de tipo

Aplicabilidade

- Android nativo
- Mobile multiplataforma (KMM)
- Frontend Web com Kotlin/JS
- Frameworks (Ex: Kvison e Fritz2)
- Backend com target node.js do Kotlin/JS.

**Para praticar:**

[Kotlin Playground: Edit, Run, Share Kotlin Code Online](https://play.kotlinlang.org/)

Tipos de dados

- Int
- Long
- Float
- Double
- Array
- Boolean
- Char
- Byte
- Short
- Null!

Para conversão de dados - Ex.: **.toByte() - Caso a conversão não seja possível, a IDE irá alertar.**

**Declaração de variáveis**

- Var (valor mutável, CamelCase):
    - Variável que pode ter seu valor alterado durante o código;
- Val (valor imutável, CamelCase):
    - Variável que terá somente o valor atribuído;
- Const Val (valor imutável, SNAKE_CASE):
    - Constante cujo valor é atribuído durante compilação.
    

Const Val é usada em um escopo global.

Dentro de uma função, a declaração de Val obtém o mesmo efeito, sem gerar erros.

Uma variável **não pode** ser declarada **sem tipo e sem atribuição**.

Uma variável com inferência de tipo só receberá valores do mesmo tipo que a sua primeira atribuição.

Podemos usar a conversão de valores no momento de atribuir novos valores à variáveis já existentes.

**Nullability**

Qualquer tipo pode ser nulo, porém isso deve ser explicitado na declaração de variável através do uso da interrogação [?];

A inferência de tipo não atribui nullability;

Ex.:

**var day:Int = null** // Erro: Null can not be a value of a non-null type Int.

Atribuindo nullability: **var day:Int? = null**

**Operadores aritméticos**

- Os operadores podem ser chamados tanto como expressão quanto como comando. O resultado será o mesmo.
- A função de soma também funciona para concatenar Strings.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/fa738bd2-79eb-4071-b8ab-5f2f4fa74a5a/Untitled.png)

**Operadores comparativos**

- maior/menor - > <;
- igual - ==
- diferente - ≠ ou !=
- Os comandos compareTo retornam os valores -1 (menor que), 0 (igual) ou 1 (maior). Já os operadores retornam valores booleanos;
- O comando equals retorna um booleano;

**Operadores lógicos**

- E (&&) - expresão1 e/and expressão2
- Ou (||) - expressão1 ou/or expressão2
- Quando utiliza-se o comando, é recomendado colocar a expressão entre parênteses;

**Operadores In e Range**

- Contém (In)
- Não contém (!In)
- range/Faixa de valores (int..int)
- Se valor está presente em uma lista ou uma faixa (range) de valores;
- Range cria um intervalo de valores que inicia no primeiro parâmetro e acaba no segundo.

Ex.:

```kotlin
//teste de operadores in e range
fun main() {
val bingo = listOf(8,6,34,2,13)
var number = (1..34).random()

printIn(number)
printIn(number in bingo)
}
```

Ex.:

```kotlin
//teste de operadores in e range
const val MIN_AGE = 16
const val MAX_AGE = 60
//função principal
fun main() {
	var age = (10..100).random()
	printIn(age)
	printIn(age in MIN_AGE..MAX_AGE)
	printIn(age >= MIN_AGE && age <= MAX_AGE)
}
```

**Manipulação de Strings**

- Strings possuem diversos métodos associados;
- Indexação
    - String como array;
    - First(), last(), String.length, String[index];
- Concatenação
    - Para concatenar duas strings o plus/+ pode ser utilizado;
    - Para concatenar uma variável a uma String, os símbolos ${} devem ser inseridos;
    - Ex: printIn(”${s}, ${name}!”)
- Comparação,
- Formatação;
    - Capitalização de strings
        - capitalize(), toUpperCase(), toLowerCase(), decapitalize()
    - Remoção de espaços
        - trimEnd(), trimStart(), trim()
    - Substituição de caracteres
        - replace(x, y)
    - formatação
        - “padrão ${valor}”.format(valor)
- Pode ser concatena com plus/+;
- Também é tratada como um array de Char;

**Empty x Blank**

Empty e blank são métodos de comparação

- String está vazia (empty), em branco (blank) ou é nula (null) ?

Se o tamanho da string (variável.length) for 0 está empty e blank;

Se o tamanho for > 0 mas todos os caracteres são espaços em branco, está blank mas não empty.

### Funções

Funções no Kotlin são estabelecidas pelo prefixo fun, de function.

- Prefixo **Fun nomeDaFunção(nome:Tipo):TipoRetorno{}**
- Funções anônimas, single-line, inline, extensões, Lambdas, ordem superior;

3 exemplos da mesma função:

```kotlin
private fun getFullName(name:String, lastName:String):String{
		val fullname = "$name $lastName"
		return fullname
}

private fun getFullName(name:String, lastName:String):String{
		return "$name $lastName"
}

private fun getFullName(name:String, lastName:String) = "$name $lastName"

```

**Funções de ordem superior**

Recebem outra função ou lambda por parâmetro;

Bastante úteis para a generalização de funções e tratamento de erros.
