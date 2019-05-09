# PHP vs Node.js

## pt-BR

Essa comparação é bem comum, mas não é exata. PHP é uma linguagem e Node.js é uma runtime. Como você citou uso de recursos, como CPU e I/O (requests/segundo), então imagino que queira comparar runtimes:

A implementação mais comum pro PHP é a Zend Engine via PHP-FPM atrás de um web server como (Nginx e Apache), nesse quesito o Node.js acaba sendo melhor mesmo por causa da sua natureza em lidar com requisições de forma assíncrona através do pattern reactor (implementar um event-loop), porém de forma single-thread, ou seja, se um processo desse loop demorar na CPU, todos os outros no loop terão esse delay também.

Porém, da mesma forma que o Node.js é uma forma "nova e diferente" de rodar JavaScript, tipo rodar ele fora do browser e permitir web-servers+backend, exite para o PHP forma novas e diferentes também e que também implementam o pattern reactor e permite que as requisições sejam manipuladas de forma assíncrona. O melhor exemplar é o Swoole que inclusive, pra concorrência, implementa co-rotinas baseadas nas Go-routines da Go.

Tendo isso claro, entenda que comparar Node.js com o Swoole é o mais justo, não com o PHP; e aí o Node.js perde feio, porque o Swoole além de suportar muito mais requisições por segundo ele é multi-thread, ele usa muito melhor os recursos de CPU (vai melhor mais ainda com o JIT do PHP 8) e de forma paralela, em mais de um thread do processador.

O resultado disso? É 4º "web framework" mais rápido segundo os benchmarks da TechEmpower: https://www.techempower.com/benchmarks/ (faz o PHP ser a única linguagem de script nas top 30) e em comparação com o Node.js da um baile:

![TechEmpower printscreen](/static/php-vs-nodejs.png)
