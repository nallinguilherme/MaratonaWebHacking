# Web Hacking | Aula #02

> ABSTRACT: nessa aula foram abordados os conteúdos de serialização e desserialização assim como programação orientada a objetos(POO).

## Programação Orientada a Objetos:

Chamamos de Programação Orientada a Objetos a representação de um objeto, com suas funcionalidades, métodos, características e particularidades por meio de um bloco de código.

- **Serialização:** é o método pelo qual objetos são transformados em blocos de código(binários) e posteriormente gravados em arquivos, banco de dados, cookies;
- **Desserialização:** é o método pelo qual objetos são retirados de um banco de dados, arquivos, transformados novamente em blocos de código a fim de voltá-los a sua forma natural de objeto.

```php
<?php

Class Celular{
	public $celular = "preto";
	public $modelo = "A50";

	public function ligar(){
		echo "[+] LIGANDO...";
	}
	public function enviarMensagem(){
		echo "[+] ENVIANDO MENSAGEM...";
	}
}

$meu_celular = new Celular();
echo serialize("$meu_celular");
```
*Nesse código é possível perceber como funciona o processo de criação de um objeto em PHP e com a função nativa "serialize()" como a serizalização do objeto é guardada no banco de dados por exemplo*

```bash
O:7:"CELULAR":2:{...} // objeto após a serialização
```

Portanto, modificando o objeto serializado é possível encontrar vulnerabilidades no sistema já que existem parâmetros nesse objeto que identificam o usuário de certas maneiras como *user ou admin*.

No vídeo é usado um laboratório da PortSwigger para teste de vulnerabilidades com serialização insegura no seguinte link: [PortSwigger Academy](https://portswigger.net/web-security)

