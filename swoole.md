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
