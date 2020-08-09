# HTML is a Programming Language

## pt-BR
### É uma linguagem de marcação
Linguagens de marcação também são de programação. Ser de marcação não diminui nem exclui o fato de ser de programação.
Linguagens de marcação são um subconjunto das linguagens de programação, assim como um quadrado é um retângulo e ele não deixa de ser um retângulo por ser um quadrado.
Por exemplo, a CFML é de marcação e você faz até um servidor web com ela: https://en.wikipedia.org/wiki/ColdFusion_Markup_Language ou mais um exemplo: a LaTexX que é até Turing-complete: https://en.wikipedia.org/wiki/LaTeX

### Você não faz funções
Isso não faz ser mais ou menos linguagem de programação. Em Assembly, por exemplo, e algumas implementações de BASIC, você não escreve funções. Assembly não é linguagem de programação também?

### Você não cria algorítimos
Ter a habilidade de criar algorítimos e estruturas de controle de fluxo, são características de uma parte das linguagens de programação, mas não do todo; nem toda linguagem precisa ser GPL e Turing-complete, existem as DSLs, Declarativas, Totais etc, que é o universo onde o HTML se encaixa. E DSLs Totais são linguagens que não precisam ter o "poder de fogo" de implementar algorítimos, elas servem um propósito bem especifico, por exemplo a SQL.

### Você não cria condições/estruturas de fluxo (if, for, while...)
Programação declarativa é justamente poder expressar a lógica de uma computação sem descrever o fluxo de controle (for, if, while).
Fora que qual é a diferença de um `<noscript></noscript>` pra um `if (!script) {}`? rs Um é declarativo e o outro não, só isso.

### Não é Turing-complete
Linguagens de programação não precisam ser Turing-complete, nesse caso são chamadas de linguagens Totais e não deixam de ser de programação por causa desse fato. Isso só significa que elas terminação provável e não sofrem do halting-problem.
https://en.wikipedia.org/wiki/Total_functional_programming

### More
O que acontece é que HTML é uma DSL, por isso não tem implementações extravagantes pra ela, apenas as que os navegadores usam como Blink, Gecko, WebKit... Mas da mesma forma que JS se tornou muito mais poderoso agora com uma nova runtime, o Node.js, nada impede de haver um Node.html que roda HTML no servidor e faz coisas como a CFML.

### Another try
Geralmente, quando a pessoa inicia nesse meio de programação, ela começa aprendendo estruturas para controle de fluxo de dados de forma imperativa, até chamam isso de "lógica de programação" e isso acaba sendo difundido erroneamente como o que é A programação, então linguagens que não implementam esse modelo, acabam sendo vistas como não-programação.
Mas é uma visão muito simplista (normal pra quem tá aprendendo), a ideia de programação vai mais além e existem vários outros paradigmas além do imperativo, varias outras formas de pensar em como instruir um computador. O HTML é uma linguagem de programação declarativa, ser uma linguagem que usa markup como sintaxe, não exclui o fato de ainda de ser de programação; outros exemplos são TeX e CFML.
De começo, pra não passar "vergonha" no meio da garotada, fala que não é rsrs, mas continua estudando, indo atrás, abrindo a cabeça e vendo outras linguagens e paradigmas além do imperativo que um dia esse estalo vem ;) vou deixar umas referências como comentário do meu comentário:

### CFML example

Ser de marcação não siginifica que não é programação, uma coisa não exclui a outra. Linguagens markup são um subconjunto. Por exemplo:
```cfml
<!--- temperature.cfc --->
<cfcomponent>
  <cffunction name="FtoC" access="public" returntype="numeric">
    <cfargument name="fahrenheit" required="yes" type="numeric" />
    <cfset answer= (fahrenheit - 32)*100/180 />
    <cfreturn answer />
  </cffunction>
</cfcomponent>
<!--- test.cfm --->
<cfset fDegrees = 212 />
<cfinvoke component="temperature" method="FtoC" returnvariable="result">
  <cfinvokeargument name="fahrenheit" value="#fDegrees#" />
</cfinvoke>
<cfoutput>#fDegrees#&deg;F = #result#&deg;C</cfoutput> <br />
```
É um programa que converte farenheight para celsius, só com "tags", puro markup, essa linguagem se chama ColdFusion Markup Language.

---
- https://www.quora.com/What-is-the-difference-between-programming-languages-markup-languages-and-scripting-languages-in-terms-of-how-they-manipulate-create-use-data-What-are-the-differences/answer/Quildreen-Motta
- https://www.youtube.com/watch?v=4A2mWqLUpzw
- https://www.youtube.com/watch?v=-csXdj4WVwA
- https://twitter.com/PeterLodewijk/status/1047392522102890496
- https://www.youtube.com/watch?v=grr09e_cH_c
