---
TOCTitle: 'Notas de Versão do Windows Server Update Services 3.0 SP2'
Title: 'Notas de Versão do Windows Server Update Services 3.0 SP2'
ms:assetid: 'b3723422-489d-47b7-abfa-663353647da0'
ms:contentKeyID: 21799054
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Dd939886(v=WS.10)'
---

Notas de Versão do Windows Server Update Services 3.0 SP2
=========================================================

Estas notas de versão descrevem a versão do Windows Server Update Services 3.0 Service Pack 2 (WSUS 3.0 SP2). Este documento contém as seguintes secções:

1.  Novidades Desta Versão
2.  Requisitos de Sistema para a Instalação de Servidor do WSUS 3.0 SP2
3.  Pré-requisitos de Configuração e Recomendações de Melhores Práticas para o Servidor WSUS.
4.  Pré-requisitos do Windows Small Business Server
5.  Requisitos de Sistema para a Instalação da Consola Remota do WSUS 3.0 SP2.
6.  Requisitos de Sistema para a Instalação Cliente
7.  Requisitos e Recomendações de Actualização
8.  Instalar o WSUS 3.0 SP2
9.  Configurar Parâmetros da Linha de Comandos para Instalações Autónomas do WSUS 3.0 SP2
10. Problemas Conhecidos

Novidades Desta Versão
----------------------

