---
TOCTitle: Segurança Durante a Configuração do RMS
Title: Segurança Durante a Configuração do RMS
ms:assetid: '0a3d40b2-f27e-4e63-baff-a9c8433f5f91'
ms:contentKeyID: 18123938
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc720192(v=WS.10)'
---

Segurança Durante a Configuração do RMS
=======================================

Para instalar e configurar os ficheiros do RMS, o programa de configuração do RMS utiliza as credenciais do utilizador com sessão iniciada. Para esse fim, o administrador que procede à instalação deve iniciar sessão com uma conta de utilizador que seja membro do grupo local de Administradores. Para todas as instalações, excepto para as instalações num só computador, também deve ser uma conta de utilizador de domínio.

Durante o procedimento de instalação, o servidor Windows Installer (Msiexec.exe) é iniciado. Este serviço herda o respectivo token do utilizador principal. Posteriormente, se ocorrerem acções personalizadas após o processo, o serviço Msiexec.exe utiliza a identificação do utilizador com sessão iniciada. Isto ocorre independentemente de o processo ser iniciado a partir de um browser ou da linha de comandos.

O programa de configuração do RMS executa as seguintes tarefas:

-   Copia os ficheiros para a pasta C:\\Programas\\RMS. Esta pasta geralmente permite que os Administradores e Utilizadores Avançados lhe possam aceder. Pode indicar a localização da unidade e do ficheiro durante a configuração.
-   Por predefinição, cria o Web site de aprovisionamento (ou seja, o Web site Administração do RMS) na porta 5720. Este Web site aponta para os ficheiros instalados.
-   Cria um grupo de aplicações (WMCSProvisioningAppPool) e associa-o ao Web site Administração do RMS. A conta de serviço que é utilizada por este grupo de aplicações é a de Serviços de Rede.
-   Instala os contadores de desempenho.
-   Concede permissões de Leitura e Escrita ao Grupo de Serviços do RMS para a chave de registo indicada a seguir.
    Em computadores com a versão de 32 bits do Windows Server 2003:
    `HKEY_LOCAL_MACHINE\Software\Microsoft\DRMS\1.0`
    Em computadores com a versão de 64 bits do Windows Server 2003:
    `HKEY_LOCAL_MACHINE\Software\WOW6432Node\Microsoft\DRMS\1.0`
