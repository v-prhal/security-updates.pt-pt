---
TOCTitle: 'Passo 1: Rever os Requisitos de Instalação do WSUS 3.0'
Title: 'Passo 1: Rever os Requisitos de Instalação do WSUS 3.0'
ms:assetid: '912b37d7-021e-4c95-b317-49dd15b4611c'
ms:contentKeyID: 18142205
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc708484(v=WS.10)'
---

Passo 1: Rever os Requisitos de Instalação do WSUS 3.0
======================================================

Este guia explica como instalar o WSUS 3.0. Para informações sobre os requisitos de software e as plataformas suportadas para o WSUS 3.0, consulte as Notas de Lançamento ([http://go.microsoft.com/fwlink/?LinkId=71220](http://go.microsoft.com/fwlink/?linkid=71220)) (página em inglês) sobre os sistemas operativos Windows Server 2003 Service Pack 1 e Windows Server® 2008.

Requisitos de Software para Instalar o WSUS 3.0 no Windows Server 2003 Service Pack 1
-------------------------------------------------------------------------------------

Para instalar o WSUS 3.0 no Windows Server 2003 Service Pack1, é necessário ter os seguintes componentes instalados no computador. Se alguma destas actualizações requerer que o servidor seja reiniciado quando a instalação estiver concluída, deverá reiniciar o servidor antes de instalar o WSUS 3.0.

-   Microsoft Internet Information Services (IIS) 6.0.
-   Actualização para o Serviço de Transferência Inteligente em Segundo Plano (BITS) 2.0 e WinHTTP 5.1 Windows Server 2003. Para transferir este software, aceda ao Centro de Transferências ([http://go.microsoft.com/fwlink/?LinkID=47251](http://go.microsoft.com/fwlink/?linkid=47251)).
-   Microsoft .NET Framework Redistributable Package versão 2.0 (x86). Para transferir este software, aceda ao Centro de Transferências ([http://go.microsoft.com/fwlink/?LinkID=68935](http://go.microsoft.com/fwlink/?linkid=68935)). (Para plataformas de 64 bits, aceda também ao Centro de Transferências \[[http://go.microsoft.com/fwlink/?LinkID=70637](http://go.microsoft.com/fwlink/?linkid=70637)\].) (página em inglês)
-   Microsoft Report Viewer Redistributable 2005. Para obter este software, aceda ao Centro de Transferências ([http://go.microsoft.com/fwlink/?LinkID=70410](http://go.microsoft.com/fwlink/?linkid=70410)) (página em inglês).
-   Consola de Gestão da Microsoft 3.0 para Windows Server 2003 (KB907265). Para transferir este software, aceda ao Centro de Transferências ([http://go.microsoft.com/fwlink/?LinkID=70412](http://go.microsoft.com/fwlink/?linkid=70412)). (Para plataformas de 64 bits, aceda também ao Centro de Transferências \[[http://go.microsoft.com/fwlink/?LinkID=70638](http://go.microsoft.com/fwlink/?linkid=70638)\].) (página em inglês)

Requisitos de Software para Instalar o WSUS 3.0 no Windows Server 2008
----------------------------------------------------------------------

Para instalar o WSUS 3.0 no Windows Server 2008, é necessário ter os seguintes componentes instalados no computador. Se alguma destas actualizações requerer que o servidor seja reiniciado quando a instalação estiver concluída, deverá reiniciar o servidor antes de instalar o WSUS 3.0.

-   Microsoft Internet Information Services (IIS) 7.0. Certifique-se de que os componentes seguintes estão activados:
    -   Autenticação do Windows
    -   Compatibilidade de Gestão
    -   do ASP.NET 6.0
    -   Compatibilidade de Metabase do IIS
-   Microsoft Report Viewer Redistributable 2005. Para transferir este software, aceda ao Centro de Transferências ([http://go.microsoft.com/fwlink/?LinkID=70410](http://go.microsoft.com/fwlink/?linkid=70410)) (página em inglês).
-   Microsoft SQL Server™ 2005 Service Pack 1. Para transferir este software, aceda ao Centro de Transferências ([http://go.microsoft.com/fwlink/?LinkID=66143](http://go.microsoft.com/fwlink/?linkid=66143)) (página em inglês).

As actualizações para o .NET Framework 2.0 e BITS 2.0 estão disponíveis no Windows Server 2008 como parte do sistema operativo.

Recomendações e requisitos de disco
-----------------------------------

Para instalar o WSUS 3.0, o sistema de ficheiros do servidor deverá preencher os seguintes requisitos:

-   Tanto a partição do sistema como a partição de instalação do WSUS 3.0 têm de estar formatadas com o sistema de ficheiros NTFS.
-   É recomendado, no mínimo, 1 GB de espaço livre para a partição do sistema.
-   São necessários, no mínimo, 20 GB de espaço livre para o volume onde o WSUS armazena conteúdos; são recomendados 30 GB de espaço livre.
-   São recomendados 2 GB de espaço livre no volume onde o programa de configuração do WSUS instala o Base de dados interna do Windows®.

Requisitos de instalação apenas para consolas
---------------------------------------------

O WSUS já permite a instalação da consola de Administração do WSUS em sistemas remotos separada do servidor WSUS. As instalações apenas para consolas podem ser executadas nos seguintes sistemas operativos:

-   Windows Server® 2008
-   Windows Vista®
-   Windows Server 2003 Service Pack 1
-   Windows XP Service Pack 2

Pré-requisitos de software para instalação apenas para consolas

-   Microsoft .NET Framework Redistributable Package versão 2.0 (x86), disponível no Centro de Transferências da Microsoft ([http://go.microsoft.com/fwlink/?LinkId=68935](http://go.microsoft.com/fwlink/?linkid=68935)). Para plataformas de 64 bits, aceda a Microsoft .NET Framework Version 2.0 Redistributable Package (x64) ([http://go.microsoft.com/fwlink/?LinkId=70637](http://go.microsoft.com/fwlink/?linkid=70637)) (página em inglês).
-   Consola de Gestão da Microsoft 3.0 para Windows Server 2003 (KB907265), disponível no Centro de Transferências da Microsoft ([http://go.microsoft.com/fwlink/?LinkId=70412](http://go.microsoft.com/fwlink/?linkid=70412)). Para plataformas de 64 bits, aceda a Microsoft Management Console 3.0 para Windows Server 2003 x64 Edition (KB907265) ([http://go.microsoft.com/fwlink/?LinkId=70638](http://go.microsoft.com/fwlink/?linkid=70638)) (página em inglês).
-   Microsoft Report Viewer Redistributable 2005, disponível no Centro de Transferências da Microsoft ([http://go.microsoft.com/fwlink/?LinkId=70410](http://go.microsoft.com/fwlink/?linkid=70410)) (página em inglês).

Requisitos de Actualizações Automáticas
---------------------------------------

O serviço Actualizações Automáticas é o componente cliente do WSUS 3.0. O serviço Actualizações Automáticas não tem outros requisitos de hardware que não estar ligado à rede. É possível utilizar Actualizações Automáticas com o WSUS 3.0 em computadores a executar qualquer um dos seguintes sistemas operativos:

-   Windows Vista.
-   Windows Server® 2008.
-   Microsoft Windows® Server 2003, todas as versões e service packs.
-   Microsoft Windows XP Professional, Service Pack 1 ou Service Pack 2.
-   Microsoft Windows 2000 Professional Service Pack 4, Windows 2000 Server Service Pack 4 ou Windows 2000 Advanced Server Service Pack 4.

Permissões
----------

Devem ser concedidas as seguintes permissões de disco aos utilizadores especificados para os directórios especificados:

1.  O grupo Utilizadores incorporado ou a conta NT Authority\\Network Service (no Windows Server 2003) devem ter permissão de leitura na pasta raiz da unidade onde se encontra o directório de conteúdos do WSUS. Se esta permissão não existir, as transferências do BITS falharão.
2.  A conta NT Authority\\Network Service deve ter permissão "Full Control" (controlo total) no directório de conteúdos do WSUS, normalmente &lt;SystemDriver&gt;:WSUS\\WsusContent. Esta permissão é definida pelo programa de configuração do servidor do WSUS quando cria o directório, mas alguns programas de software de segurança podem repor esta permissão. Se esta permissão não existir, as transferências do BITS falharão.
3.  A conta NT Authority\\Network Service deve ter permissão "Full Control" (controlo total) nas seguintes pastas para que o componente de Administração do WSUS seja apresentado correctamente:
    -   %windir%\\Microsoft .NET\\Framework\\v2.0.50727\\Temporary ASP.NET Files
    -   %windir%\\Temp

Para mais informações sobre a definição de permissões, consulte DCPROMO não mantém as permissões em algumas pastas do IIS em [http://go.microsoft.com/fwlink/?LinkID=76332](http://go.microsoft.com/fwlink/?linkid=76332).
