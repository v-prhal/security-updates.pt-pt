---
TOCTitle: Excluir Certificados de Conta
Title: Excluir Certificados de Conta
ms:assetid: 'cba5e901-942c-4d06-9865-e6c4648c95e6'
ms:contentKeyID: 18124159
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc747670(v=WS.10)'
---

Excluir Certificados de Conta
=============================

Se um utilizador for fidedigno apesar de apresentar credenciais do RMS suspeitas, pode excluir o certificado de conta de direitos desse utilizador através da exclusão da respectiva chave pública. Quando efectuar esta operação, o RMS recusa novos pedidos de licença de utilização que envolvam esse certificado de conta de direitos. Depois de excluir um certificado de conta de direitos, da próxima vez que esse utilizador tentar adquirir uma licença de utilização para conteúdo novo, o pedido será recusado. Para adquirir uma licença de utilização, o utilizador terá de obter um novo certificado de conta de direitos com um novo par de chaves.

Os certificados de contas de direitos poderão ser excluídos utilizando a página **Políticas de exclusão** do Web site de administração. Quando excluir um certificado de conta de direitos de um utilizador, o RMS adiciona a chave excluída, o nome da conta do utilizador, e a data e a hora da exclusão à tabela DRMS\_GicExclusionList da base de dados de configuração do cluster de certificações de raiz. Estas informações aparecem também na página **Políticas de exclusão** do Web site de administração. Além disso, o RMS elimina as chaves pública e privada que estão associadas ao certificado de conta excluído da tabela UD\_Users da base de dados de configuração.

Para excluir um certificado de conta de direitos que se encontra no servidor ou no cluster de certificações de raiz, especifique a conta de domínio do utilizador na página **Políticas de exclusão** do servidor de certificações de raiz. Deverá excluir um certificado de conta de direitos nos servidores pré-inscritos de cada Web site de administração do servidor. Para excluir um utilizador num servidor ou cluster de licenciamento pré-inscrito, introduza o valor da chave pública do certificado de conta de direitos na página **Políticas de exclusão** do Web site de administração do servidor de licenciamento. Este valor poderá ser obtido na página **Políticas de exclusão** do Web site de administração do cluster de certificações de raiz.

Para simplificar a exclusão do certificado de conta de direitos numa implementação do RMS em vários clusters, pode replicar a tabela DRMS\_GicExclusionList da base de dados de configuração do cluster de certificações de raiz para a base de dados de configuração de cada base de dados de cada cluster de licenciamento. Se o fizer, não tem de introduzir manualmente o valor da chave pública de cada servidor.
