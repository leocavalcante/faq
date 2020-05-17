# Should I use it pure or with a framework?

## pt-BR

Se você estiver numa posição em que pode tomar decisões de arquitetura, mas principalmente, tem know-how pra isso, não vejo problema nenhum fazer "puro", é melhor mesmo (e se você realmente tem experiência com isso, já sabe que é melhor, não estaria fazendo essa pergunta) porque o problema é quando a pessoa acha que sabe o que tá fazendo; aí é melhor usar um framework pra te ajudar com relação às questões organizacionais.

Mas mais ainda: se você tiver conhecimento em arquiteturas limpas, o framework vira um mero detalhe, uma coisa que você troca e experimenta sem afetar seu código. Ai ao invés de um fully-bloated como Laravel você vai preferir componentes especializados em problemas, tipo a FastRoute do Nikita Popov pra rotas, a Doctrine pra acesso ao banco de dados, a Flysystem da The PHP League pra storage etc etc... No fim o Laravel é um catadão desses componentes, a diferença é que você vai ter liberdade pra escolher, trocar e organizar da melhor forma pro seu projeto/problema.

https://youtu.be/DuB6UjEsY_Y
