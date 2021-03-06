---
TOCTitle: Para Activar a Certificação dos Serviços do Servidor
Title: Para Activar a Certificação dos Serviços do Servidor
ms:assetid: '0ed78c85-7acb-4e3b-a594-613f8ccb5b14'
ms:contentKeyID: 18123943
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc720196(v=WS.10)'
---

Para Activar a Certificação dos Serviços do Servidor
====================================================

Para efectuar este procedimento, tem de iniciar sessão localmente no Web site Administração com uma conta de utilizador de domínio que seja membro do grupo Administradores. Como procedimento de segurança recomendado, considere utilizar o comando **Executar como** para efectuar este procedimento.

Este procedimento só é aplicável no cluster de raiz.

Este procedimento assume que criou um grupo de utilizadores com as contas dos utilizadores que os serviços do servidor imitarão quando consumirem conteúdo protegido.

Activar a Certificação dos Serviços do Servidor
-----------------------------------------------

#### Para Activar a Certificação dos Serviços do Servidor

1.  Inicie sessão no computador como membro do grupo de administradores locais.

2.  Abra um browser do sistema de ficheiros e vá para a pasta &lt;unidade do sistema&gt;:\\Inetpub\\wwwroot\\\_wmcs\\Certification.

3.  Para activar os serviços do servidor para receberem certificados de contas de direitos (RACs), clique com o botão direito do rato no ficheiro ServerCertification.asmx e, em seguida, clique em **Propriedades**.

4.  No separador **Segurança**, clique em **Adicionar** e adicione o grupo criado para esta categoria de utilizadores e o **Grupo de Serviços do RMS**.

5.  Nas listas de **Permissões** para os grupos, seleccione a caixa de verificação **Permitir** para as permissões **Leitura & Execução** e clique em **OK**.

6.  Os passos 1 - 4 devem ser repetidos para cada servidor no cluster.

| ![](images/Cc720196.note(WS.10).gif)Nota                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Para o Microsoft Exchange Server 2007, deve adicionar todos os objectos de computador Active Directory de todos os servidores bridgehead à lista de controlo de acesso discricionário (DACL) do ficheiro ServerCertification.asmx. Da mesma forma, para o Microsoft Office SharePoint Server 2007 deve adicionar o objecto de computador Active Directory do servidor Office SharePoint Server 2007 a esta lista DACL. Recomenda-se que adicione um grupo de segurança a esta lista DACL e que lhe acrescente os objectos de computador adequados. |
