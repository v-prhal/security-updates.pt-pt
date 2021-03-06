---
TOCTitle: Gerir o Tamanho do Registo
Title: Gerir o Tamanho do Registo
ms:assetid: '431b32b3-02f0-4666-b52c-183eb65154fd'
ms:contentKeyID: 18123957
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc720271(v=WS.10)'
---

Gerir o Tamanho do Registo
==========================

O serviço de registo envia grandes quantidades de dados para a base de dados do SQL Server. Verifique regularmente o registo da base de dados para se certificar de que existe espaço em disco suficiente. Se achar que a quantidade de dados é excessiva e que as suas necessidades em termos de relatórios não necessitam de parte da informação, pode considerar a hipótese de configurar filtros no SQL Server de forma a reduzir o tamanho dos ficheiros de registo, armazenando apenas as informações de que necessita. Para mais instruções sobre a forma de filtrar as informações a reter nos ficheiros de registo, consulte a Ajuda do SQL Server Enterprise Manager.

Se acha que a base de dados de registo está a ficar demasiado grande para o espaço livre em disco, pode mudar a base de dados de registo para outro servidor, como descrito em "[Mudar a Localização da Base de Dados de Registo](https://technet.microsoft.com/34ea8045-dc94-422e-9601-29927cfc1534)" posteriormente nesta secção.

| ![](images/Cc720271.Important(WS.10).gif)Importante                                                                                                                                                                                                                                                                                             |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Utilize também o Monitor de Sistema para controlar regularmente o tamanho da fila de mensagens de registo de saída. Se o tamanho da fila aumentar substancialmente, verifique se o serviço de escuta do registo está a funcionar correctamente. Para mais informações sobre como utilizar o Monitor de sistema, consulte o Centro de Ajuda e Suporte do Windows Server 2003. |
