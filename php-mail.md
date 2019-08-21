# PHP's `mail()` function

## pt-BR

A função [`mail()`[1]](https://www.php.net/manual/en/book.mail.php) do PHP vai usar o [MTA (Message Transfer Agent)[2]](https://en.wikipedia.org/wiki/Message_transfer_agent) configurado por padrão na máquina em que ele está sendo executado.
Geralmente é o [sendmail[3]](https://en.wikipedia.org/wiki/Sendmail), mas raramente ele ou outro MTA vai estar configurado corretamente, principalmente em hospedagens compartilhadas e no Windows.
Outro ponto é que mesmo que esteja devidamente configurado na sua máquina de casa, de desenvolvimento, a maioria dos clientes de e-mail vão bloquear a mensagem porque o remetente vem de um IP doméstico.
A melhor forma de enviar e-mails, não só no PHP, é usando um serviço de SMTP relay como o [SendGrid[4]](https://sendgrid.com/), [Mailgun[5]](https://www.mailgun.com/) ou [SMTP2GO[6]](https://www.smtp2go.com/).
Para acessar esses serviços através do PHP, você chama as APIs HTTP deles (geralmente é o método recomendado) usando um client HTTP como [Guzzle[7]](http://docs.guzzlephp.org/en/stable/) ou [cURL[8]](https://www.php.net/manual/en/book.curl.php).
Ou se conecta direto no SMTP Relay Server deles usando um client de SMTP como [SwiftMailer[9]](https://swiftmailer.symfony.com/) e [PHPMailer[10]](https://github.com/PHPMailer/PHPMailer).

- [1] https://www.php.net/manual/en/book.mail.php
- [2] https://en.wikipedia.org/wiki/Message_transfer_agent
- [3] https://en.wikipedia.org/wiki/Sendmail
- [4] https://sendgrid.com/
- [5] https://www.mailgun.com/
- [6] https://www.smtp2go.com/
- [7] http://docs.guzzlephp.org/en/stable/
- [8] https://www.php.net/manual/en/book.curl.php
- [9] https://swiftmailer.symfony.com/
- [10] https://github.com/PHPMailer/PHPMailer
