---
TOCTitle: 'Passo 1: Confirmar os Requisitos de Instalação do WSUS 3.0 SP2'
Title: 'Passo 1: Confirmar os Requisitos de Instalação do WSUS 3.0 SP2'
ms:assetid: 'ec01bd75-5def-4899-8cee-ddab827bbd83'
ms:contentKeyID: 21799083
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Dd939916(v=WS.10)'
---

Passo 1: Confirmar os Requisitos de Instalação do WSUS 3.0 SP2
==============================================================

Antes de instalar ou actualizar para a versão do Windows Server Upgrade Services 3.0 Service Pack 2 (WSUS 3.0 SP2), confirme se tanto o servidor como os computadores cliente cumprem os requisitos de sistema do WSUS 3.0 SP2 e se dispõe das permissões necessárias para concluir a instalação.

Requisitos de Hardware e Software do Servidor para Instalar o WSUS 3.0 SP2
--------------------------------------------------------------------------

1.  Confirme se o servidor cumpre os requisitos de sistema do WSUS 3.0 SP2 quanto a hardware, sistema operativo e outro software necessário. Os requisitos de sistema encontram-se indicados nas Notas de Versão do WSUS 3.0 SP2 em [http://go.microsoft.com/fwlink/?LinkId=139840](http://go.microsoft.com/fwlink/?linkid=139840). Se estiver a utilizar o Gestor de Servidor para instalar o WSUS 3.0 SP2 Server, pode confirmar se cumpre os requisitos de software seguindo os passos indicados na secção “A preparar a instalação do WSUS 3.0 SP2”.
2.  Se instalar funções ou actualizações de software que necessitem que reinicie o servidor depois de concluída a instalação, reinicie o servidor antes de instalar o WSUS 3.0 SP2.

Requisitos de Software de Cliente
---------------------------------

O serviço Actualizações Automáticas é o cliente do WSUS 3.0. O serviço Actualizações Automáticas não tem outros requisitos de hardware para além da ligação à rede.

1.  Confirme se o computador no qual está a instalar as Actualizações Automáticas cumpre os requisitos de sistema do WSUS 3.0 SP2 para computadores cliente. Os requisitos de sistema encontram-se indicados nas Notas de Versão do WSUS 3.0 SP2 em [http://go.microsoft.com/fwlink/?LinkId=139840](http://go.microsoft.com/fwlink/?linkid=139840).
2.  Se instalar actualizações de software que necessitem que reinicie o computador, reinicie-o antes de instalar o WSUS 3.0 SP2.

Permissões
----------

São necessárias as seguintes permissões para os utilizadores e directórios especificados:

1.  A conta NT Authority\\Network Service tem de ter permissão Controlo Total para as seguintes pastas, de modo a que o snap-in Administração WSUS seja visualizado correctamente:
    -   %windir%\\Microsoft .NET\\Framework\\v2.0.50727\\Temporary ASP.NET Files
    -   %windir%\\Temp
2.  Confirme se a conta que pretende utilizar para instalar o WSUS 3.0 SP2 é membro do grupo Administradores local.

Preparar a instalação do WSUS 3.0 SP2
-------------------------------------

Se estiver a utilizar o Windows 7 ou o Windows Server 2008 SP2, pode instalar o WSUS 3.0 SP2 a partir do Gestor de Servidor. Se estiver a utilizar outro sistema operativo suportado ou a instalar apenas a Consola de Administração do WSUS, passe para a secção seguinte deste manual para instalar o WSUS 3.0 SP2 utilizando o ficheiro WUSSetup.exe.

**Para preparar a instalação do WSUS 3.0 SP2 Server utilizando o Gestor de Servidor**
1.  Inicie sessão no servidor no qual pretende instalar o WSUS 3.0 SP2 utilizando uma conta membro do grupo Administradores local.

2.  Clique em **Iniciar**, aponte para **Ferramentas Administrativas** e, em seguida, clique em **Gestor de Servidor**.

3.  No painel da direita da janela do Gestor de Servidor, na secção Resumo das Funções, clique em **Adicionar Funções**.

4.  Se a página Antes de Começar aparecer, clique em **Seguinte**.

5.  Na página Seleccionar Funções de Servidor, confirme se as opções **Servidor de Aplicações** e **Servidor Web (IIS)** estão seleccionadas. Se estiverem seleccionadas, utilize o restante deste passo para confirmar se os serviços de função necessários estão seleccionados. Caso contrário, instale o Servidor de Aplicações e o Servidor Web (IIS) como se indica a seguir.

    1.  Na página Seleccionar Funções de Servidor, seleccione **Servidor de Aplicações** e **Servidor Web (IIS)**. Clique em **Seguinte**.
    2.  Se estiver a instalar Serviços de Função de Aplicações, na página Servidor de Aplicações, clique em **Seguinte**. Na página Serviços de Função do Servidor de Aplicações, aceite as predefinições e clique em **Seguinte**.
    3.  Se estiver a instalar o Servidor Web IIS, na página Servidor Web (IIS), clique em **Seguinte**. Na página Serviços de Função do Servidor Web (IIS), para além das predefinições, seleccione **ASP.NET**, **Autenticação do Windows**, **Compressão de Conteúdo Dinâmico** e **Compatibilidade de Gestão do IIS 6**. Se aparecer o Assistente para Adicionar Funções, clique em **Adicionar Serviços de Função Requeridos**. Clique em **Seguinte**.
    4.  Na página Confirmar Selecções de Instalação, clique em **Instalar**.
    5.  Na página Resultados da Instalação, confirme se aparece a mensagem “Instalação com êxito” para os serviços de função que instalou neste passo e clique em **Fechar**.

Passo seguinte
--------------

[Passo 2: Instalar o servidor WSUS ou a Consola de Administração](https://technet.microsoft.com/6db6fcb0-c55d-43b9-9b07-4040c6267759).

Recursos adicionais
-------------------

[Manual Passo a Passo do Windows Server Update Services 3.0 SP2](https://technet.microsoft.com/4b504edc-93b3-45b0-a7e8-d0107f1a4442)
