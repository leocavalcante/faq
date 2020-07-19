# Frameworks

# pt-BR

Se você tá com essa dúvida, é melhor usar um pronto.

Frameworks pra PHP são péssimos. Frameworks web tentam resolver propósitos gerais, mas seu problema não é geral, é de algum domínio em específico, então todo aquele boilerplate do framework querendo resolver coisas que você não precisa vai estar lá.

PHP já é uma linguagem muito high-level pra web.

Por isso coisas como micro-frameworks surgiram. São "frameworks" que geralmente só resolvem a parte de rotas e arquitetura MVC e o resto você pode compor conforme a necessidade.

E é justamente em arquitetura que um framework pode te ajudar.

Se você não faz ideia do que tá fazendo ainda, um framework vai te ajudar com arquitetura, se você usa um framework MVC você vai entender como organizar seu código dum jeito MVC de entender.

Mas só em arquitetura? E a parte de segurança, banco de dados etc?

Sim, só em arquitetura porque pras essas outras coisas você pode contar com bibliotecas mesmo, cada uma especializada no problema que você quer resolver e no fim um framework vai ser um punhado de bibliotecas dentro de uma arquitetura pré-definida, ou seja:

Se você tem know-how e está numa posição onde pode tomar decisões de arquitetura, não use frameworks, componha bibliotecas na melhor arquitetura que você analisou pro problema.
Se você tá iniciando e ainda não sabe muito bem o que tá fazendo, use um framework.

Mas mais ainda: se você tiver conhecimento em arquiteturas limpas, o framework vira um mero detalhe, uma coisa que você troca e experimenta sem afetar seu código. Ai ao invés de um fully-bloated como Laravel você vai preferir componentes especializados em problemas, tipo a FastRoute do Nikita Popov pra rotas, a Doctrine pra acesso ao banco de dados, a Flysystem da The PHP League pra storage etc etc... No fim o Laravel é um catadão desses componentes, a diferença é que você vai ter liberdade pra escolher, trocar e organizar da melhor forma pro seu projeto/problema.
