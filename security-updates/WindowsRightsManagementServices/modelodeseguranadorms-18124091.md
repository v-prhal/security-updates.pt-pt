---
TOCTitle: Modelo de Segurança do RMS
Title: Modelo de Segurança do RMS
ms:assetid: '665db831-366d-4dca-9bb3-cc2912481fe1'
ms:contentKeyID: 18124091
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc747598(v=WS.10)'
---

Modelo de Segurança do RMS
==========================

Durante o funcionamento, o RMS obtém acesso a diversos recursos, incluindo o servidor de bases de dados, o Active Directory, a fila de mensagens e o disco rígido local. O programa de configuração do RMS cria e expõe também determinados recursos necessários ao respectivo funcionamento, tal como entradas SOAP, páginas Web, filas de mensagens de registo, etc. O programa de configuração do RMS configura as DACL nos recursos que cria e expõe, configurando também a autenticação IIS para cada recurso.

Esta secção fornece informações sobre a forma como o RMS configura a segurança para os recursos utilizados e como o RMS obtém acesso aos recursos durante as diversas fases das operações executadas: configuração, aprovisionamento e normal.

Esta secção trata de:

-   [Grupos de Segurança do RMS](https://technet.microsoft.com/25749a83-8c12-48ec-96ad-296d31fd55d4)
-   [Modos de Segurança do RMS](https://technet.microsoft.com/d7792293-5bb2-4232-9d48-e81e87ab6219)
-   [Segurança Durante a Configuração do RMS](https://technet.microsoft.com/0a3d40b2-f27e-4e63-baff-a9c8433f5f91)
-   [Segurança Durante o Aprovisionamento](https://technet.microsoft.com/9f1282c5-5642-4870-a9a4-c3a485f8ff76)
-   [Segurança Durante a Utilização Normal do RMS](https://technet.microsoft.com/98f3d584-6320-4aa1-9959-7133cfdb6df7)
