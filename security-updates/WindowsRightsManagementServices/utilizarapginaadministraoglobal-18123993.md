---
TOCTitle: Utilizar a Página Administração Global
Title: Utilizar a Página Administração Global
ms:assetid: '57bbf402-2351-4dee-823c-27f4dd32447c'
ms:contentKeyID: 18123993
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc747575(v=WS.10)'
---

Utilizar a Página Administração Global
======================================

A partir da página **Administração Global** do Web site de administração, pode aprovisionar e desaprovisionar um servidor do RMS e alterar a conta de serviço do RMS.

Para aceder a esta página Web a partir do servidor que pretende administrar, utilize os seguintes passos:

1.  Inicie a sessão como administrador local.
2.  Clique em **Iniciar**, aponte para **Todos os programas**, aponte para **Windows RMS** e clique em **Administração do Windows RMS**.

Não é possível aceder à página de **Administração Global** a partir de um browser que se encontra num computador remoto.

Se ainda não aprovisionou o servidor a partir do qual está a aceder à página de **Administração Global**, são apresentadas as seguintes opções para cada Web site que está a ser executado no servidor:

-   **Aprovisionar o RMS neste Web site**. Clique neste ligação se este for o primeiro servidor que pretende aprovisionar neste cluster. Isto dá início ao processo de aprovisionamento, durante o qual são instalados os recursos do RMS, como, por exemplo, os directórios virtuais. Além disso, as bases de dados são instaladas no servidor de bases de dados. Para mais informações, consulte "[Para Aprovisionar o Primeiro Servidor de Certificações de Raiz](https://technet.microsoft.com/debc42f3-74ff-4c99-b7a4-4921fccdabc2)" posteriormente nesta secção.
-   **Adicionar o RMS a um cluster**. Clique nesta ligação se pretende aprovisionar o servidor e adicioná-lo a um cluster existente. Pode adicionar um servidor a um cluster de certificações de raiz ou a um cluster de licenciamentos . São instalados os recursos do RMS, como, por exemplo, os directórios virtuais. Contudo, não são criadas as bases de dados, porque este servidor irá utilizar as bases de dados do cluster. Para mais informações, consulte "[Para Adicionar um Servidor a um Cluster](https://technet.microsoft.com/db635238-5528-4bec-9cc6-8244e2b3d733)" posteriormente nesta secção.

Se aceder à página de **Administração** Global a partir de um servidor que já foi aprovisionado, são apresentadas as seguintes opções:

-   **Administrar o RMS neste Web site.** Clique nesta ligação para que a página Administração de Cluster seja apresentada. Para mais informações, consulte "[Utilizar a Home Page de Administração](https://technet.microsoft.com/6c155977-bd0e-47d6-ac65-1746cddb505e)" posteriormente nesta secção.
-   **Alterar a conta de serviço do RMS.** Clique nesta ligação para especificar uma conta de serviço do RMS diferente, na qual o RMS deverá ser executado. Para mais informações, consulte "[Alterar a Conta de Serviço do RMS](https://technet.microsoft.com/f257d66d-b823-41e4-bcb7-7c90eb295238)" posteriormente nesta secção.
-   **Remover o RMS deste Web site.**Clique nesta ligação para desaprovisionar o RMS. Quando desaprovisiona o RMS, os directórios virtuais e as aplicações do RMS são removidas do servidor, mas o RMS não é desinstalado. Para mais informações, consulte "[Para Desinstalar o RMS](https://technet.microsoft.com/885e3b4f-ea32-466f-9f7f-d8440b0f7c28)" posteriormente nesta secção.

| ![](images/Cc747575.note(WS.10).gif)Nota                                                                                                                                                                                                                                             |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| O Web site da Administração do RMS utiliza janelas de contexto para a configuração de algumas funcionalidades. Se estiver a utilizar um bloqueador de contexto no seu browser Web, deverá configurar as definições do browser para permitir que apareçam janelas de contexto do Web site da Administração do RMS. |
