---
TOCTitle: 'Definir Permissões no Ficheiro do Serviço de Pré-inscrição'
Title: 'Definir Permissões no Ficheiro do Serviço de Pré-inscrição'
ms:assetid: '737bb69b-fe26-4057-9569-e632f7bbf295'
ms:contentKeyID: 18124041
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc747627(v=WS.10)'
---

Definir Permissões no Ficheiro do Serviço de Pré-inscrição
==========================================================

O serviço de pré-inscrição é executado no servidor de certificações de raiz e inscreve um servidor de licenciamentos durante o aprovisionamento. Por predefinição, o serviço de pré-inscrição permite aceder apenas à conta de sistema local que está no servidor de certificações de raiz. Para aprovisionar um servidor de licenciamentos, deve iniciar a sessão no servidor de licenciamentos com uma conta do tipo referido. Em alternativa, um administrador local deverá, no servidor de certificações de raiz, modificar a DACL no ficheiro do serviço de pré-inscrição, SubEnrollService.asmx, de forma a conceder acesso à conta de utilizador que irá executar o aprovisionamento no servidor de licenciamentos. SubEnrollService.asmx está localizado no directório virtual Certification, no servidor de certificações de raiz.
