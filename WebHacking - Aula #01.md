# Web Hacking | Aula #01

> Abstract: nesta aula foram abordadas as bases da web, isto é, como funciona a comunicação entre o cliente e o servidor com base em requisições do protocolo HTTP.

1. Tecnologias da Web: 
- Front-End: constituída de arquivos HTML(linguagem de marcação), CSS(linguagem de estilização) e JS(linguagem de programação usada para a comunicação com o servidor, como por exemplo em aplicações dinâmicas com atualizações em tempo-real);
- Back-End: constituído de máquinas(servidores) que transferem as informações para serem renderizadas pelo cliente; usam Python, NodeJS, .NET, Ruby...
- HTTP: é um protocolo de comunicação usado para fazer a ligação entre o Front-End e Back-End. Muitos dos ataques à aplicações são feitos por meio de falhas no HTTP.

## Protocolo HTTP

1. O Protocolo HTTP e seus métodos: 
- GET: usado para ler dados do servidor;
- POST: enviar dados para o servidor;
- PUT: criar/atualizar dados no servidor;
- DELETE: deletar dados no servidor;
- PATCH: atualizar dados no servidor.

2. HTTP: Request / Response:
- Request: requisitado pelo cliente; contém o método HTTP necessário(GET, POST), a página necessária pelo usuário(/admin), o host(google.com) e o tipo de conteúdo(content-type) necessário como resposta(text, html...);
- Response: resposta vinda do servidor; contém o método HTTP necessário(GET, POST), o *status-code* que define se a resposta foi um sucesso, se o conteúdo não foi encontrado entre outras respostas, o tipo de conteúdo(content-type), o ambiente que está rodando no servidor(Apache / CentOS) e por fim o conteúdo que foi requisitado pelo cliente(html...).

3. Status-Code HTTP:
- Respostas de informação (`100`-`199`):
	- 100 Continue: Essa resposta provisória indica que tudo ocorreu bem até agora e que o cliente deve continuar com a requisição ou ignorar se já concluiu o que gostaria;
	- 101 Switching-Protocol: Esse código é enviado em resposta a um cabeçalho de solicitação 					  pelo cliente, e indica o protocolo a que o servidor está alternando;
	- 102 Processing: Este código indica que o servidor recebeu e está processando a requisição, mas nenhuma resposta está disponível ainda;
	- 103 Early-Hints: Este código tem principalmente o objetivo de ser utilizado com o cabeçalho [`Link`](https://developer.mozilla.org/pt-BR/docs/Web/HTTP/Headers/Link "O cabeçalho de entidade Link provém maneiras para serializar um ou mais links em cabeçalhos HTTP. Ele é semanticamente equivalente ao elemento HTML <link>."), indicando que o agente deve iniciar a [pré-carregar](https://developer.mozilla.org/pt-BR/docs/Web/HTML/Preloading_content) recursos enquanto o servidor prepara uma resposta.
- Respostas de sucesso (`200`-`299`):
	- 200 OK: Esta requisição foi bem sucedida. O significado do sucesso varia de acordo com o método HTTP;
	- 201 Created: A requisição foi bem sucedida e um novo recurso foi criado como resultado. Esta é uma tipica resposta enviada após uma requisição POST.
- Redirecionamentos (`300`-`399`):
	- 300 Multiple Choice: A requisição tem mais de uma resposta possível. User-agent ou o user deve escolher uma delas. Não há maneira padrão para escolher uma das respostas.
	- 301 Moved Permanently: Esse código de resposta significa que a URI do recurso requerido mudou. Provavelmente, a nova URI será especificada na resposta. 
- Erros do cliente (`400`-`499`):
	- 400 Bad Request: Essa resposta significa que o servidor não entendeu a requisição pois está com uma sintaxe inválida.
	- 401 Unauthorized: Embora o padrão HTTP especifique "unauthorized", semanticamente, essa resposta significa "unauthenticated". Ou seja, o cliente deve se autenticar para obter a resposta solicitada;
	- 404 Not Found: O servidor não pode encontrar o recurso solicitado. Este código de resposta talvez seja o mais famoso devido à frequência com que acontece na web. 
- Erros do servidor (`500`-`599`):
	- 500 Internal Server Error: O servidor encontrou uma situação com a qual não sabe lidar;
	- 502 Bad Gateway: Esta resposta de erro significa que o servidor, ao trabalhar como um gateway a fim de obter uma resposta necessária para manipular a requisição, obteve uma resposta inválida.

## DevTools: 

Acessando, por meio de atalhos como ctrl+shift+I ou F12, o modo desenvolvedor é possível entender como funciona na prática a comunicação entre o cliente e o servidor por meio de métodos HTTP. *Por conta da grande quantidade de recursos gráficos e prática não incluirei aqui todos os detalhes do que é visto na aula*

## Burp-Suite: 
Burp Suite é um software desenvolvido em Java pela PortSwigger, para a realização de testes de segurança em aplicações web. Ele tem as seguintes features: 

- Target: faz o mapeamento de todos os arquivos e estrutura de pastas do alvo;
- Proxy: ele se coloca entre a comunicação do cliente e o servidor para interceptar e entender como funcionam os métodos HTTP do alvo;
- Repeater: repete a requisição feita pelo cliente quantas vezes quisermos;
- Intruder: faz brute-force em sistemas de autenticação.



