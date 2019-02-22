# What about Swoole

## pt-BR
Diferente de Node.js, Nginx e Tornado (Python), o Swoole montou o modelo assíncrono dele, ainda basead em event-loop, mas em multi-thread ao invés de ser single-node.
E o Swoole tem um modelo de concorrência baseado em co-rotinas, como a Go.

Ao invés de rodar atrás de um servidor web/CGI, como é feito normalmente com PHP, o Swoole roda direto na CLI e cria processos de acordo com a quantidade de núcleos no processador
![Swoole Model](https://www.swoole.co.uk/images/how-swoole-works.png)

### O benchmark da TechEmpower
É uma comparação de desempenho entre frameworks web que fazem coisas reais do mundo real, como serialização JSON, acesso ao banco de dados e composição templates do lado do servidor etc.
As implementações são todas open-source, enviadas pela comunidade; se você acha que seu framework pode ser mais rápido, só enviar um PR :) E as configurações já são todas baseadas num ambiente de produção, não de desenvolvimento.
