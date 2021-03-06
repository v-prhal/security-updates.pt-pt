---
TOCTitle: Mudar a Localização da Base de Dados de Registo
Title: Mudar a Localização da Base de Dados de Registo
ms:assetid: '34ea8045-dc94-422e-9601-29927cfc1534'
ms:contentKeyID: 18123936
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc720238(v=WS.10)'
---

Mudar a Localização da Base de Dados de Registo
===============================================

A configuração predefinida do RMS coloca a base de dados de configuração e a base de dados de registo no mesmo servidor. Verifique periodicamente se o SQL Server tem espaço livre suficiente para ambas as bases de dados.

Se a base de dados de registo ficar demasiado grande, pode mudá-la a qualquer altura para outro servidor. Não é possível mudar a localização da base de dados de registo utilizando o Web site de administração; é necessário mudar manualmente a base de dados, executando os seguintes passos:

1.  Desactive o registo como descrito em "[Para Activar ou Desactivar o Registo](https://technet.microsoft.com/8e672f95-566f-4070-9a2a-2f70f087148f)" posteriormente nesta secção.
2.  Copie a base de dados de registo do servidor de partida para o de destino, através do SQL Server Enterprise Manager. Certifique-se de que são criados na nova base de dados as tabelas e procedimentos armazenados. Uma das formas de o fazer é utilizando o assistente de cópias de bases de dados do SQL Server Enterprise Manager.
3.  Altere a base de dados de configuração de forma a reflectir os novos nomes do servidor e da base de dados. Na tabela DRMS\_ClusterPolicies da base de dados de configuração do cluster para onde está a deslocar a base de dados, faça o seguinte:
    -   Altere o valor da política de LoggingDatabaseServer para que reflicta o novo nome do servidor da base de dados.
    -   Altere o valor da política de LoggingDatabaseName para que reflicta o novo nome da base de dados.

    | ![](images/Cc720238.note(WS.10).gif)Nota                                                                                                                                                               |
    |-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | O SQL Server Enterprise Manager não funciona com campos db\_variant, pelo que não pode ser utilizado para esta tarefa. Em vez disso, pode utilizar o Query Analyzer do SQL Server, ou outra ferramenta de edição de bases de dados. |

4.  Reinicie o IIS em todos os servidores do cluster.
5.  Volte a ligar o registo.
