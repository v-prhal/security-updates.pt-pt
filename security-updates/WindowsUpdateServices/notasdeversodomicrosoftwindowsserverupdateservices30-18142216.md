---
TOCTitle: 'Notas de Versão do Microsoft Windows Server Update Services 3.0'
Title: 'Notas de Versão do Microsoft Windows Server Update Services 3.0'
ms:assetid: '94d1385f-4872-4c29-8822-3a4ec5e45ae4'
ms:contentKeyID: 18142216
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc708491(v=WS.10)'
---

Notas de Versão do Microsoft Windows Server Update Services 3.0
===============================================================

Estas notas de versão descrevem problemas conhecidos que afectam o Microsoft® Windows® Server Update Services (WSUS) 3.0 e incluem recomendações e requisitos para a instalação da aplicação. Estas notas contêm as secções seguintes:

-   Requisitos do sistema para a instalação do servidor WSUS 3.0
-   Requisitos de configuração para a instalação do servidor WSUS 3.0
-   Requisitos do sistema para a instalação da consola remota WSUS 3.0
-   Requisitos de configuração para consolas remotas WSUS 3.0
-   Requisitos do sistema para instalação de clientes
-   Requisitos de software para a instalação do servidor WSUS 3.0
-   Requisitos mínimos de espaço em disco para a instalação do servidor WSUS 3.0
-   Requisitos de actualização do WSUS 3.0
-   Parâmetros de linha de comandos do Programa de Configuração
-   Problemas de configuração e actualização
-   Problemas conhecidos
-   WSUS 3.0 no Windows Server® 2008
-   O WSUS 3.0 no Windows Small Business Server 2003

