---
TOCTitle: Aquisição da Licença de Utilização
Title: Aquisição da Licença de Utilização
ms:assetid: '0b6cde34-418a-4dee-9d27-b65b93b535ac'
ms:contentKeyID: 18123935
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc720194(v=WS.10)'
---

Aquisição da Licença de Utilização
==================================

Para consumir conteúdo protegido pelo RMS, um utilizador tem de adquirir uma licença de utilização através do serviço de licenciamento do RMS. A figura seguinte ilustra o processo de pedido e recepção de uma licença de utilização.

![](images/Cc720194.37b8d28c-9749-4e81-bc6a-22692fefb8b6(WS.10).gif)

O processo de aquisição de uma licença de utilização envolve os seguintes passos:

1.  O utilizador recebe um ficheiro protegido através de um canal de distribuição típico e, em seguida, abre-o com uma aplicação activada pelo RMS. Se o utilizador não tiver um certificado de conta de direitos no computador ou dispositivo actual, terá de adquirir um.
2.  A aplicação activada pelo RMS envia um pedido de licença de utilizador ao servidor que emitiu a licença de publicação para o conteúdo protegido. O pedido inclui o certificado de conta de direitos do utilizador (que contém a chave pública do utilizador) e a licença de publicação (que contém a chave simétrica do conteúdo).
    Uma licença de publicação emitida por um certificado de licenciador de clientes inclui o URL do servidor que emitiu o certificado. Neste exemplo, o pedido para uma licença de utilização vai para o servidor que emitiu o certificado de licenciador de clientes e não para o computador que emitiu a licença de publicação.
3.  O servidor de licenciamento verifica se o utilizador está autorizado, se consta da licença de publicação e, em seguida, cria uma licença de utilização. O servidor valida o certificado de conta do utilizador e, em seguida, determina quais as permissões concedidas ao utilizador, seja directamente ou como um membro de um grupo a quem tenham sido concedidas permissões.
    O servidor desencripta a chave de conteúdo simétrica utilizando a chave privada do servidor, volta a encriptá-la, utilizando a chave pública do destinatário, e adiciona-a à licença de utilização. Este passo assegura que apenas o utilizador em causa possa desencriptar a chave de conteúdo e o conteúdo protegido.
    O servidor adiciona todas as condições relevantes à licença de utilização, como, por exemplo, uma aplicação ou a exclusão de uma versão do Windows. Estas condições são impostas pelo cliente na altura em que a licença de utilização é associada ao conteúdo protegido pelo RMS.
4.  Quando a validação estiver concluída, o servidor de licenciamento devolve a licença de utilização ao computador cliente do utilizador.
