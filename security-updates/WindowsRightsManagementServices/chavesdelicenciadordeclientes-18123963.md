---
TOCTitle: Chaves de Licenciador de Clientes
Title: Chaves de Licenciador de Clientes
ms:assetid: '28781125-2692-4ff9-99b1-e09227d72966'
ms:contentKeyID: 18123963
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc720221(v=WS.10)'
---

Chaves de Licenciador de Clientes
=================================

Os autores podem adquirir certificados de licenciador de clientes para publicarem conteúdo protegido pelo RMS quando não estão ligados à rede activada pelo RMS. Um certificado de licenciador de clientes tem um par de chaves RSA de 1024 bits.

O cliente do RMS utiliza a chave pública do certificado de licenciador de clientes quando emite uma licença de publicação para executar as seguintes tarefas:

-   Encriptar a chave de conteúdo simétrica.
-   Assinar licenças de publicação que são emitidas localmente enquanto o utilizador não está ligado à rede.