-   Integração com o Windows Server 2008 R2.
-   Suporte para a funcionalidade BranchCache no Windows Server 2008 R2.
-   Suporte para os clientes Windows 7.
-   Melhoramentos do cliente Windows Update Agent (WUA). O novo cliente WUA oferece uma colecção de melhoramentos do desempenho, melhoramentos da experiência de utilizador e uma série de correcções com base nos comentários do cliente.
    -   O tempo de análise do cliente é mais reduzido do que em versões anteriores.
    -   Os computadores geridos por servidores WSUS podem agora executar análises ‘"confinadas" nestes mesmos servidores WSUS, em vez de efectuarem uma análise completa. Isto irá originar análises mais rápidas da ordem de magnitude de aplicações utilizando APIs do Microsoft Update, tais como o Windows Defender.
    -   Os melhoramentos da experiência de utilizador do Windows Update Agent (WUA) ajudam os utilizadores a organizarem melhor as actualizações e proporcionam maior clareza no comportamento e valor da actualização.
    -   Os computadores duplicados serão apresentados de forma mais clara na consola WSUS. Para mais informações, consulte o artigo com o título [Um computador baseado no Windows 2000, baseado no Windows Server 2003 ou baseado no Windows XP que foi configurado utilizando uma imagem do Windows 2000, Windows Server 2003 ou Windows XP não aparece na consola WSUS](http://go.microsoft.com/fwlink/?linkid=159749).
-   Novas funcionalidades:
    -   As regras de aprovação automática incluem, agora, a capacidade de especificar a data e hora do prazo de aprovação para todos os computadores ou para grupos específicos de computadores.
    -   Melhor abordagem da selecção de idioma para servidores a jusante, que inclui uma nova caixa de diálogo de aviso apresentada quando decidir transferir actualizações apenas para idiomas especificados.
    -   Os novos relatórios de Actualização e Estado do Computador permitem filtrar as actualizações aprovadas para instalação. Pode executar estes relatórios a partir da consola WSUS ou utilizar a API (application programming interface, interface de programação de aplicações) para incorporar esta funcionalidade nos seus próprios relatórios.
-   A interface de utilizador é compatível entre o Service Pack 1 e o Service Pack 2 para o WSUS 3.0, tanto no cliente como no servidor.
-   Actualizações de software.
-   Problemas conhecidos do Windows Update Agent resolvidos nesta versão:
    1.  O WSUS 3.0 SP2 e o Windows 7 incluem uma nova versão do Windows Update Agent (para Windows XP, Windows Vista, Windows Server 2000, Windows Server 2003 e Windows Server 2008). Esta versão corrige o seguinte problema: As APIs chamadas por chamadores não locais do sistema numa sessão não interactiva falham.
    2.  Problema corrigido pela versão 7.2.6001.788 do Windows Update Agent. Esta actualização corrige o seguinte problema: Quando tenta instalar simultaneamente 80 ou mais actualizações a partir da página Web Windows Update ou da página Web Microsoft Update, poderá receber o código de erro 0x80070057.
    3.  Melhoramentos e problemas corrigidos pela versão 7.2.6001.784 do Windows Update Agent. Esta actualização inclui o seguinte: Melhora os tempos de análise para o Windows Update, melhora a velocidade de entrega das actualizações de assinatura, permite o suporte para a funcionalidade de reinstalação do Windows Installer e melhora as mensagens de erro.

<span id="BKMK_SysReqWSUS30SP2"></span>
Requisitos de Sistema para a Instalação de Servidor do WSUS 3.0 SP2
-------------------------------------------------------------------

Esta secção descreve os requisitos de software e de hardware necessários para a instalação do WSUS 3.0 SP2.

### Pré-requisitos de Software de Servidor do WSUS

-   Tem de ter um dos seguintes sistemas operativos suportados instalados:
    -   Windows Server 2008 R2
    -   Windows Server 2008 SP1 ou versões posteriores
 
        <table style="border:1px solid black;">
        <colgroup>
        <col width="100%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th style="border:1px solid black;" ><img src="images/Dd939886.Warning(WS.10).gif" />Aviso</th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td style="border:1px solid black;">Se o WSUS 3.0 SP2 estiver instalado no Windows Server 2008 antes de actualizar para o Windows Server 2008 R2, ocorrerá uma falha na actualização para o Windows Server 2008 R2. Consulte a secção <a href="#bkmk_knownissues">Problemas Conhecidos</a> para obter mais informações.
        </td>
        </tr>
        </tbody>
        </table>
 

    -   Windows Server 2003 SP1 ou versões posteriores
    -   Windows Small Business Server 2008
    -   Windows Small Business Server 2003

    Tenha em atenção que existem pré-requisitos adicionais para o Windows Small Business Server. Para mais informações, consulte a secção "Pré-requisitos do Windows Small Business Server".
-   Serviços de Informação Internet (IIS) 6.0 ou versões posteriores
-   Microsoft .NET Framework 2.0 ou versões posteriores
-   Tem de ter uma das seguintes bases de dados suportadas instaladas:
    -   Microsoft SQL Server 2008 Standard ou Enterprise Edition
    -   Microsoft SQL Server 2005 SP3 ou versões posteriores
    -   Windows Internal Database

    Se uma das versões suportadas do SQL Server não estiver instalada, o Assistente de Configuração do WSUS 3.0 SP2 instalará o Windows Internal Database.
-   Microsoft Management Console 3.0
-   Microsoft Report Viewer Redistributable 2008

 
<table style="border:1px solid black;">
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" ><img src="images/Dd939886.Important(WS.10).gif" />Importante</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">O Windows Server 2008 R2 requer o WSUS 3.0 SP2. Se instalar o Windows Server 2008 R2, deverá instalar o WSUS 3.0 SP2. Não instale o WSUS 3.0 SP1 no Windows Server 2008 R2.

O WSUS 3.0 SP2 não é suportado para utilização com os Serviços de Terminal no servidor front-end numa configuração de SQL remoto.
</td>
</tr>
</tbody>
</table>
 

### Pré-requisitos de Software da Consola de Administração do WSUS

-   Um dos seguintes sistemas operativos suportados: Windows Server 2008 R2, Windows Server 2008, Windows Server 2003 SP2 ou versões posteriores, Windows Small Business Server 2008 ou Windows Small Business Server 2003, Windows Vista ou Windows XP SP2
-   Microsoft .NET Framework 2.0 ou versões posteriores
-   Microsoft Management Console 3.0
-   Microsoft Report Viewer Redistributable 2008

### Requisitos Mínimos de Hardware do Servidor WSUS

A seguinte lista contém os requisitos mínimos de hardware necessários para uma instalação básica do servidor. Consulte o Guia de Distribuição de WSUS 3.0 SP2 em [http://go.microsoft.com/fwlink/?LinkId=139832](http://go.microsoft.com/fwlink/?linkid=139832) para obter uma lista abrangente de configurações de hardware suportadas.

-   Tanto a partição do sistema como a partição de instalação do WSUS 3.0 SP2 têm de estar formatadas com o sistema de ficheiros NTFS.
-   1 GB, no mínimo, de espaço livre na partição do sistema.
-   2 GB, no mínimo, de espaço livre no volume em que serão armazenados os ficheiros de base de dados.
-   São necessários, no mínimo, 20 GB de espaço livre no volume em que é armazenado o conteúdo, recomenda-se 30 GB.

 
<table style="border:1px solid black;">
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" ><img src="images/Dd939886.Important(WS.10).gif" />Importante</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Não é possível instalar o WSUS 3.0 SP2 em unidades comprimidas.
</td>
</tr>
</tbody>
</table>
 

Pré-requisitos de Configuração e Recomendações de Melhores Práticas para o Servidor WSUS.
-----------------------------------------------------------------------------------------

Antes de instalar o WSUS 3.0 SP2, certifique-se de que concluiu as tarefas aplicáveis desta secção.

### IIS

-   Na página Serviços de Função do Servidor Web do Gestor de Servidor (IIS), instale todas as funcionalidades necessárias, todos os serviços de função IIS predefinidos e os seguintes serviços de função: **ASP.NET**, **Autenticação do Windows**, **Compressão de Conteúdo Dinâmico** e **Compatibilidade de Gestão do IIS 6**.
-   Se o IIS estiver a ser executado no modo de isolamento do IIS 5.0, a instalação falhará. Desactive o modo de isolamento do IIS 5.0 antes de instalar o WSUS 3.0 SP2.
-   Se qualquer componente do IIS estiver instalado no modo de compatibilidade de 32 bits numa plataforma de 64 bits, a instalação do WSUS 3.0 SP2 pode falhar. Todos os componentes do IIS devem ser instalados no modo nativo em plataformas de 64 bits.

### Servidores Proxy

O WSUS 3.0 SP2 permite um servidor proxy só para suportar HTTP. Como procedimento recomendado, configure um segundo servidor proxy que execute HTTPS utilizando a linha de comandos (**wsusutil configuresslproxy**) antes de configurar o servidor WSUS a partir do Assistente de Configuração ou da Consola de Administração.

### Web Sites em Execução na Porta 80

Se tiver dois ou mais Web sites em execução na porta 80 (por exemplo, Windows SharePoint Services), elimine todos excepto um deles antes de instalar o WSUS. Se não fizer isto, os clientes do servidor poderão não ser actualizados automaticamente.

### Programas Antivírus

Quando instalar o WSUS 3.0 SP2, pode ter de desactivar programas antivírus antes de poder efectuar a instalação com êxito. Depois de desactivar o software antivírus, reinicie o computador antes de instalar o WSUS. Reiniciar o computador impede que os ficheiros sejam bloqueados quando o processo de instalação tiver de aceder aos mesmos. Após concluir a instalação, certifique-se de que reactiva o software antivírus. Visite o Web site do fabricante do software antivírus para obter os passos exactos de desactivação e reactivação do software antivírus e da respectiva versão.

 
<table style="border:1px solid black;">
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" ><img src="images/Dd939886.Caution(WS.10).gif" />Cuidado</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Esta solução pode tornar o seu computador ou rede mais vulnerável a ataques de utilizadores mal intencionados ou software malicioso, como, por exemplo, vírus. Não recomendamos esta solução, mas estamos a fornecer estas informações para que possa implementá-la conforme entender. Utilize esta solução por sua conta e risco.

O software antivírus ajuda a proteger o seu computador contra vírus. Não transfira nem abra ficheiros de origens que não considera fidedignas, não visite Web sites que não considera fidedignos, nem abra anexos de correio electrónico quando o programa antivírus estiver desactivado.
</td>
</tr>
</tbody>
</table>
 

### Opção de Accionadores Aninhados no SQL Server

Se planear utilizar uma base de dados SQL Server como arquivo de dados do Windows Server Update Services, o administrador do SQL Server deverá confirmar se a opção de accionadores aninhados está activada antes de o administrador do WSUS instalar o WSUS 3.0 SP2. A opção de accionadores aninhados está activada por predefinição; no entanto, pode ser desactivada por um administrador do SQL Server. A Configuração do WSUS 3.0 SP2 activa a opção RECURSIVE\_TRIGGERS, que é uma opção específica de base de dados. No entanto, a Configuração do WSUS 3.0 SP2 não activa a opção de accionadores aninhados, que é uma opção global de servidor.

### Requisitos e Limitações de SQL Remoto

O WSUS 3.0 SP2 suporta a execução de uma versão compatível do software SQL Server num computador separado do computador em que a aplicação WSUS 3.0 SP2 está a ser executada. Aplicam-se os requisitos seguintes a uma instalação de SQL remoto.

-   Não é possível utilizar um servidor configurado como controlador de domínio para o back-end do par SQL remoto.
-   Não é possível executar Serviços de Terminal no computador que será o servidor front-end de uma instalação de SQL remoto.
-   Tanto o computador front-end como o computador back-end devem ser associados a um domínio do Active Directory. Se os computadores front-end e back-end estiverem em domínios diferentes, estabeleça uma fidedignidade entre os domínios antes de executar a Configuração do WSUS.
-   Se já tiver instalado o WSUS 2.0 numa configuração de SQL remoto e pretender actualizar para o WSUS 3.0 SP2, faça o seguinte antes de instalar o WSUS:
    1.  Desinstale o WSUS 2.0 (utilizando **Adicionar ou Remover Programas** no Painel de Controlo), assegurando simultaneamente que a base de dados existente permanece intacta.
    2.  Instale o SQL Server 2005 SP2 ou o SQL Server 2008 e actualize a base de dados existente.

### O IIS será reiniciado durante a Configuração do WSUS 3.0 SP2

A configuração do WSUS 3.0 SP2 irá reiniciar o IIS sem notificação, o que poderá afectar Web sites existentes na organização. Como procedimento recomendado, notifique antecipadamente as partes afectadas em relação à instalação. Tenha em atenção que, se o IIS não estiver a ser executado, a configuração do WSUS 3.0 SP2 irá iniciá-lo durante a configuração.

Pré-requisitos do Windows Small Business Server
-----------------------------------------------

Se estiver a instalar o WSUS 3.0 SP2 no Windows Small Business Server, aplicam-se os requisitos seguintes.

### Se a Raiz Virtual do IIS Estiver Restringida a Determinados Endereços IP ou Nomes de Domínio

Algumas instalações do Windows Small Business Server podem ter o Web site predefinido do IIS configurado como **restrições de endereço IP e de nome de domínio**. Se for este o caso, o Cliente Windows Update no servidor poderá não conseguir efectuar a actualização automaticamente. Remova a restrição antes de instalar o WSUS 3.0 SP2.

### Se Estiver a Utilizar um Servidor Proxy ISA

-   Se o Windows Small Business Server utilizar um servidor proxy ISA para aceder à Internet, introduza **as definições, a porta e o nome do servidor proxy** na interface de utilizador (IU) **Definições**.
-   Se o ISA estiver a utilizar a Autenticação do Windows, introduza as credenciais do servidor proxy sob a forma *DOMÍNIO*\\*utilizador*. O utilizador deve ser um membro do grupo Utilizadores Internet.

### Se Adicionou uma Sub-rede à Rede e Não Utilizou os Assistentes do Windows Small Business Server

O processo de configuração do servidor WSUS instala duas raízes virtuais do IIS no servidor: SelfUpdate e ClientWebService. A Configuração também coloca alguns ficheiros no directório raiz do Web site predefinido (na porta 80), permitindo aos computadores cliente actualizarem-se automaticamente através do Web site predefinido. Por predefinição, o Web site predefinido está configurado para negar o acesso a qualquer endereço IP que não o localhost ou sub-redes específicas ligadas ao servidor. Consequentemente, os computadores cliente que não se encontrem no localhost ou nessas sub-redes específicas não podem actualizar-se automaticamente. Se tiver adicionado uma sub-rede à rede sem utilizar os assistentes do Microsoft Windows Small Business Server, efectue este procedimento:

1.  Em Gestão do Servidor, expanda **Gestão Avançada**, expanda **Serviços de Informação Internet**, expanda **Web Sites**, expanda **Web Site Predefinido**, clique com o botão direito do rato no directório virtual **Selfupdate** e, em seguida, clique em **Propriedades**.
2.  Clique em **Segurança de Directórios**.
3.  Em **Restrições de endereço IP e de nome de domínio**, clique em **Editar** e, em seguida, clique em **Acesso Concedido**.
4.  Clique em **OK**, clique com o botão direito do rato no directório virtual **ClientWebService** e, em seguida, clique em **Propriedades**.
5.  Clique em **Segurança de Directórios**.
6.  Em **Restrições de endereço IP e de nome de domínio**, clique em **Editar** e, em seguida, clique em **Acesso Concedido**.

Requisitos de Sistema para a Instalação da Consola Remota do WSUS 3.0 SP2.
--------------------------------------------------------------------------

A Consola Remota do WSUS 3.0 SP2 pode ser instalada num dos seguintes sistemas operativos:

-   Windows Server 2008 R2, Windows Server 2008 SP1 ou versões posteriores, Windows Server 2003 SP2 ou versões posteriores, Windows Small Business Server 2003, Windows Small Business Server 2005 ou Windows Small Business Server 2008, Windows Vista ou Windows XP Professional SP3 ou versões posteriores.

Requisitos de Sistema para a Instalação Cliente do WSUS
-------------------------------------------------------

O serviço Actualizações Automáticas, o software cliente do WSUS, pode ser instalado num dos seguintes sistemas operativos:

-   Windows Server 2008 R2, Windows Server 2008 SP1 ou versões posteriores, Windows Server 2003 SP2 ou versões posteriores, Windows Small Business Server 2003, Windows Small Business Server 2005 ou Windows Small Business Server 2008, Windows Vista, Windows XP Professional RTM, Windows XP Professional SP1, Windows XP Professional SP2, Windows XP Professional SP3 ou versões posteriores, Windows 2000 SP4 ou cliente Windows 7.

Requisitos e Recomendações de Actualização
------------------------------------------

As seguintes versões do WSUS podem ser actualizadas para o WSUS 3.0 SP2, não sendo necessário desinstalar a versão anterior:

-   WSUS 2.0, 2.0 SP1, 3.0 e 3.0 SP1.

As actualizações de WSUS 1.0 para WSUS 3.0 SP2 não são suportadas. Desinstale o Software Update Services (SUS) 1.0 antes de instalar o WSUS 3.0 SP2.

O Windows Server 2008 R2 requer o WSUS 3.0 SP2. Se instalar o Windows Server 2008 R2, deverá instalar o WSUS 3.0 SP2. Não instale o WSUS 3.0 SP1 no Windows Server 2008 R2.

#### Antes de Actualizar para o WSUS 3.0 SP2

1.  Verifique se existem erros recentes nos registos de eventos, problemas de sincronização entre servidores a jusante e servidores a montante e problemas reportados por clientes. Resolva estes problemas antes de efectuar a actualização.

2.  Opcionalmente, poderá executar DBCC CHECKDB para garantir que a base de dados do WSUS está indexada correctamente. Para mais informações sobre DBCC CHECKDB, consulte [DBCC CHECKDB](http://go.microsoft.com/fwlink/?linkid=86948).

3.  Efectue uma cópia de segurança da base de dados do WSUS. Note que a configuração do WSUS 3.0 SP2 adicionará a nova base de dados ao directório predefinido, que é *unidade*\\WSUS (*unidade* é a unidade NTFS local que tem mais espaço livre). Se já existir uma cópia de segurança da base de dados neste directório, esta poderá ser substituída. Como procedimento recomendado, guarde uma cópia de segurança da base de dados da versão actual do WSUS numa localização diferente antes de actualizar para o WSUS 3.0 SP2.

4.  Se alterou manualmente a porta utilizada pelo WSUS (ou seja, se não utilizou o utilitário Wsusutil) e está a executar o SUS 1.0 ou WSUS 2.0, inicie o Web site predefinido antes de desinstalar o SUS 1.0 ou o WSUS 2.0 de 64 bits.

5.  Se estiverem abertas ligações a uma base de dados do WSUS existente (por exemplo, se o SQL Server Management Studio estiver aberto), a instalação pode falhar. Feche todas as ligações antes de instalar o WSUS 3.0 SP2.

### Recuperar de uma Actualização Com Falhas

Se estiver a actualizar de uma versão anterior do WSUS para o WSUS 3.0 SP2 e a actualização falhar (por qualquer razão, excepto tentar uma actualização não suportada a partir de SUS 1.0), efectue as seguintes tarefas.

1.  Reinstale a versão anterior do WSUS.
2.  Restaure a base de dados a partir da cópia de segurança que fez antes de tentar actualizar. Não poderá concluir uma actualização com êxito se existir uma base de dados do WSUS 3.0 SP2 de uma instalação anterior. Na maioria dos casos, o WSUS também cria automaticamente uma cópia de segurança. Procure a localização no ficheiro WSUSSetup.log.
3.  Reveja os registos para determinar a causa da falha e resolva o problema.
4.  Instale o WSUS 3.0 SP2.

### A alteração do nome do computador antes da actualização para o WSUS 3.0 SP2 pode fazer com que a actualização falhe

Se alterar o nome do computador depois de instalar o WSUS 2.0 e antes de actualizar para o WSUS 3.0 SP2, a actualização pode falhar.

Utilize o seguinte script para remover e voltar a adicionar os grupos ASPNET e Administradores WSUS. Em seguida, execute novamente a actualização.

        ```

### Se migrou de MSDE para SQL Server 2008 ou SQL Server 2005 no WSUS 2.0, tem de alterar um valor de registo.

Se tem uma instalação do WSUS 2.0 e migrou para SQL Server 2008 ou SQL Server 2005, tem de alterar o valor **HKLM\\SOFTWARE\\Microsoft\\Update Services\\Server\\Setup\\WmsdeInstalled** de 1 para 0. Se não o fizer antes de actualizar para o WSUS 3.0 SP2, a actualização falhará.

### Se desinstalar o WSUS 3.0 SP2 e se esquecer dos ficheiros de registo, poderão não ter as permissões apropriadas após a reinstalação

Se desinstalar o WSUS 3.0 SP2, tem a opção de manter os ficheiros de registo da instalação. Ao reinstalar o WSUS 3.0 SP2, os ficheiros de registo antigos poderão perder as respectivas permissões (normalmente, apenas para Administradores WSUS). Como procedimento recomendado, confirme as permissões nestes ficheiros de registo após a instalação.

### Se os clientes WSUS 2.0 tiverem actualizações com o estado "Não Aplicável", as actualizações serão apresentadas com o estado "Desconhecido" durante um curto período de tempo depois de actualizar para o WSUS 3.0 SP2.

Se um servidor WSUS 2.0 existente tem clientes que têm actualizações com o estado **Não Aplicável**, estas actualizações poderão ser listadas com um estado **Desconhecido** durante um curto período de tempo depois de actualizar para o WSUS 3.0 SP2. O estado da actualização voltará a **Não Aplicável** da próxima vez que o cliente fizer uma procura.

Instalar o WSUS 3.0 SP2
-----------------------

O Manual de Instalação Passo a Passo do WSUS em [http://go.microsoft.com/fwlink/?LinkId=139836](http://go.microsoft.com/fwlink/?linkid=139836) fornece instruções para instalar o WSUS 3.0 SP2 utilizando o Windows Server Manager ou o ficheiro WSUSSetup.exe.

Para informações completas sobre como instalar e utilizar o WSUS, consulte:

O Guia de Distribuição de WSUS em [http://go.microsoft.com/fwlink/?LinkId=139832](http://go.microsoft.com/fwlink/?linkid=139832).

O Guia de Funcionamento do WSUS em [http://go.microsoft.com/fwlink/?LinkId=139838](http://go.microsoft.com/fwlink/?linkid=139838).

Configurar Parâmetros da Linha de Comandos para Instalações Autónomas do WSUS 3.0 SP2
-------------------------------------------------------------------------------------

É possível efectuar instalações autónomas do WSUS 3.0 SP2 utilizando o programa de configuração da linha de comandos do WSUS. Esta tabela mostra os parâmetros da linha de comandos para a configuração do WSUS 3.0 SP2.

###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Opção</th>
<th style="border:1px solid black;" >Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><strong>/q</strong></td>
<td style="border:1px solid black;">Efectuar uma instalação automática.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>/u</strong></td>
<td style="border:1px solid black;">Desinstalar.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><strong>/p</strong></td>
<td style="border:1px solid black;">Verificação de pré-requisitos. Inspecciona o sistema e reporta os pré-requisitos em falta.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>/?, /h</strong></td>
<td style="border:1px solid black;">Mostra os parâmetros da linha de comandos e respectivas descrições.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><strong>/g</strong></td>
<td style="border:1px solid black;">Actualização a partir da versão anterior do WSUS. (As actualizações a partir do SUS 1.0 não são suportadas.) O único parâmetro válido com esta opção é /q (instalação automática). A única propriedade válida com esta opção é DEFAULT_WEBSITE.</td>
</tr>
</tbody>
</table>
  
Esta tabela mostra as propriedades da linha de comandos para o WSUS 3.0 SP2.
  
###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Propriedade</th>
<th style="border:1px solid black;" >Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">CONTENT_LOCAL</td>
<td style="border:1px solid black;">0=conteúdo alojado localmente, 1=alojar no Microsoft Update</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">CONTENT_DIR</td>
<td style="border:1px solid black;">Caminho para o directório de conteúdo. A predefinição é <em>WSUSInstallationDrive\WSUS\WSUSContent</em>, em que <em>WSUSInstallationDrive</em> é a unidade local que tem mais espaço livre.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">WYUKON_DATA_DIR</td>
<td style="border:1px solid black;">Caminho para o directório de dados do Windows Internal Database.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">SQLINSTANCE_NAME</td>
<td style="border:1px solid black;">O nome deve ser apresentado no formato <em>NomeServidor</em>\<em>NomeInstânciaSQL</em>. Se a instância de base de dados estiver na máquina local, utilize a variável de ambiente %COMPUTERNAME%. Se não estiver presente uma instância existente, a predefinição é %COMPUTERNAME%\WSUS.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DEFAULT_WEBSITE</td>
<td style="border:1px solid black;">0=porta 8530, 1=porta 80</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">PREREQ_CHECK_LOG</td>
<td style="border:1px solid black;">Caminho e nome de ficheiro para o ficheiro de registo</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">CONSOLE_INSTALL</td>
<td style="border:1px solid black;">0=instalar o servidor WSUS, 1=instalar apenas a consola</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">ENABLE_INVENTORY</td>
<td style="border:1px solid black;">0=não instalar funcionalidades de inventário, 1=instalar funcionalidades de inventário</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DELETE_DATABASE</td>
<td style="border:1px solid black;">0=reter base de dados, 1=remover base de dados</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DELETE_CONTENT</td>
<td style="border:1px solid black;">0=reter ficheiros de conteúdo, 1=remover ficheiros de conteúdo</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DELETE_LOGS</td>
<td style="border:1px solid black;">0=reter ficheiros de registo, 1=remover ficheiros de registo (utilizado com o parâmetro de instalação /u)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">CREATE_DATABASE</td>
<td style="border:1px solid black;">0=utilizar base de dados actual, 1=criar base de dados</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">PROGRESS_WINDOW_HANDLE</td>
<td style="border:1px solid black;">Identificador de janela para devolver mensagens de evolução do Windows Installer</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MU_ROLLUP</td>
<td style="border:1px solid black;">1=participar no Programa de Melhoramento do Microsoft Update, 0=não participar no Programa de Melhoramento do Microsoft Update</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">FRONTEND_SETUP</td>
<td style="border:1px solid black;">1=não escrever a localização de conteúdo na base de dados, 0=escrever a localização de conteúdo na base de dados (para NLB)</td>
</tr>
</tbody>
</table>
  
### Utilização de Exemplo
  
```  
WSUSSetup.exe /q DEFAULT\_WEBSITE=0 (instalação no modo silencioso utilizando a porta 8530) WSUSSetup.exe /q /u (desinstalar o WSUS)  
```
 
<table style="border:1px solid black;">
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" ><img src="images/Dd939886.Important(WS.10).gif" />Importante</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Se instalar o WSUS 3.0 SP2 no modo silencioso (/q) e o computador não tiver todos os pré-requisitos instalados, a instalação irá gerar um ficheiro com o nome WSUSPreReqCheck.xml e irá guardá-lo no directório %TEMP%.
</td>
</tr>
</tbody>
</table>
 

<span id="BKMK_KnownIssues"></span>
Problemas Conhecidos
--------------------

-   Após a conclusão com êxito do Assistente de Instalação do WSUS, é solicitado ao utilizador que clique em **Concluir**. Em casos raros, é apresentada uma caixa de diálogo que contém a mensagem seguinte, “**Ocorreu um erro durante a comunicação com o servidor e este assistente tem de ser fechado. Poderá reiniciar o Assistente de Configuração do Servidor WSUS na página Opções na consola WSUS.**” Para garantir que as selecções de instalação foram guardadas, abra a página **Opções** na consola de administração do WSUS e confirme as definições em cada secção.
-   **As versões localizadas do cliente Windows Update Agent (WUA) serão disponibilizadas após a versão WSUS 3.0 SP2**. Esta situação deve-se a uma dependência da agenda de localização do Windows 7. Durante o período de tempo entre a versão WSUS 3.0 SP2 e a versão localizada do cliente WUA, este último só suporta cinco idiomas (inglês, alemão, francês, espanhol e japonês).
-   **Os novos relatórios de Actualização e Estado do Computador que foram introduzidos nesta versão SP2 não são funcionais num ambiente em que os servidores WSUS 3.0 SP1 a jusante são geridos a partir de um servidor WSUS 3.0 SP2**. Se os novos relatórios forem executados para um servidor SP1, é apresentada a seguinte mensagem de erro, “Ocorreu um erro durante a geração do relatório. Se o problema persistir, tente executar novamente o relatório ou contacte o administrador de rede.” Uma nova execução do relatório não irá resolver o problema e este problema também não está relacionado com a rede. Os novos relatórios dependem da funcionalidade API que não existe no SP1, no entanto, a Consola de Administração do SP2 não bloqueia os novos relatórios quando gere um servidor SP1.
-   **A actualização para o WSUS 3.0 SP2 falha quando o SSL está configurado sem o nome do certificado**. A existência de um nome do certificado é obrigatória se configurar o SSL.
-   **O WSUS 3.0 SP2 com o Base de dados interna do Windows instalado no Windows Server 2008 impede a actualização para o Windows Server 2008 R2**. Antes de continuar a actualização para o Windows Server 2008 R2, é apresentada uma mensagem de erro do Relatório de Compatibilidade solicitando ao utilizador que desactive o Base de dados interna do Windows. É necessário actualizar o Base de dados interna do Windows antes de continuar a actualização para o Windows Server 2008 R2. Consulte [Como obter o service pack mais recente do Windows Internal Database](http://go.microsoft.com/fwlink/?linkid=162104) (http://go.microsoft.com/fwlink/?LinkId=162104) para obter instruções e mais informações sobre a actualização Base de dados interna do Windows.

Aviso de Direitos de Autor
--------------------------

As informações contidas neste documento, incluindo URLs e outras referências a Web sites, estão sujeitas a alterações sem aviso prévio. Os nomes de empresas, organizações, produtos, nomes de domínio, endereços de correio electrónico, logótipos, pessoas, locais e eventos mencionados neste documento são fictícios e não se destinam a representar qualquer empresa, organização, produto, nome de domínio, endereço de correio electrónico, logótipo, pessoa, local ou evento real, salvo indicação em contrário. É da responsabilidade do utilizador agir em conformidade com todas as leis de direitos de autor aplicáveis. Sem prejuízo dos direitos de autor, nenhuma parte deste documento pode ser reproduzida, armazenada ou introduzida num sistema de recuperação, ou transmitida sob qualquer forma ou por qualquer meio (electrónico, mecânico, fotocópia, gravação ou outro), para qualquer fim, sem a permissão expressa, por escrito, da Microsoft Corporation.

Neste documento, podem ser feitas referências a patentes ou a pedidos de patentes pendentes, marcas comerciais, direitos de autor ou outros direitos de propriedade intelectual da Microsoft. Salvo disposição expressa em qualquer contrato de licença escrito da Microsoft, o facto de este documento lhe ser fornecido não lhe concede quaisquer direitos sobre essas patentes, marcas comerciais, direitos de autor ou outro tipo de propriedade intelectual.

© 2009 Microsoft Corporation. Todos os direitos reservados.

Microsoft, Active Directory, ActiveX, Authenticode, Excel, InfoPath, Internet Explorer, MSDN, Outlook, Visual Studio, Win32, Windows, Windows Server e Windows Vista são marcas comerciais do grupo de empresas da Microsoft.

Todas as restantes marcas comerciais são propriedade dos respectivos proprietários.
