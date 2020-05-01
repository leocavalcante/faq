# What about Swoole

## pt-BR
Diferente de Node.js, Nginx e Tornado (Python), o Swoole montou o modelo assíncrono dele, ainda basead em event-loop, mas em multi-thread ao invés de ser single-node.
E o Swoole tem um modelo de concorrência baseado em co-rotinas, como a Go.

O forma mais comum de rodar PHP tem sido sob a CGI de um web server (Apache/Nginx/IIS/etc); que é basicamente: o web server recebe uma requisição, percebe que ela é um PHP então delega isso pro interpretador do PHP que por sua vez roda o script e devolve o que teve de output de volta pro web server, que devolve pra quem fez a requisição (um browser, por exemplo).

### Como se compara ao Node.js
Só que da mesma forma que tiraram o JavaScript do contexto do browser e colocaram uma camada de APIs (Node.js) em volta da sua engine (V8), o Swoole faz de forma similar com o PHP, só que: de dentro pra fora - vou tentar explicar - a engine é a mesma, ainda é a Zend Engine, assim como no Node.js ainda é a V8, só que ao invés de se propor a ser um bootstraper como o Node.js, a Swoole é um extensão pro próprio PHP que espera ser invocada, o controle de fluxo é o contrário, o Node.js chama seu JS, mas nesse caso, seu PHP que chama a Swoole (nada é bala de prata, essa inversão de controle vai ter seus prós e contras e foi a forma que o pessoal do Swoole achou melhor); só que no fim, a ideia é mesma, colocar os ambientes de execução (V8/Zend Engine) sob uma camada de eventos em loop (Node.js/Swoole) e fazer as linguagens (JS/PHP) terem um comportamento com I/O não bloqueante (assíncrono). Com a grande vantagem pro Swoole aqui que é fazer isso usando multi-thread ao invés de single-thread como o Node.js.


Ao invés de rodar atrás de um servidor web/CGI, como é feito normalmente com PHP, o Swoole roda direto na CLI e cria processos de acordo com a quantidade de núcleos no processador
![Swoole Model](https://www.swoole.co.uk/images/how-swoole-works.png)

### O benchmark da TechEmpower
É uma comparação de desempenho entre frameworks web que fazem coisas reais do mundo real, como serialização JSON, acesso ao banco de dados e composição templates do lado do servidor etc.
As implementações são todas open-source, enviadas pela comunidade; se você acha que seu framework pode ser mais rápido, só enviar um PR :) E as configurações já são todas baseadas num ambiente de produção, não de desenvolvimento.

### Misc

Bom, quando outra linguagem de script tiver multi-task preemptivo implementado por green-threads num modelo de co-rotinas e concorrência baseada em CPS tudo isso sob um scheduler multi-thread... aí a gente conversa; por enquanto vou de PHP mesmo que nesse cenário tá batendo até em .NET Core.

### 5o5

#### Negativos

1. Só funciona em Unix então você precisa de Docker ou WSL se desenvolve no Windows e eu acho que isso é uma puta barreira pra iniciantes
2. O modelo de corotinas pra resolver concorrência é o mais díficil, IMHO, e essas trocas de paradigmas custam muitas calorias, nosso cérebro tende evitar
3. Documentação muito pobre ainda e o que tem é em mandarim tem que saber se virar vendo os sources, testes e exemplos
4. Comunidade engatinhando, não vai ter trocentos links de Swoole com trocentas formas de usa-lo em trocentos idiomas como é com um Laravel e WordPress da vida
5. Pessoas e infra, isso é muito importante pra decisão de stack em muitas empresas, como ficaria trazer gente pro time e como é o deploy disso, tipo, não vai rodar no compartilhado da Locaweb.
(esses 3 ultimos pontos estão meio que interligados, se eu pensar em coisa melhor eu posto aqui)

#### Positivos

6. I/O não-bloqueante, acho que não tem como fazer web mais da outra forma.
7. Performance é absurda, põe PHP do lado de Go, .NET e JVM
8. Raw TCP! Implementação de servers Http, websockets até de Redis (server mesmo, não client) são possíveis, games servers tipo segurar um MMO, WebRTC etc
9. Usar todos os cores da máquina sem precisar fazer nada explicitamente pra isso acontecer, o próprio scheduler da Swoole distribui as corotinas entre workers que estão divididos entre as CPUs (o video do Akita explica isso muito bem, é o mesmo esquema de Go e Erlang)
10. Ainda é PHP, todo know-how que você já tem em PHP, toda sua equipe de devs PHP, ganhando esse poderio todo isso é deveras interessante pra empresas grandes, é o que motivou Facebook a fazer Hack/HHVM e Vimeo a fazer Psalm, por exemplo, uma ferramenta pra devs PHP ao invés de trocar de linguagem
