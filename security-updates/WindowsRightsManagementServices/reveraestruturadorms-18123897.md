---
TOCTitle: Rever a Estrutura do RMS
Title: Rever a Estrutura do RMS
ms:assetid: '0ed1dd67-8e07-47c9-9e2e-0104438bd19f'
ms:contentKeyID: 18123897
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc720185(v=WS.10)'
---

Rever a Estrutura do RMS
========================

Antes de iniciar a implementação, certifique-se de que o plano do RMS contempla as seguintes questões:

-   Uma aplicação cliente activada pelo RMS foi seleccionada e os planos de instalação foram implementados.
-   Foi determinado um método de distribuição do cliente RMS.
-   Existe um servidor de bases de dados instalado e acessível.
-   Foi seleccionada uma topologia básica ou distribuída para o RMS.
-   O Active Directory está instalado nos controladores de domínio que executam o Windows 2000 com Service Pack 3 (SP3) ou posterior e todos os utilizadores têm um objecto de contacto com um atributo de correio electrónico configurado. O Windows Server 2003 está instalado com as actualizações mais recentes. A Colocação de Mensagens em Fila, os Serviços de Informação Internet e o ASP.NET versão 1.1 estão activados.

| ![](images/Cc720185.note(WS.10).gif)Nota                                                                                                                                                    |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Se planeia instalar o RMS num computador de 64 bits, reveja os "Requisitos de Software para o RMS" em "Planear uma Implementação do RMS" nesta colecção de documentação para obter instruções de configuração especiais. |

-   Foram definidos métodos de balanceamento de carga e activação pós-falha do servidor.
-   O registo DNS foi configurado para os servidores do RMS.
-   Foram implementados planos de cópia de segurança e recuperação.
-   Foram satisfeitos os requisitos de segurança específicos da organização.
