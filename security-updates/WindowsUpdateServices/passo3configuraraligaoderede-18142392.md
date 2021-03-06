---
TOCTitle: 'Passo 3: Configurar a Ligação de Rede'
Title: 'Passo 3: Configurar a Ligação de Rede'
ms:assetid: 'cd77566d-7780-4ce4-aa56-41183c65c4a7'
ms:contentKeyID: 18142392
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc708559(v=WS.10)'
---

Passo 3: Configurar a Ligação de Rede
=====================================

Depois de instalar o WSUS, está pronto para aceder à consola WSUS para configurar o WSUS e para começar. Por predefinição, o WSUS está configurado para utilizar o Microsoft Update como localização de obtenção de actualizações. Se tiver um servidor proxy na rede, utilize a consola WSUS para configurar o WSUS para que este utilize o servidor proxy. Se houver um firewall empresarial entre o WSUS e a Internet, poderá ser necessário configurar o firewall de modo a assegurar que o WSUS consegue obter actualizações.

| ![](images/Cc708559.note(WS.10).gif)Nota                                                                                                                                                                                                                       |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Embora tenha de ter ligação à Internet para transferir actualizações do Microsoft Update, o WSUS oferece-lhe a capacidade de importar actualizações para redes não ligadas à Internet. Para mais informações, consulte a documentação “Deploying Microsoft Windows Server Update Services”. |

O Passo 3 contém os seguintes procedimentos:

-   Configurar o firewall para que o WSUS possa obter actualizações.
-   Abrir a consola WSUS.
-   Configurar as definições do servidor proxy para que o WSUS possa obter actualizações.

**Para configurar o firewall**
-   Se houver um firewall empresarial entre o WSUS e a Internet, poderá ser necessário configurar esse firewall de modo a assegurar que o WSUS consegue obter actualizações. Para obter actualizações a partir do Microsoft Update, o servidor WSUS utiliza a porta 80 para o protocolo HTTP e a porta 443 para o protocolo HTTPS. Estas definições não são configuráveis.

-   Se a organização não permitir que essas portas e protocolos estejam abertos para todos os endereços, poderá restringir o acesso a apenas aos domínios abaixo, de modo que o WSUS e o serviço Actualizações Automáticas possam comunicar com o Microsoft Update:

    -   http://windowsupdate.microsoft.com
    -   http://\*.windowsupdate.microsoft.com
    -   https://\*.windowsupdate.microsoft.com
    -   http://\*.update.microsoft.com
    -   https://\*.update.microsoft.com
    -   http://\*.windowsupdate.com
    -   http://download.windowsupdate.com
    -   http://download.microsoft.com
    -   http://\*.download.windowsupdate.com
    -   http://wustat.windows.com
    -   http://ntservicepack.microsoft.com

| ![](images/Cc708559.note(WS.10).gif)Nota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Os passos mencionados acima para configurar o firewall destinam-se a um firewall empresarial situado entre o WSUS e a Internet. Dado que o WSUS inicia todo o respectivo tráfego de rede, não é necessário configurar o Firewall do Windows no servidor WSUS. Embora a ligação entre o Microsoft Update e o WSUS requeira que as portas 80 e 443 estejam abertas, poderá configurar vários servidores WSUS para sincronizarem com uma porta personalizada. Para mais informações sobre como sincronizar servidores WSUS com uma porta personalizada, consulte a documentação “Deploying Microsoft Windows Server Update Services”. |

**Para abrir a consola WSUS**
-   No servidor WSUS, clique em **Iniciar**, aponte para **Todos os Programas**, aponte para **Ferramentas Administrativas** e clique em **Microsoft Windows Server Update Services**.

| ![](images/Cc708559.note(WS.10).gif)Nota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Para utilizar a consola WSUS, tem de ser membro do grupo Administradores do WSUS ou do grupo Administradores local no servidor no qual o WSUS está instalado. Se não adicionar **http://&lt;***nome do Web site WSUS***&gt;** à lista de sites na zona Intranet Local do Internet Explorer no Windows Server 2003, poderão ser-lhe pedidas credenciais sempre que abrir a consola WSUS. Se alterar a atribuição de portas no IIS após a instalação do WSUS, terá de actualizar manualmente o atalho no menu **Iniciar**. É também possível abrir a consola WSUS a partir do Internet Explorer em qualquer servidor ou computador na rede introduzindo o seguinte URL: **http://***nomeservidorWSUS***/WSUSAdmin** |

**Para especificar um servidor proxy**
1.  Na barra de ferramentas da consola WSUS, clique em **Opções** e, em seguida, clique em **Opções de Sincronização**.

2.  Na caixa **Servidor proxy**, seleccione a caixa de verificação **Utilizar um servidor proxy quando sincronizar** e escreva o nome e número de porta do servidor proxy (porta 80 por predefinição) nas caixas correspondentes.

3.  Se pretender ligar ao servidor proxy utilizando credenciais de utilizador específicas, seleccione a caixa de verificação **Utilize credenciais de utilizador para ligar ao servidor proxy** e escreva o nome de utilizador, domínio e palavra-passe do utilizador nas caixas correspondentes. Se pretender activar a autenticação básica para o utilizador que estabelece ligação com o servidor proxy, seleccione a caixa de verificação **Permitir autenticação básica (a palavra-passe é enviada como texto simples)**.

4.  Em **Tarefas**, clique em **Guardar definições** e, na caixa de diálogo de confirmação, clique em **OK**.
