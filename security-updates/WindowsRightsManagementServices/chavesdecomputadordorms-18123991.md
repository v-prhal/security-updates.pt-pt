---
TOCTitle: Chaves de Computador do RMS
Title: Chaves de Computador do RMS
ms:assetid: '56e59ec2-f681-4ca2-98c7-72218ab9e9d9'
ms:contentKeyID: 18123991
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc747572(v=WS.10)'
---

Chaves de Computador do RMS
===========================

Um computador cliente do RMS SP1 tem um par de chaves de RSA de 1024 bits denominado chaves de computador.

A chave pública de computador é utilizada na encriptação de uma chave privada de certificado de conta de direitos. O certificado de computador do RMS contém a chave pública de computador. O cofre contém a chave privada de computador que é utilizada na desencriptação do certificado de conta de direitos para permitir a utilização da chave privada de utilizador.
