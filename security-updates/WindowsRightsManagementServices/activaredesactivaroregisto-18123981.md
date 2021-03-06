---
TOCTitle: Activar e Desactivar o Registo
Title: Activar e Desactivar o Registo
ms:assetid: '50ccd827-2d39-41e7-a395-3d5f5836869b'
ms:contentKeyID: 18123981
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc747565(v=WS.10)'
---

Activar e Desactivar o Registo
==============================

Pode activar e desactivar o registo do cluster ou servidor actual na página das **Definições de registo**. Desactivar o registo impede que os serviços Web do RMS enviem dados registados para a fila de dados de registo. Pára também o serviço de escuta do registo. Não é possível desactivar o registo utilizando a ferramenta de administração dos Serviços do Windows Server 2003.

Os registos do RMS são enviados para o servidor da base de dados através da colocação de mensagens em fila. Caso não exista uma ligação ao servidor da base de dados, a colocação de mensagens em fila guarda os registos numa cache local até que a ligação seja restabelecida. Na primeira vez que activar o registo, deve certificar-se que o servidor do RMS tem uma ligação ao servidor da base de dados e que o serviço da base de dados foi iniciado. Se estiver a utilizar o SQL Server como servidor da base de dados, pode verificar que os registos estão a ser guardados na base de dados através dos passos seguintes:

-   No SQL Server Enterprise Manager, vá até à base de dados de registo, expanda **Databases** e depois expanda a base de dados que contém a base de dados de registo do RMS.
-   Clique na base de dados do registo, clique em **Tables**, clique com o botão direito do rato em **DRMS\_log\_master** e clique em **Open table return all rows**. Se os ficheiros de registo estiverem a ser criados, é possível ver um ou mais ficheiros de registo.
