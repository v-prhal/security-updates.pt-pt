---
TOCTitle: Desactivar Servidores do RMS
Title: Desactivar Servidores do RMS
ms:assetid: '11badb02-62c1-455c-96b7-935bbcb496bc'
ms:contentKeyID: 18123944
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc720200(v=WS.10)'
---

Desactivar Servidores do RMS
============================

Quando desactivar o RMS, o comportamento do servidor do RMS altera-se para que possa fornecer uma chave que desencripte os conteúdos protegidos pelo RMS publicados anteriormente. Esta chave permite guardar o conteúdo sem protecção do RMS. Isto pode ser útil no caso de decidir deixar de utilizar a protecção por RMS na organização.

Deverá executar o servidor no estado desactivado o tempo suficiente para que os utilizadores tenham a oportunidade de guardar o seu conteúdo sem protecção RMS, e para que os administradores de sistema e de rede tenham a oportunidade de desactivar quaisquer clientes activados pelo RMS para os impedir de utilizar o serviço.

Pode activar a desactivação através da página **Definições de segurança** no Web site Administração. Depois de activar a desactivação, não é possível restaurar o servidor para uma configuração padrão do servidor do RMS. Se a instalação englobava também domínios de publicação fidedignos, estes são também desactivados.

Depois de activar a desactivação, o Web site de administração terá apenas a página **Informações do servidor desactivado**. A administração deixa de ser suportada. Para concluir a desactivação do servidor, deverá executar os seguintes passos:

1.  Dê permissões de Leitura e de Execução ao **Grupo de Serviços do RMS** para a raiz virtual de desactivação.
2.  Adicione o grupo **Todos** à DACL do ficheiro decommissioning.asmx com permissão de Leitura.
3.  Informe os utilizadores de que está a desactivar a instalação do RMS e aconselhe-os a estabelecerem ligação com o servidor para guardar os respectivos conteúdos sem protecção do RMS.
4.  Configure todas as aplicações activadas pelo RMS da empresa para estabelecerem ligação com a página decommissioning.asmx. Dependendo da aplicação activada pelo RMS, esta poderá ser controlada por uma chave de registo ou pela definição de Política de Grupo.
5.  Se a organização estiver a utilizar aplicações activadas pelo RMS que utilizam automaticamente a instalação para publicar, deverá utilizar a Política de Grupo para definir uma entrada de registo nesses computadores, para que essas aplicações utilizem o serviço de desactivação.
6.  Quando tiver a certeza de que todo o conteúdo está desprotegido, deverá efectuar uma cópia de segurança da chave privada do servidor e, em seguida, remover o RMS do servidor.
