---
TOCTitle: Para Desaprovisionar o RMS
Title: Para Desaprovisionar o RMS
ms:assetid: '9fa63daa-5fb9-4afd-8371-b38248619857'
ms:contentKeyID: 18124179
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc747706(v=WS.10)'
---

Para Desaprovisionar o RMS
==========================

Para efectuar este procedimento, tem de iniciar sessão localmente no Web site Administração com uma conta de utilizador de domínio que seja membro do grupo Administradores no computador a que está a aceder. Os membros do grupo de administradores de domínio também podem efectuar este procedimento. Como uma boa prática de segurança, considere a utilização do comando **Executar como** para efectuar este procedimento.

Para abrir a página **Administração Global**, clique em **Iniciar**, aponte para **Todos os programas**, aponte para **Windows RMS** e clique em **Administração do Windows RMS**.

Quando desaprovisiona um servidor, este é removido da tabela ClusterServer da base de dados de configuração. Quando desaprovisiona o último servidor de um cluster, a base de dados de serviços de directório é eliminada do SQL Server. Quando desaprovisiona o último servidor de certificações de raiz de um cluster, terá de desregistar manualmente o ponto de ligação do serviço de certificações (SCP). O desaprovisionamento e a desinstalação não remove o SCP do Active Directory.

Se optar por desinstalar um servidor de certificações de raiz antes de o ter aprovisionado, será avisado de que o site não foi ainda desaprovisionado e que o SCP não será removido do Active Directory. No entanto, se seleccionar **Sim** para continuar, o site será desaprovisionado. A desinstalação não remove o ponto de ligação do serviço do Active Directory.

Desaprovisionar o RMS
---------------------

#### Para Desaprovisionar o RMS

1.  Inicie a sessão no servidor em que pretende desaprovisionar o RMS.

2.  Abra a página **Administração Global**.

3.  Junto ao Web site em que o RMS está aprovisionado, clique em **Remover o RMS deste Web site** e, em seguida, clique em **OK**.

4.  Clique em **Desregistar URL**, na página Web do ponto de ligação do serviço do RMS, para desregistar a ligação do serviço de certificações do Active Directory.
