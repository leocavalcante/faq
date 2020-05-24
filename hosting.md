# Hosting

## Hosting providers vs. VPSes

### pt-BR

O que pega aí é o 'formulário'.
Se forem páginas 100% estáticas da pra por em vários lugares. Firebase Hosting é uma boa, não ficar open-source como no GitHub pages.
Mas a computação desse formulário vai precisar de algo 'não-estático'. Tem planos free forever na Azure e na GCP, mas você ainda vai precisar de um cartão de crédito internacional, mesmo que a fatura não venha ou venha zerada.

Se você trabalha com isso, vale a pena pegar uma VPS em major players como AWS, Azure, DigitalOcean, Google Cloud etc e estudar um mínimo de DevOps, o mínimo suficiente pra pelo menos suas próprias aplicações e configurações de ambiente. Se você não é programador, não trabalha com desenvolvimento, mas tem um site pra hospedar, aí coisas como Locaweb e Hostgator podem fazer sentido.

#### Free

Se for um site estático (só html, css, js, imagens etc) sem processamento no servidor, então tem mais opções: tem o GitHub pages, Netlify e ZEIT Now, entre outras. Se você precisar de algo no servidor, falar com banco de dados, websockets, filas etc, então pode experimentar o Heroku e se tiver um cartão de crédito internacional da pra criar contas nas AWS (gratuito por 12 meses), na Azure e na Google Cloud.

#### Self-hosted PaaS on a major player

De hospedagem é complicado. Hoje, pra mim já é de-facto ir pra major player num cloud tipo AWS, DigitalOcean, Azure e GCP. Aí se você não manja muito de sysadmin/devops, pega um PaaS self-hosted, vai ser tipo seu próprio Heroku, você vai conseguir subir as aplicações usado interface gráfica ou com um um simples comando no terminal, vai conseguir configurar https também com um clique e se pegar um PaaS com marketplace como o CapRover, vai poder subir bancos (MySQL, Postgres, MongoDB...) com um clique. Se for apps conhecidos tipo WordPress e Hasura também vai ter o one-click install pra eles. Vale muito a pena, fora poder linkar outros nós e montar um cluster se a coisa escalar.
Minha dica é CapRover num droplet da DigitalOcean, tem até no marketplace deles pra subir um direto.
