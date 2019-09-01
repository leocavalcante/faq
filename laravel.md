# Laravel

## pt-BR

O memory footprint do Laravel é altíssimo e não é um trade-off que pode ser considerado justo, como em alguns casos da JVM que o memory footprint é alto, mas entrega CPU; e um dos fatores que contribui pra ele ser alto é justamente ser apenas mais camadas de abstração sobre camadas de abstração, é mais um framework sendo bootado a cada request (preloading no PHP 7.4 visa acabar com isso) e mais objetos consumindo recursos na máquina em troca de "facilidade"... Tenho algumas máximas: NADA na área de tecnologia é bala-de-prata e TUDO é questão de avaliar os trade-offs; se essa facilidade que o Laravel entrega em troca de acabar com sua RAM é bom pra você/sua equipe/seu projeto, então boas, manda bala; só não vai achar ruim depois quando o projeto crescer e você só conseguir escalar verticalmente (adicionando mais recursos - o jeito mais caro), ainda mais depois de usar um framework com foco em projetos monólitos.
Isso falando de performance, claro, que é o tema dessa sub-thread, mas a gente pode falar sobre as más práticas que acabam sendo adotadas por coisas como "Facades".
