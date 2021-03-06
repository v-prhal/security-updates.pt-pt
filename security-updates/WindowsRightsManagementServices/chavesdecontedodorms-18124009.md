---
TOCTitle: Chaves de Conteúdo do RMS
Title: Chaves de Conteúdo do RMS
ms:assetid: '63c814bf-2809-477e-a2db-d90370442075'
ms:contentKeyID: 18124009
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc720284(v=WS.10)'
---

Chaves de Conteúdo do RMS
=========================

Quando um autor publica conteúdo protegido pelo RMS, uma aplicação activada pelo RMS cria uma chave de conteúdo simétrica e utiliza-a para desencriptar o conteúdo. O RMS utiliza a norma de encriptação avançada (AES, Advanced Encryption Standard) para criar a chave de conteúdo.

A chave de conteúdo é incluída na licença de publicação e encriptada com a chave pública do servidor do RMS emitida pela licença.

Quando esse servidor recebe um pedido de licença de utilização, desencripta a chave de conteúdo com a chave privada do servidor e, em seguida, volta a encriptar a chave de conteúdo com a chave pública de utilizador (a qual é recebida como parte do conteúdo). A chave de conteúdo fica, assim, contida na licença de utilização.