| ![](images/Cc708491.note(WS.10).gif)Nota                                                                                                                                                                                                                       |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Existe uma cópia deste documento disponível para transferência no [Centro de Transferências da Microsoft](http://go.microsoft.com/fwlink/?linkid=71220) ([http://go.microsoft.com/fwlink/?LinkId=71220](http://go.microsoft.com/fwlink/?linkid=71220)). Esta página poderá estar em inglês. |

Problema de configuração importante: Tem de substituir a palavra-passe do servidor proxy no assistente de configuração
----------------------------------------------------------------------------------------------------------------------

Se estiver a utilizar um servidor proxy que requeira um nome de utilizador/palavra-passe para autenticação, o servidor WSUS poderá não sincronizar actualizações caso a palavra-passe do servidor proxy não seja substituída ao executar o Assistente de Configuração do Servidor WSUS. Uma vez que o assistente de configuração é iniciado automaticamente no final da configuração, este problema pode causar erros de sincronização depois de actualizar uma versão mais antiga do WSUS para o WSUS 3.0.

Pode evitar este problema cancelando o assistente de configuração após a actualização, ou voltando a introduzir a palavra-passe proxy correcta ao executar o assistente de configuração. Para recuperar deste problema após a sua ocorrência, aceda a **Origem de Actualização e Servidor Proxy** na página de **Opções**, volte a introduzir a palavra-passe proxy e guarde a definição.

Requisitos do sistema para a instalação do servidor WSUS 3.0
------------------------------------------------------------

#### O servidor WSUS 3.0 é suportado no Windows Server 2003 Service Pack 1 e Windows Server 2008

O servidor WSUS 3.0 é suportado no Windows Server 2003 Service Pack 1 e Windows Server 2008.

#### O Windows 2000 Server não é suportado para servidores WSUS 3.0

O Microsoft Windows® 2000 Server não é um sistema operativo suportado para servidores WSUS 3.0.

#### O WSUS 3.0 não é suportado em servidores a executar Serviços de Terminal

Apesar de o WSUS 3.0 poder ser executado em servidores a executar Serviços de Terminal, tal prática não é suportada nem recomendada. O WSUS 3.0 não será executado num servidor a executar Serviços de Terminal em configurações que utilizem implementações de SQL Server remoto. Como todas as acções personalizadas remotas (incluindo a instalação) num servidor de licença do Servidor de Terminais serão executadas como a conta do sistema e a conta do sistema do servidor pode não ter permissões no SQL Server remoto, a instalação pode falhar.

Requisitos de configuração para a instalação do servidor WSUS 3.0
-----------------------------------------------------------------

#### O IIS tem de estar instalado

O Microsoft Windows Server Update Services 3.0 requer os Serviços de informação Internet (IIS), que não estão instalados por predefinição no Microsoft Windows Server 2003 ou no Windows Server 2008. Se tentar instalar o WSUS 3.0 sem o IIS, a Configuração do Windows Server Update Services apresenta uma mensagem de erro a indicar que o IIS não está instalado

#### Se o IIS estiver a ser executado no modo de isolamento do IIS 5.0, a instalação irá falhar

Se actualizou o servidor do Windows 2000 Server para o Windows Server 2003, o IIS poderá estar a ser executado no modo de compatibilidade do IIS 5.0. É também possível activar o modo de isolamento do IIS 5.0 no Gestor de IIS. Tal fará com que a instalação falhe. Será necessário desactivar o modo de isolamento do IIS 5.0 antes de instalar o WSUS 3.0.

#### Se qualquer componente do IIS estiver instalado no modo de compatibilidade de 32 bits numa plataforma de 64 bits, a instalação do WSUS 3.0 pode falhar

Todos os componentes do IIS devem ser instalados no modo nativo em plataformas de 64 bits. A instalação pode falhar se qualquer componente do IIS estiver num modo de compatibilidade de 32 bits

#### Os servidores proxy têm de suportar HTTP e HTTPS

Quando configura o servidor de raiz do WSUS (o servidor WSUS que recebe as actualizações directamente a partir do Microsoft Update) e existe um servidor proxy entre o servidor WSUS e a Internet, o servidor proxy tem de suportar HTTP e HTTPS.

#### Se dois ou mais Web sites já estiverem a ser executados na porta 80, elimine todos excepto um deles antes de instalar o WSUS

Se tiver dois ou mais Web sites a serem executados na porta 80 (por exemplo, Windows® SharePoint® Services), deverá eliminar todos excepto um deles antes de instalar o WSUS. Caso não o faça, os clientes do servidor poderão não conseguir actualizar-se.

#### Quando instalar o WSUS 3.0, pode ser necessário desactivar programas antivírus

Quando instalar o WSUS 3.0, pode ser necessário desactivar programas antivírus, antes de poder efectuar a instalação com êxito. Depois de desactivar o programa antivírus, reinicie o computador antes de iniciar a instalação do WSUS. Reiniciar o computador impede que os ficheiros sejam bloqueados quando o processo de instalação necessitar de aceder aos mesmos. Após concluir a instalação, certifique-se de que reactiva o programa antivírus. Visite o Web site do fornecedor do programa antivírus para ter os passos exactos de desactivação e reactivação do programa de antivírus e respectiva versão.

| ![](images/Cc708491.Caution(WS.10).gif)Atenção                                                                                                                                                                                                                               |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Esta solução pode tornar o seu computador ou rede mais vulnerável a ataques de utilizadores ou software malicioso, tal como os vírus. Não recomendamos esta solução, mas estamos a fornecer estas informações para que possa implementá-la conforme entender. Utilize esta solução por sua conta e risco. |

| ![](images/Cc708491.note(WS.10).gif)Nota                                                                                                                                                                                                                                          |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Um programa antivírus destina-se a ajudá-lo a proteger o computador de vírus. Não transfira ou abra ficheiros a partir de origens que não considera fidedignas, não visite Web sites que não considera fidedignos, nem abra anexos de correio electrónico quando o seu programa antivírus estiver desactivado. |

#### O WSUS 3.0 requer que a opção de accionadores aninhados esteja activada no SQL Server

A opção de accionadores aninhados está activada por predefinição; no entanto, pode ser desactivada por um administrador do SQL Server.

Se planear utilizar uma base de dados SQL Server como arquivo de dados do Windows Server Update Services, o administrador do SQL Server deverá confirmar que a opção de accionadores aninhados está activada antes de o administrador do WSUS 3.0 instalar o WSUS 3.0 e especificar a base de dados durante a configuração.

O Programa de Configuração do WSUS 3.0 activa a opção RECURSIVE\_TRIGGERS, que é uma opção específica de base de dados; no entanto, não activa a opção de accionadores aninhados, que é uma opção global de servidor.

Para ver se a opção de accionadores aninhados está activada, utilize:

**sp\_configure 'nested triggers'**

Para activar a opção de accionadores aninhados no SQL Server, execute o seguinte a partir de um ficheiro batch no computador com SQL Server:

**sp\_configure 'nested triggers', 1**

**GO**

**RECONFIGURE**

**GO**

Se não tiver o SQL Server Management Studio no servidor, convém executar scripts de SQL a partir da linha de comandos. Pode obter o Utilitário de Consulta de Linha de Comandos do Microsoft SQL Server 2005 a partir do [Centro de Transferências da Microsoft](http://go.microsoft.com/fwlink/?linkid=70728) (http://go.microsoft.com/fwlink/?LinkId=70728). Esta página poderá estar em inglês. Para começar, execute **sqlcmd**.

Se pretender executar scripts de SQL em Base de dados interna do Windows, também é necessário transferir o SQL Native Client a partir da mesma página de transferência.

#### Requisitos e limitações de SQL remoto

O WSUS 3.0 oferece suporte para execução de software de base de dados num computador separado do computador que contém o resto da aplicação WSUS 3.0. Existem alguns requisitos para configurar uma instalação do SQL remoto

-   Não é possível utilizar um servidor configurado como controlador de domínio para back-end do par SQL remoto.
-   Não deve estar a executar o Servidor de Terminais no computador que irá ser o servidor front-end de uma instalação do SQL remoto.
-   Deve utilizar, pelo menos, o Microsoft SQL Server 2005 Service Pack 1 (disponível no [Centro de Transferências da Microsoft](http://go.microsoft.com/fwlink/?linkid=66143) (http://go.microsoft.com/fwlink/?LinkId=66143) (esta página poderá estar em inglês) para software de base de dados no computador back-end caso esse computador esteja a executar o Windows Server 2003, e o SQL Server 2005 Service Pack 2 caso esteja a executar o Windows Server® 2008.
-   Os computadores front-end e back-end têm de estar ligados a um domínio do Active Directory; caso contrário, se se encontrarem em domínios diferentes, será necessário estabelecer fidedignidade entre domínios antes de executar a configuração do WSUS.
-   Se já tiver instalado o WSUS 2.0 numa configuração de SQL remoto e pretender actualizar para o WSUS 3.0, deve desinstalar o WSUS 2.0 (utilizando **Adicionar ou Remover Programas** no Painel de Controlo) no computador de back-end, assegurando simultaneamente que a base de dados existente permanece intacta. Em seguida, deve instalar o SQL Server 2005 SP1 ou SP2 e actualizar a base de dados existente. Finalmente, deve instalar o WSUS 3.0 no computador front-end.

#### Não é possível instalar o WSUS quando já estão instaladas determinadas versões de pré-lançamento do Internet Explorer 7 e os Serviços de Terminal

A configuração do WSUS falha quando existem versões Release Candidate do Internet Explorer 7 com os Serviços de Terminal

Requisitos do sistema para a instalação da consola remota WSUS 3.0
------------------------------------------------------------------

A consola remota WSUS 3.0 pode ser instalada nas plataformas seguintes:

-   Windows Server 2008
-   Windows Vista®
-   Windows Server 2003 SP1
-   Windows XP SP2

Requisitos de configuração para consolas remotas WSUS 3.0
---------------------------------------------------------

#### Deve utilizar uma ligação de banda larga entre uma consola de administração remota e um servidor WSUS 3.0

Pode ter alguns problemas de desempenho se estabelecer ligação ao servidor WSUS 3.0 com uma consola de administração remota através de uma ligação WAN de banda estreita. É possível limitar o número de actualizações e computadores que visualiza filtrando as vistas de actualizações e computadores, mas é recomendada a utilização de uma ligação de banda larga entre a consola de administração remota e os servidores WSUS 3.0. Se tiver problemas de desempenho com a consola remota, recomendamos que estabeleça ligação ao servidor utilizando o Servidor de Terminais para gestão remota.

Requisitos do sistema para instalação de clientes
-------------------------------------------------

A funcionalidade Actualizações Automáticas é o cliente de software do WSUS. Pode ser utilizada com o WSUS em qualquer dos sistemas operativos seguintes:

-   Windows Vista
-   Windows Server 2008
-   Microsoft Windows Server 2003, qualquer edição
-   Microsoft Windows XP Professional SP2
-   Microsoft Windows 2000 Professional SP4, Windows 2000 Server SP4 ou Windows 2000 Advanced Server com SP4

Requisitos de software para a instalação do servidor WSUS 3.0
-------------------------------------------------------------

A tabela seguinte mostra o software necessário para plataformas Windows Server 2003 SP1. O software necessário para o Windows Server 2008 será abordado na secção que trata do WSUS 3.0 no Windows Server 2008.

Antes de executar o Programa de Configuração do WSUS 3.0, certifique-se de que o servidor WSUS 3.0 preenche esta lista de requisitos. Se alguma destas actualizações requerer que o computador seja reiniciado quando a instalação estiver concluída, deverá reiniciá-lo antes de instalar o WSUS 3.0.

###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Requisito</th>
<th style="border:1px solid black;" >Detalhes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Serviços de Informação Internet da Microsoft (IIS)</td>
<td style="border:1px solid black;">Instale a partir do sistema operativo.
Consulte o Ponto 1: O IIS tem de estar instalado.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Microsoft .NET Framework Version 2.0 Redistributable Package (x86)</td>
<td style="border:1px solid black;">Consulte Microsoft .NET Framework Version 2.0 Redistributable Package (x86) no <a href="http://go.microsoft.com/fwlink/?linkid=68935">Centro de Transferências da Microsoft</a> (http://go.microsoft.com/fwlink/?LinkId=68935). Esta página poderá estar em inglês. Para plataformas de 64 bits, consulte Microsoft .NET Framework Version 2.0 Redistributable Package (x64) no <a href="http://go.microsoft.com/fwlink/?linkid=70637">Centro de Transferências da Microsoft</a> (http://go.microsoft.com/fwlink/?LinkId=70637). Esta página poderá estar em inglês.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Consola de Gestão da Microsoft 3.0 para Windows Server 2003</td>
<td style="border:1px solid black;">Isto é um pré-requisito para utilizar a IU do WSUS 3.0. Consulte Consola de Gestão da Microsoft 3.0 para Windows Server 2003 (KB907265) no <a href="http://go.microsoft.com/fwlink/?linkid=70412">Centro de Transferências da Microsoft</a> (http://go.microsoft.com/fwlink/?LinkId=70412) (esta página poderá estar em inglês). Para plataformas de 64 bits, consulte Consola de Gestão da Microsoft 3.0 para Windows Server 2003 x64 Edition (KB907265) no <a href="http://go.microsoft.com/fwlink/?linkid=70638">Centro de Transferências da Microsoft</a> (http://go.microsoft.com/fwlink/?LinkId=70638). Esta página poderá estar em inglês.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Microsoft Report Viewer</td>
<td style="border:1px solid black;">Isto é um pré-requisito para utilizar a IU do WSUS 3.0. Consulte Microsoft Report Viewer Redistributable 2005 no <a href="http://go.microsoft.com/fwlink/?linkid=70410">Centro de Transferências da Microsoft</a> (http://go.microsoft.com/fwlink/?LinkId=70410). Esta página poderá estar em inglês.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">SQL Server 2005 (opcional)</td>
<td style="border:1px solid black;">O WSUS 3.0 irá instalar o Base de dados interna do Windows caso ainda não se encontre instalada uma versão compatível do SQL Server. Se planear utilizar uma base de dados SQL Server completa, terá de utilizar (no mínimo) o SQL Server 2005 SP1 (disponível no <a href="http://go.microsoft.com/fwlink/?linkid=66143">Centro de Transferências da Microsoft</a> (http://go.microsoft.com/fwlink/?LinkId=66143) no Windows Server 2003, ou o SQL Server 2005 SP2 (disponível no <a href="http://go.microsoft.com/fwlink/?linkid=84823">Centro de Transferências da Microsoft</a> em http://go.microsoft.com/fwlink/?LinkId=84823) para Windows Server 2008. Estas páginas poderão estar em inglês.</td>
</tr>
</tbody>
</table>
  
| ![](images/Cc708491.note(WS.10).gif)Nota                                                                                                                                                                                                                                                                                                              |  
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
| Se o WSUS 2.0 já tiver sido instalado anteriormente e estiver a utilizar o SQL Server 2000, SQL Server Desktop Engine 2000 ou qualquer base de dados do SQL Server anterior ao SQL Server 2005 SP1 (ou SQL Server 2005 SP2 em Windows Server 2008), o programa de instalação do WSUS 3.0 fará a instalação de Base de dados interna do Windows® e migrará para aí a base de dados. |
  
Requisitos mínimos de espaço em disco para a instalação do servidor WSUS 3.0  
----------------------------------------------------------------------------
  
Seguem-se os requisitos mínimos de espaço em disco para instalação do Windows Server Update Services:
  
-   1 GB na partição do sistema  
-   2 GB para o volume no qual os ficheiros de base de dados serão armazenados  
-   20 GB para o volume em que o conteúdo é armazenado
  
| ![](images/Cc708491.Important(WS.10).gif)Importante                                  |  
|-------------------------------------------------------------------------------------------------------------------|  
| Não é possível instalar o WSUS 3.0 em unidades comprimidas. Verifique se a unidade escolhida não está comprimida. |
  
Requisitos de actualização do WSUS 3.0  
--------------------------------------
  
#### Certifique-se de que a sua instalação do WSUS está a funcionar correctamente e efectue uma cópia de segurança da base de dados do WSUS antes de proceder à actualização
  
Se estiver a actualizar para o WSUS 3.0 a partir de uma versão anterior, certifique-se de que a instalação actual está a funcionar correctamente e efectue uma cópia de segurança da base de dados do WSUS antes de proceder à actualização.
  
1.  Verifique a existência de erros recentes nos registos de eventos, problemas de sincronização entre servidores a jusante e a montante, ou problemas com clientes não relatados. Antes de continuar, certifique-se de que estes problemas se encontram resolvidos.  
2.  Poderá querer executar o DBCC CHECKDB para garantir que a base de dados do WSUS está indexada correctamente. Para mais informações sobre o CHECKDB, consulte [DBCC CHECKDB](http://go.microsoft.com/fwlink/?linkid=86948) (http://go.microsoft.com/fwlink/?LinkId=86948).  
3.  Efectue uma cópia de segurança da base de dados do WSUS.
  
#### O Software Update Services 1.0 deve ser desinstalado
  
A instalação do WSUS 3.0 falhará se o Software Update Services 1.0 estiver instalado no mesmo computador. Deve desinstalar o Software Update Services 1.0 antes de instalar o WSUS 3.0.
  
#### A actualização de uma versão beta do WSUS 3.0 para a versão RTM do WSUS 3.0 não é suportada, mas a actualização da versão RC para a versão RTM é permitida
  
Se já tiver uma versão beta do WSUS 3.0 instalada, necessitará de desinstalá-la e de eliminar a base de dados antes de instalar a versão RTM do WSUS 3.0. Só é possível efectuar a actualização de uma versão RC para a versão RTM.
  
#### Não é possível efectuar a actualização do WSUS 2.0 para WSUS 3.0 num sistema operativo de 64 bits
  
O WSUS 2.0 não é suportado em sistemas operativos de 64 bits. Não é possível efectuar a actualização do WSUS 2.0 para WSUS 3.0 em sistemas de 64 bits.
  
Parâmetros de linha de comandos do Programa de Configuração  
-----------------------------------------------------------
  
É possível efectuar instalações automáticas do WSUS 3.0 utilizando os parâmetros de linha de comandos do WSUS. Esta tabela mostra os parâmetros de linha de comandos para o WSUS 3.0.
  
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
<td style="border:1px solid black;">Efectuar uma instalação silenciosa.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>/u</strong></td>
<td style="border:1px solid black;">Desinstalar o produto. Desinstala também a instância Base de dados interna do Windows caso se encontre instalada.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><strong>/p</strong></td>
<td style="border:1px solid black;">Apenas verificação de pré-requisito. Não instala o produto, mas inspecciona o sistema e apresenta quaisquer pré-requisitos em falta.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>/?, /h</strong></td>
<td style="border:1px solid black;">Apresentar parâmetros de linha de comandos e as respectivas descrições.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><strong>/g</strong></td>
<td style="border:1px solid black;">Actualizar a partir da versão 2.0 do WSUS. O único parâmetro válido com esta opção é /q (instalação silenciosa). A única propriedade válida com esta opção é DEFAULT_WEBSITE.</td>
</tr>
</tbody>
</table>
  
Esta tabela mostra as propriedades de linha de comandos para o WSUS 3.0.
  
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
<td style="border:1px solid black;">Caminho para o directório de conteúdo. A predefinição é <em>UnidadeInstalaçãoWSUS</em><strong>\WSUS\WSUSContent</strong>, em que <em>UnidadeInstalaçãoWSUS</em> é a unidade local com a maior quantidade de espaço livre.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">WYUKON_DATA_DIR</td>
<td style="border:1px solid black;">Caminho para o directório de dados Base de dados interna do Windows.</td>
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
<td style="border:1px solid black;">0=reter ficheiros de registo, 1=remover ficheiros de registo (utilizado com o comutador de instalação /u).</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">CREATE_DATABASE</td>
<td style="border:1px solid black;">0=utilizar base de dados actual, 1=criar base de dados</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">PROGRESS_WINDOW_HANDLE</td>
<td style="border:1px solid black;">Identificador de janela para devolver mensagens de progresso MSI</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MU_ROLLUP</td>
<td style="border:1px solid black;">1=participar no Programa de Melhoramento do Microsoft Update, 0=não participar</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">FRONTEND_SETUP</td>
<td style="border:1px solid black;">1=não escrever a localização de conteúdo na base de dados, 0=escrever a localização de conteúdo na base de dados (para NLB)</td>
</tr>
</tbody>
</table>
  
#### Utilização de Exemplo
  
```  
WSUSSetup.exe /q DEFAULT\_WEBSITE=0 (install in quiet mode using port 8530) WSUSSetup.exe /q /u (uninstall WSUS)  
```  
| ![](images/Cc708491.Important(WS.10).gif)Importante                                                                                                                                    |  
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
| Se instalar o WSUS 3.0 no modo silencioso (/q) e o computador não tiver todos os pré-requisitos instalados, a instalação irá gerar um ficheiro com o nome WSUSPreReqCheck.xml e irá guardá-lo no directório %TEMP%. |
  
Problemas de configuração  
-------------------------
  
#### O IIS será reiniciado pelo Programa de Configuração do WSUS 3.0
  
O Programa de Configuração do WSUS 3.0 irá reiniciar o IIS sem notificação, o que poderá afectar Web sites existentes na organização. Se o IIS não estiver em execução, será iniciado pela configuração do WSUS 3.0.
  
#### Se estiverem abertas ligações para uma base de dados existente do WSUS, a instalação pode falhar
  
Se estiver a actualizar para o WSUS 3.0 a partir de uma instalação existente e ainda estiverem abertas as ligações a uma base de dados WSUS existente (por exemplo, se o SQL Server Management Studio estiver aberto), a instalação pode falhar. Feche todas as ligações e reinstale o WSUS 3.0.
  
#### A configuração do WSUS mostra o directório errado para os ficheiros de base de dados
  
Na configuração do WSUS, o ecrã **Pronto para Instalar** indica incorrectamente que o directório principal é a localização da base de dados. Por exemplo, a localização predefinida é %systemdrive%\\WSUS\\UpdateServicesDbFiles, mas esta localização aparece incorrectamente como %systemdrive%\\WSUS.
  
#### Se o WSUS for instalado numa máquina com pacotes de idiomas com Interface de Utilizador Multilingue (MUI) e com um idioma predefinido que não o inglês, a Ajuda será apresentada no idioma predefinido, e não em inglês
  
Se tiver uma máquina com pacotes de idiomas com Interface de Utilizador Multilingue (MUI) e com um idioma predefinido que não o inglês, poderá instalar o WSUS quando a região do utilizador actual for correspondente a inglês. A interface de utilizador será apresentada em inglês, mas terá de utilizar uma solução para que a Ajuda seja apresentada em inglês. Copie o ficheiro de Ajuda .chm em inglês (*DirectórioInstalWSUS*\\documentation\\mui\\0409\\WSUS30Help.chm) para o directório de documentação principal (*DirectórioInstalWSUS*\\documentation\\WSUS30Help.chm). Nesta altura, a Ajuda deve ser apresentada correctamente em todos os idiomas.
  
Problemas de actualização  
-------------------------
  
#### A actualização do WSUS 3.0 RC para o WSUS 3.0 RTM irá fazer com que o certificado SSL não seja atribuído ao Web site do WSUS
  
O Web site do WSUS é eliminado e recriado durante a actualização do WSUS 3.0 RC para o WSUS 3.0 RTM. Consequentemente, o certificado SSL deixará de ser atribuído ao Web site do WSUS. Será necessário reatribuir o certificado após a actualização.
  
#### Recuperar de uma actualização com falha
  
Se estiver a actualizar o WSUS 2.0 para o WSUS 3.0 e a actualização falhar por um qualquer motivo, será necessário reinstalar o WSUS 2.0 e restaurar a respectiva base de dados a partir da cópia de segurança.
  
#### Não é possível actualizar do WSUS 2.0 para o WSUS 3.0, se existir uma base de dados WSUS 3.0 de uma instalação anterior
  
Se já tiver instalado anteriormente o WSUS 3.0 e, em seguida, tiver reinstalado o WSUS 2.0, tem de eliminar a base de dados do WSUS 3.0 do computador, antes de tentar reinstalar o WSUS 3.0.
  
#### A alteração do nome do computador antes da actualização para o WSUS 3.0 pode fazer com que a actualização de versão falhe
  
Se alterar o nome do computador depois de instalar o WSUS 2.0 e antes de actualizar para o WSUS 3.0, a actualização de versão pode falhar
  
Utilize o seguinte script para remover e voltar a adicionar os grupos ASPNET e Administradores WSUS. Em seguida, execute novamente a actualização.
  
Terá de substituir *&lt;DBLocation&gt;* pela pasta em que está instalada a base de dados e *&lt;ContentDirectory&gt;* pela pasta de armazenamento local.
  
```  
sqlcmd.exe -S *&lt;DBLocation&gt;* -E -Q "USE SUSDB DECLARE @asplogin varchar(200) SELECT @asplogin=name from sysusers WHERE name like '%ASPNET' EXEC sp\_revokedbaccess @asplogin" sqlcmd.exe -S *&lt;DBLocation&gt;* -E -Q "USE SUSDB DECLARE @wsusadminslogin varchar(200) SELECT @wsusadminslogin=name from sysusers WHERE name like '%WSUS Administrators' EXEC sp\_revokedbaccess @wsusadminslogin"   sqlcmd.exe -S *&lt;DBLocation&gt;* -E -Q "USE SUSDB DECLARE @asplogin varchar(200) SELECT @asplogin=HOST\_NAME()+'\\ASPNET' EXEC sp\_grantlogin @asplogin EXEC sp\_grantdbaccess @asplogin EXEC sp\_addrolemember webService,@asplogin" sqlcmd.exe -S *&lt;DBLocation&gt;* -E -Q "USE SUSDB DECLARE @wsusadminslogin varchar(200) SELECT @wsusadminslogin=HOST\_NAME()+'\\WSUS Administrators' EXEC sp\_grantlogin @wsusadminslogin EXEC sp\_grantdbaccess @wsusadminslogin EXEC sp\_addrolemember webService,@wsusadminslogin"   sqlcmd.exe -S *&lt;DBLocation&gt;* -E -Q "backup database SUSDB to disk=N'*&lt;ContentDirectory&gt;*\\SUSDB.Dat' with init"  
```
  
#### A Configuração pode substituir uma cópia de segurança da base de dados anterior
  
A configuração do WSUS 3.0 adicionará a base de dados ao directório especificado durante a configuração. Por predefinição, é *%systemdrive%*\\WSUS\\UpdateServicesDbFiles. Se houver uma cópia de segurança da base de dados anterior neste directório, será substituída pela nova base de dados. Os administradores devem fazer cópia de segurança dos ficheiros de base de dados antes de aplicar actualizações ao computador onde se encontra a base de dados.
  
#### Se procedeu à migração do MSDE para o SQL Server 2000 ou SQL Server 2005 no WSUS 2.0, será necessário alterar um valor de registo
  
Se tiver uma instalação do WSUS 2.0 e tiver migrado do SQL Server 2000 ou SQL Server 2005, será necessário alterar o valor **HKLM\\SOFTWARE\\Microsoft\\Update Services\\Server\\Setup\\WmsdeInstalled** de um 1 para 0. Caso não o faça antes da actualização para o 3.0, a actualização irá falhar.
  
#### Se a configuração do WSUS 2.0 for iniciar e cancelada, eliminará a chave do Registo WSUS
  
Se iniciar a configuração do WSUS 2.0 e, em seguida, a cancelar, a chave do registo WSUS será eliminada. Isso pode originar problemas se já tiver o WSUS 3.0 instalado. O mesmo problema ocorrerá se iniciar a desinstalação do WSUS 2.0, cancelar a operação e, em seguida, tentar efectuar a actualização do WSUS 2.0 para o WSUS 3.0.
  
#### Se desinstalar o WSUS 3.0 e se esquecer dos ficheiros de registo, poderão não ter as permissões correctas após a reinstalação
  
Quando desinstalar o WSUS 3.0, tem a opção de manter os ficheiros de registo da instalação. Ao reinstalar o WSUS 3.0, os ficheiros de registo antigos perdem as respectivas permissões (normalmente, apenas para Administradores WSUS). Deverá restaurar as permissões para estes ficheiros de registo.
  
#### Se o Windows SharePoint Services tiver sido instalado depois do WSUS 3.0 RC, terá de utilizar outra solução para actualizar para o WSUS 3.0 RTM
  
Se instalou o WSUS 3.0 RC e, em seguida, instalou o Windows SharePoint Services no mesmo computador, só poderá efectuar a actualização para o WSUS 3.0 RTM se optar por instalar na porta personalizada (porta 8530). Para efectuar esta instalação a partir da linha de comandos, abra uma shell de comandos e, em seguida, introduza o comando: **WSUSSetup /q / g/ DEFAULT\_WEBSITE=0**. (Para efectuar esta instalação utilizando a IU, escreva **WSUSSetup /g DEFAULT\_WEBSITE=0**.)
  
Se o WSUS for instalado numa máquina com pacotes de idiomas com Interface de Utilizador Multilingue (MUI), a Ajuda será apresentada no idioma predefinido, e não no idioma actual do utilizador
  
#### Se os clientes WSUS 2.0 tiverem actualizações com estado "Não Aplicável", as actualizações surgirão com a classificação "Desconhecido" durante um breve período de tempo após a actualização para o WSUS 3.0
  
Se um servidor WSUS 2.0 tiver clientes com actualizações com a indicação "Não Aplicável", estas actualizações surgirão com o estado "Desconhecido" durante um breve período de tempo após o servidor ser actualizado para o WSUS 3.0. O estado da actualização regressará a "Não Aplicável" na próxima vez que o cliente fizer uma análise.
  
Problemas Conhecidos  
--------------------
  
#### Resolução de múltiplos erros de transferência ou de repetidas falhas de sincronização de cliente
  
Se os clientes do WSUS 3.0 relatarem múltiplos erros de transferência ou se os clientes não conseguirem sincronizar com o servidor WSUS 3.0 durante um longo período de tempo, pode ter uma cache de transferência de cliente danificada. Para recuperar deste estado, pode tentar eliminar a cache de transferência do cliente a partir do sistema de ficheiros.
  
Para eliminar a cache de transferência do cliente:
  
1.  Elimine todos os ficheiros e subdirectórios nesta localização no computador cliente: **%windir%\\SoftwareDistribution\\Download**  
2.  Tente instalar a actualização sincronizando o computador cliente com o WSUS 3.0 de novo. Esta tentativa de instalação deverá falhar, sendo apresentada a seguinte mensagem de erro: **WU\_E\_DM\_NOTDOWNLOADED, "A actualização não foi transferida."**  
3.  Depois desta falha, o computador cliente irá automaticamente reiniciar a transferência e a instalação poderá prosseguir.
  
#### Se ocorrer uma falha na sincronização, tente executá-la novamente
  
Se a sincronização falhar, a primeira medida para resolução de problemas deve ser tentar sincronizar o servidor de novo. Se as sincronizações subsequentes falharem, utilize as informações de resolução de problemas do [Windows Server Update Services 3.0 Operations Guide](http://go.microsoft.com/fwlink/?linkid=81072) (http://go.microsoft.com/fwlink/?LinkId=81072). Esta página poderá estar em inglês.
  
#### A alteração da configuração do WSUS 3.0 directamente na base de dados não é suportada
  
O Windows Server Update Services armazena os respectivos dados de configuração numa base de dados do SQL Server. No entanto, a alteração dos dados de configuração acedendo-se directamente à base de dados não é suportada. Não tente modificar a configuração do WSUS 3.0 acedendo directamente à base de dados. Deve alterar a configuração do WSUS 3.0 utilizando a consola WSUS 3.0 ou iniciando as APIS do WSUS 3.0.
  
#### As falhas de transferência não são relatadas rapidamente se as quotas de disco estiverem activadas
  
Se as quotas de disco estiverem activadas e a quota for atingida, as falhas de transferência de actualização no WSUS podem não ser relatadas de forma atempada. Para evitar esta situação, desactive as quotas de disco ou aumente a quota.
  
#### Se o WSUS 3.0 for implementado utilizando SSL, os computadores cliente podem apresentar falhas com o código de erro 0x8024400a
  
Os computadores cliente podem, por vezes, apresentar uma falha com um código de erro "0x8024400a" ao comunicarem com um servidor WSUS 3.0 utilizando SSL. Para obter uma actualização que resolva este problema, consulte o artigo [KB 905422](http://go.microsoft.com/fwlink/?linkid=70593) (http://go.microsoft.com/fwlink/?LinkId=70593). Esta página poderá estar em inglês.
  
#### A conta de domínio dos Administradores WSUS não será eliminada se o WSUS for desinstalado
  
O grupo Administradores WSUS é criado como uma conta de domínio (não uma conta local) em controladores de domínio, por isso todas as instalações que utilizam esta conta de domínio seriam desactivadas se a conta fosse eliminada no decurso da desinstalação do WSUS. Por conseguinte, a desinstalação do WSUS não irá eliminar a conta de domínio Administradores WSUS.
  
#### Se um servidor a jusante for convertido num servidor a montante, é necessário reimportar actualizações de site de catálogo
  
Se tornar um servidor a jusante num servidor a montante, também tem de reimportar todas as actualizações do site de catálogo. De outro modo, o site não conseguirá sincronizar as novas revisões de actualização de site do catálogo com este servidor.
  
#### Se estiver a utilizar o IIS com o SSL, o acesso não encriptado continua a ser possível, a menos que esteja marcada a opção "Requerer Canal Seguro"
  
Se configurar o IIS para utilizar SSL instalando um certificado, ainda é possível aceder ao site através de HTTP não encriptado, a menos que esteja marcada a opção "Requerer Canal Seguro". Para mais informações, consulte o artigo sobre a [activação da encriptação](http://go.microsoft.com/fwlink/?linkid=70601) (http://go.microsoft.com/fwlink/?LinkId=70601). Esta página poderá estar em inglês.
  
#### A importação do site do catálogo pode falhar sem permissões de leitura/escrita para a pasta %windir%\\TEMP
  
Ao efectuar uma importação do site do catálogo, a conta Serviço de Rede não tem permissão de leitura/escrita para a pasta %windir%\\TEMP, a importação pode falhar apresentando uma mensagem de erro como a seguinte: "O servidor não conseguiu processar o pedido. ---&gt; Não foi possível localizar o ficheiro 'C:\\WINDOWS\\TEMP\\*nomeFicheiroTemporário*.dll'."
  
#### O desempenho pode ser lento ao sincronizar entre o WSUS 3.0 e um servidor de réplica a jusante com o WSUS 2.0
  
Se instalar o WSUS 3.0 num servidor a montante e tentar sincronizar com um servidor de réplica a jusante com o WSUS 2.0, pode ter alguns problemas de desempenho. Para resolver este problema, consulte o artigo [KB 910847](http://go.microsoft.com/fwlink/?linkid=70669) (http://go.microsoft.com/fwlink/?LinkId=70669). Esta página poderá estar em inglês.
  
#### Se o servidor de correio estiver indisponível ou inacessível, a notificação por correio electrónico falha sem aviso prévio
  
Se o servidor de correio electrónico da rede estiver offline, o WSUS 3.0 não enviará notificações por correio electrónico, nem apresentará um aviso para o efeito. No entanto, escreverá o evento 10052 (HealthCoreEmailNotificationRed) no registo de eventos.
  
#### As definições alteradas num servidor a montante não serão imediatamente aplicadas no servidor a jusante
  
Quando a configuração do servidor a montante for alterada, pode demorar algum tempo antes de estas alterações de configuração entrarem em vigor. Por exemplo, se alterar uma definição no servidor a montante, tal como a selecção de um novo idioma, e accionar imediatamente uma sincronização no servidor a jusante, a alteração não será apresentada. Em vez disso, será aplicada ao servidor a jusante na próxima sincronização agendada. Os tempos de espera aumentam consoante o número de actualizações existentes no servidor a montante.
  
#### Desinstalar o WSUS 3.0 não desinstala a instância de base de dados
  
Se o WSUS 3.0 for desinstalado, a instância de base de dados não será desinstalada. A instância pode ser partilhada por mais de uma aplicação, causando a falha de outras aplicações se for removida.
  
Se for necessário desinstalar o Base de dados interna do Windows, os seguintes comandos desinstalam a aplicação:
  
(em plataformas de 32 bits)
  
```  
msiexec /x {CEB5780F-1A70-44A9-850F-DE6C4F6AA8FB} callerid=ocsetup.exe  
```  
(em plataformas de 64 bits)
  
```  
msiexec /x {BDD79957-5801-4A2D-B09E-852E7FA64D01} callerid=ocsetup.exe  
```  
Se pretende desinstalar o Base de dados interna do Windows Service Pack 2 do Windows Server 2008, poderá fazê-lo através do Server Manager.
  
No entanto, a remoção da aplicação pode não remover os ficheiros .mdf e .ldf predefinidos, o que irá causar a falha da subsequente instalação do WSUS 3.0. Estes ficheiros podem ser eliminados no directório %windir%\\SYSMSI\\SSEE.
  
#### Se um servidor a jusante alterar o servidor a montante, as actualizações de estado "Desconhecido" são relatadas como sendo "Não Aplicável"
  
Se um servidor a jusante começar a sincronizar a partir de um servidor a montante diferente, as actualizações que têm um estado "Desconhecido" serão relatadas no novo servidor a montante como "Não Aplicável". Este estado é temporário e será corrigido na próxima vez que o servidor a montante relatar o seu estado, depois de os respectivos clientes terem efectuado a sincronização com o mesmo.
  
#### Se um servidor de réplica do WSUS 3.0 estiver a gerir mais do que um computador ao mesmo tempo, a agregação do relatório irá falhar
  
Se um servidor de réplica do WSUS 3.0 estiver a gerir mais do que um computador ao mesmo tempo, a agregação do relatório irá falhar. Como resultado, os relatórios disponíveis para o servidor WSUS raiz estarão incompletos. Este problema será resolvido eliminando todas menos uma das entradas duplicadas do computador no servidor de réplica.
  
#### Se o tempo limite do Assistente de Limpeza do Servidor for excedido, ao ser executado em múltiplos servidores a partir de uma consola remota, será perdida a ligação a todos os servidores
  
É possível executar o Assistente de Limpeza do Servidor em múltiplos servidores a partir de uma consola remota. No entanto, se o tempo limite do processo de limpeza se esgotar num dos servidores, a consola perderá a sua ligação aos servidores. Não serão perdidos dados, mas o administrador terá repor a ligação remota com cada um dos servidores.
  
#### O Assistente de Limpeza do Servidor elimina os ficheiros após trinta dias, e não após três meses
  
Algum texto do Assistente de Limpeza do Servidor contém imprecisões. Afirma: "Elimina as actualizações que expiraram e não foram aprovadas nos últimos três meses e elimina as revisões antigas de actualizações que não foram aprovadas nos últimos três meses". O período de tempo correcto são trinta dias, e não três meses.
  
#### Iniciar e parar a ligação numa sucessão rápida gera a mensagem de erro "sem falhas" no Assistente de Configuração
  
Ao configurar o WSUS, é necessário estabelecer ligação ao servidor a montante (o servidor a montante da intranet ou do Microsoft Update) para transferir informações básicas sobre o servidor. Se clicar em **Iniciar Ligação** e clicar de imediato em **Parar Ligação**, receberá a mensagem de erro incorrecta "Não ocorreu nenhuma falha na sincronização".
  
#### Actualmente, os clientes WSUS com Windows Vista RTM têm capacidade para procurar actualizações no Microsoft Update
  
Nas versões anteriores do WSUS, os clientes com Windows Vista RTM só conseguiam obter actualizações a partir do servidor WSUS. Actualmente, com o WSUS 3.0 RTM, os clientes Vista também conseguem obter actualizações a partir do Microsoft Update. Poderá direccionar os clientes Vista para o Microsoft Update abrindo o Windows Update a partir do Painel de Controlo e clicando na hiperligação **Procurar online por actualizações de Serviço Microsoft Update**. Se a opção de Política de Grupo **Remover acesso para utilizar todas as funções do Windows Update** estiver activada, o Windows Update não apresentará a hiperligação.
  
WSUS 3.0 no Windows Server 2008  
-------------------------------
  
#### Versões Suportadas
  
O WSUS 3.0 suporta o Windows Server 2008 nas versões de 32 e 64 bits.
  
#### Pré-requisitos
  
###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Requisito</th>
<th style="border:1px solid black;" >Detalhes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Serviços de Informação Internet da Microsoft (IIS)</td>
<td style="border:1px solid black;">Instale a partir do sistema operativo. Certifique-se de que os seguintes componentes estão activados:
Autenticação do Windows
Conteúdo Estático
ASP.NET
Compatibilidade de Gestão do 6.0
Compatibilidade da Metabase do IIS</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Microsoft .NET Framework Version 2.0 Redistributable Package (x86)</td>
<td style="border:1px solid black;">Desnecessário no Windows Server 2008, já instalado como parte do sistema operativo.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Consola de Gestão da Microsoft 3.0</td>
<td style="border:1px solid black;">Desnecessário no Windows Server 2008, já instalado como parte do sistema operativo.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Microsoft Report Viewer</td>
<td style="border:1px solid black;">Isto é um pré-requisito para utilizar a IU do WSUS. Consulte Microsoft Report Viewer Redistributable 2005 no <a href="http://go.microsoft.com/fwlink/?linkid=70410">Centro de Transferências da Microsoft</a> (http://go.microsoft.com/fwlink/?LinkId=70410). Esta página poderá estar em inglês.</td>
</tr>
</tbody>
</table>
  
#### Ponto 1: É necessário actualizar o ficheiro de configuração do IIS 7.0 antes de executar o WSUS 3.0
  
Antes de executar o WSUS 3.0 no Windows Server 2008, é necessário actualizar o ficheiro de configuração do IIS. Será necessário executar os seguintes passos:
  
1. Abra o ficheiro de configuração do IIS: %WINDIR%\\system32\\inetsrv\\applicationhost.config
  
2. Na tag &lt;System.webServer&gt;&lt;modules&gt;, remova &lt;add name="CustomErrorMode"&gt;, se existir.
  
3. Na tag &lt;System.webServer&gt;&lt;modules&gt;, adicione &lt;remove name="CustomErrorMode"&gt;.
  
A tag resultante deve ter o seguinte aspecto:
  
```  
 &lt;System.webServer&gt; &lt;modules&gt; &lt;remove name="CustomErrorMode"&gt; &lt;/modules&gt; &lt;/System.webServer&gt;  
```
  
#### Ponto 2: Se pretender instalar o WSUS 3.0 na porta personalizada no Windows Server 2008 Beta 3, terá de pré-criar o Web site
  
Se pretender instalar o WSUS 3.0 no Windows Server 2008 Beta 3 e quiser configurar o WSUS para utilizar a porta personalizada 8530, será necessário criar um Web site denominado "Administração WSUS" na porta 8530 antes de iniciar o programa de instalação do WSUS.
  
O WSUS 3.0 no Windows Small Business Server 2003  
------------------------------------------------
  
#### Ponto 1: Se a raiz virtual do IIS estiver restringida a determinados endereços IP ou nomes de domínio, o servidor WSUS 3.0 não conseguirá actualizar-se automaticamente
  
Algumas instalações do Windows Small Business Server podem ter o Web site predefinido do IIS configurado como "restrições de endereço IP e nome domínio". Neste caso, o Cliente Windows Update no servidor poderá não conseguir efectuar a actualização automaticamente
  
#### Ponto 2: Instalar o WSUS 3.0 no Small Business Server - Problemas de Integração
  
-   Se o Windows Small Business Server 2003 utilizar um servidor proxy ISA para aceder à Internet, terá de introduzir o seguinte na interface de utilizador **Definições**: definições do servidor proxy, nome do servidor proxy e porta.  
-   Se o ISA estiver a utilizar a Autenticação Windows, as credenciais do servidor proxy deverão ser escritas sob a forma "DOMÍNIO\\utilizador" (sendo que o utilizador pertence ao grupo "Utilizadores Internet").
  
#### Ponto 3: Se tiver adicionado uma sub-rede à rede sem utilizar os assistentes do Windows SBS, deve efectuar o procedimento seguinte
  
O processo de configuração do servidor WSUS instala duas raízes virtuais do IIS no servidor: SelfUpdate e ClientWebService. O Programa de Configuração também coloca alguns ficheiros no directório raiz do Web site predefinido (na porta) que permitem aos computadores cliente actualizarem-se automaticamente através do Web site predefinido. Por predefinição, o Web site predefinido está configurado para recusar acesso a qualquer endereço IP que não o localhost ou sub-redes específicas ligadas ao servidor. Como resultado, os computadores cliente que não se encontrem no localhost ou nessas sub-redes específicas não podem actualizar-se automaticamente. Se tiver adicionado uma sub-rede à rede sem utilizar os assistentes do Microsoft Windows Small Business Server 2003 (Windows SBS), deve efectuar o procedimento seguinte
  
1.  Em Gestão do Servidor, expanda **Gestão Avançada**, expanda **Serviços de Informação Internet**, expanda **Web Sites**, expanda **Web Site Predefinido**, clique com o botão direito do rato no directório virtual **Selfupdate** e, em seguida, clique em **Propriedades**.  
2.  Clique em **Segurança de Directórios**.  
3.  Em **Restrições de endereço IP e de nome de domínio**, clique em **Editar** e, em seguida, clique em **Acesso Concedido**.  
4.  Clique em **OK**, clique com o botão direito do rato no directório virtual **ClientWebService** e, em seguida, clique em **Propriedades**.  
5.  Clique em **Segurança de Directórios**.  
6.  Em **Restrições de endereço IP e de nome de domínio**, clique em **Editar** e, em seguida, clique em **Acesso Concedido**.
  
#### Copyright
  
Este documento serve de suporte à versão preliminar de um produto de software que poderá sofrer alterações substanciais antes da versão comercial final e contém informações confidenciais de propriedade da Microsoft Corporation. É divulgado ao abrigo do contrato de não divulgação celebrado entre o destinatário e a Microsoft. Este documento é fornecido apenas para fins informativos e a Microsoft não concede, neste documento, nenhuma garantia, expressa ou implícita. As informações contidas neste documento, incluindo URLs e outras referências a Web sites, estão sujeitas a alterações sem aviso prévio. É da responsabilidade do utilizador todo e qualquer risco decorrente da utilização deste documento. Os nomes de empresas, organizações, produtos, nomes de domínio, endereços de correio electrónico, logótipos, pessoas, locais e eventos mencionados neste documento são fictícios e não se destinam, de todo, a representar qualquer empresa, organização, produto, nome de domínio, endereço de correio electrónico, logótipo, pessoa, local ou evento real, salvo indicação em contrário. É da responsabilidade do utilizador agir em conformidade com todas as leis de direito de autor aplicáveis. Sem limitação para os direitos de autor, nenhuma parte deste documento pode ser reproduzida, armazenada ou introduzida num sistema de recuperação, ou transmitida sob qualquer forma ou por qualquer meio (electrónico, mecânico, fotocópia, gravação ou outro), para qualquer fim, sem a permissão expressa, por escrito, da Microsoft Corporation.
  
Neste documento, podem ser feitas referências a patentes ou a pedidos de patentes pendentes, marcas comerciais, direitos de autor ou outros direitos de propriedade intelectual da Microsoft. Salvo disposição expressa em qualquer contrato de licença escrito da Microsoft, o facto de este documento lhe ser fornecido não lhe concede quaisquer direitos sobre essas patentes, marcas comerciais, direitos de autor ou outro tipo de propriedade intelectual.
  
© 2007 Microsoft Corporation. Todos os direitos reservados.
  
Microsoft, SQL Server, Windows e Windows Server são marcas registadas ou comerciais da Microsoft Corporation nos Estados Unidos e/ou noutros países.
  
Todas as restantes marcas comerciais são propriedade dos respectivos proprietários.
