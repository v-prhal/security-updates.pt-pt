---
TOCTitle: Activar o suporte do RMS para Serviços do Servidor
Title: Activar o suporte do RMS para Serviços do Servidor
ms:assetid: '6288323c-0638-41b6-bef8-67a7c9433424'
ms:contentKeyID: 18124007
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc747593(v=WS.10)'
---

Activar o suporte do RMS para Serviços do Servidor
==================================================

O RMS também pode fornecer certificados de contas de direitos e utilizar licenças para aplicações de servidor activadas pelo RMS. Existem alguns aspectos a ter em consideração quando se configura os serviços de servidor:

-   As listas de controlo de acesso discricionário (DACLs) nos pipelines do RMS utilizam, por predefinição, as definições mais seguras. Deve modificar as listas DACL quando utilizar os serviços de servidor do RMS.
-   Se o cliente RMS estiver instalado num servidor baseado em Windows Server 2003 e a Configuração de Segurança Avançada do Internet Explorer estiver activada, deve adicionar o URL do cluster do RMS à Zona de Sites Fidedignos do Internet Explorer.
-   Muitos serviços de servidor utilizam uma funcionalidade avançada dos serviços de directório do Active Directory que apenas está disponível se todos os controladores de domínio do Active Directory estiverem a utilizar o Windows Server 2003. Se estiver a utilizar quaisquer serviços de servidor (por exemplo, o Microsoft Office SharePoint Server 2007 ou o Microsoft Exchange Server 2007), recomenda-se que todos os controladores de domínio estejam a utilizar o Windows Server 2003 e que os níveis funcionais de domínio e de floresta do Active Directory estejam ao nível do Windows Sever 2003.

Lista de controlo de acesso discricionário (DACL) predefinida no pipeline de certificação do servidor
-----------------------------------------------------------------------------------------------------

As aplicações, tais como o Microsoft Office SharePoint Server 2007 ou o Microsoft Exchange Server 2007, são activadas pelo RMS para pedir licenças de utilização em nome dos utilizadores. Numa instalação RMS predefinida, a lista DACL do pipeline de certificação do servidor do RMS é restrita, o que significa que uma aplicação não pode obter certificados e licenças para os seus utilizadores. No entanto, se tiver uma aplicação activada pelo RMS para estes computadores, pode activá-las para participarem no sistema do RMS configurando as DACLs no pipeline de certificação do servidor do RMS.

As aplicações de servidor activadas pelo RMS ligar-se-ão ao serviço de certificação do RMS utilizando o ficheiro ServerCertification.asmx.

Quando o RMS cria estes ficheiros, as listas DACL dos ficheiros são definidas para apenas permitir o acesso aos processos do sistema. Recomenda-se que crie um grupo de segurança do Active Directory para os serviços de servidor e, de seguida, preencha este grupo com os objectos do Active Directory dos computadores que estão a pedir licenças de utilização em nome dos seus utilizadores.

Após criar o grupo, pode modificar a lista DACL para o ficheiro ServerCertification.asmx para permitir que o grupo tenha permissão de Leitura & Execução no serviço. Também deve adicionar o Grupo de Serviços do RMS à lista DACL com a permissão de Leitura & Execução.

| ![](images/Cc747593.note(WS.10).gif)Nota                                                                                  |
|--------------------------------------------------------------------------------------------------------------------------------------------------------|
| Se existir mais do que um servidor RMS no cluster, a lista DACL no ficheiro ServerCertification.asmx terá de ser alterada em cada servidor no cluster. |

Para o Microsoft Exchange Server 2007, o objecto de computador do Active Directory de cada servidor bridgehead do Exchange deve ser adicionado ao grupo de serviços do servidor. Se isto não for efectuado, o servidor bridgehead do Exchange não poderá pedir licenças em nome dos utilizadores que receberam a mensagem de correio electrónico.

Para o Office SharePoint Server 2007, deve adicionar o objecto de computador do Active Directory do servidor que utiliza o Office SharePoint Server 2007 ao grupo de serviços do servidor. Se o seu servidor do Office SharePoint Server 2007 estiver configurado para utilizar o servidor predefinido no Active Directory, deve adicionar o Grupo de Serviços do RMS e o grupo criado para os serviços de servidor ao ficheiro ServiceLocater.asmx e autorizar a permissão de Leitura & Execução.

| ![](images/Cc747593.Important(WS.10).gif)Importante                                                                                                                                                               |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Os Serviços de Informação Internet (IIS) devem ser reiniciados após alterar a lista DACL nos ficheiros ServerCertification.asmx e ServiceLocater.asmx. Para reiniciar o IIS, execute o comando **iisreset** a partir de uma linha de comandos. |
