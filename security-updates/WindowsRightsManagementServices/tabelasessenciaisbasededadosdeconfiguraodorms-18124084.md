---
TOCTitle: Tabelas Essenciais à Base de dados de Configuração do RMS
Title: Tabelas Essenciais à Base de dados de Configuração do RMS
ms:assetid: '8f9e15a2-92bc-41f7-a4fd-329567afb142'
ms:contentKeyID: 18124084
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc747676(v=WS.10)'
---

Tabelas Essenciais à Base de dados de Configuração do RMS
=========================================================

Este tópico descreve as tabelas essenciais da base de dados de configuração do RMS.

DRMS\_ApplicationExclusionList
------------------------------

A tabela seguinte lista as informações sobre as aplicações excluídas.

###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Tipo de Dados</th>
<th>NULLs</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">ID</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">IDENTITY(100,1) Não NULL</td>
<td style="border:1px solid black;">Índice interno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Nome</td>
<td style="border:1px solid black;">nvarchar(256)</td>
<td style="border:1px solid black;">Não NULL</td>
<td style="border:1px solid black;">Nome da aplicação</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">VersionMinMajor</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Número da versão superior mínima da aplicação</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">VersionMinMinor</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Número da versão inferior mínima da aplicação</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">VersionMinBuild</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Número da versão de compilação mínima da aplicação</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">VersionMinRevision</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Número da versão de revisão mínima da aplicação</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">VersionMaxMajor</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Número da versão superior máxima da aplicação</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">VersionMaxMinor</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Número da versão inferior máxima da aplicação</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">VersionMaxBuild</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Número da versão de compilação máxima da aplicação</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">VersionMaxRevision</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Número da versão de revisão máxima da aplicação</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Descrição</td>
<td style="border:1px solid black;">nvarchar(256)</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Descrição da aplicação</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">dt_DateUpdated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Actualizar carimbo de data/hora</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">dt_DateCreated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Criação do carimbo de data/hora</td>
</tr>
</tbody>
</table>
  
DRMS\_AsynchronousQueue  
-----------------------
  
A tabela seguinte mostra as informações relativas à fila de mensagens.
  
###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Tipo de Dados</th>
<th>NULLs</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">AsyncQueueID</td>
<td style="border:1px solid black;">Int (PK)</td>
<td style="border:1px solid black;">IDENTITY (100,1) Não NULL</td>
<td style="border:1px solid black;">Índice interno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">QueueName</td>
<td style="border:1px solid black;">nvarchar(256)</td>
<td style="border:1px solid black;">Não NULL</td>
<td style="border:1px solid black;">Caminho para a fila de mensagens</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DateUpdated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Actualizar carimbo de data/hora</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DateCreated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Criação do carimbo de data/hora</td>
</tr>
</tbody>
</table>
  
DRMS\_CaType  
------------
  
A tabela seguinte lista informações sobre o tipo de certificado emitido para o cliente.
  
###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Tipo de Dados</th>
<th>NULLs</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">ID</td>
<td style="border:1px solid black;">Int (PK)</td>
<td style="border:1px solid black;">Não NULL</td>
<td style="border:1px solid black;">A ID do certificado</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">TypeName</td>
<td style="border:1px solid black;">nvarchar(256)</td>
<td style="border:1px solid black;">Não NULL</td>
<td style="border:1px solid black;">Desktop, MobileDevice ou Server</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DateUpdated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Actualizar carimbo de data/hora</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DateCreated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Criação do carimbo de data/hora</td>
</tr>
</tbody>
</table>
  
DRMS\_ClusterConfiguration  
--------------------------
  
A tabela seguinte lista as informações sobre o certificado de licenciador de servidores actual que se encontra na tabela DRMS\_LicensorCertificate.
  
###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Tipo de Dados</th>
<th>NULLs</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">CurrentLicensorCertID</td>
<td style="border:1px solid black;">int (FK)</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">O certificado de licenciador activo</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DateUpdated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Actualizar carimbo de data/hora</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DateCreated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Criação do carimbo de data/hora</td>
</tr>
</tbody>
</table>
  
DRMS\_ClusterPolicies  
---------------------
  
A tabela seguinte lista as informações sobre as localizações onde se encontram armazenadas as políticas dos clusters.
  
###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Tipo de Dados</th>
<th>NULLs</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">PolicyID</td>
<td style="border:1px solid black;">Int (PK)</td>
<td style="border:1px solid black;">IDENTITY(100,1) Não NULL</td>
<td style="border:1px solid black;">ID da política</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">PolicyName</td>
<td style="border:1px solid black;">nvarchar(64)</td>
<td style="border:1px solid black;">Não NULL</td>
<td style="border:1px solid black;">Nome da política</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">PolicyData</td>
<td style="border:1px solid black;">sql_variant</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Dados da política</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DateUpdated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Actualizar carimbo de data/hora</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DateCreated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Criação do carimbo de data/hora</td>
</tr>
</tbody>
</table>
  
DRMS\_ClusterServer  
-------------------
  
A tabela seguinte lista as informações sobre os servidores que fazem parte do cluster.
  
###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Tipo de Dados</th>
<th>NULLs</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">ServerID</td>
<td style="border:1px solid black;">Int (PK)</td>
<td style="border:1px solid black;">IDENTITY(100,1) Não NULL</td>
<td style="border:1px solid black;">ID do servidor</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">ServerName</td>
<td style="border:1px solid black;">nvarchar(256)</td>
<td style="border:1px solid black;">Não especificado</td>
<td style="border:1px solid black;">Nome do computador para o servidor</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DateUpdated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Actualizar carimbo de data/hora</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DateCreated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Criação do carimbo de data/hora</td>
</tr>
</tbody>
</table>
  
DRMS\_GICExclusionList  
----------------------
  
A tabela lista as informações sobre os certificados de contas de direitos excluídos.
  
###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Tipo de Dados</th>
<th>NULLs</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">PublicKeyIndex</td>
<td style="border:1px solid black;">Int (PK)</td>
<td style="border:1px solid black;">IDENTITY(100,1) Não NULL</td>
<td style="border:1px solid black;">Índice interno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">PublicKey</td>
<td style="border:1px solid black;">PublicKey</td>
<td style="border:1px solid black;">Não NULL</td>
<td style="border:1px solid black;">Bytes da chave pública</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">UserID</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Índice da ID de utilizador</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">ExpirationDate</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Data em que o certificado de conta de direitos expira</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Descrição</td>
<td style="border:1px solid black;">nvarchar(256)</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">NOME associado a esta chave do certificado de conta de direitos excluído</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">dt_DateUpdated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">Não NULL</td>
<td style="border:1px solid black;">Actualizar carimbo de data/hora</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">dt_DateCreated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">Não NULL</td>
<td style="border:1px solid black;">Criação do carimbo de data/hora</td>
</tr>
</tbody>
</table>
  
DRMS\_LicensorCertificate  
-------------------------
  
A tabela seguinte lista as informações sobre o certificado do licenciador de servidores activo.
  
###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Tipo de Dados</th>
<th>NULLs</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">i_CertID</td>
<td style="border:1px solid black;">Int (PK)</td>
<td style="border:1px solid black;">IDENTITY(100,1) Não NULL</td>
<td style="border:1px solid black;">ID da política</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">s_CertGUIDType</td>
<td style="border:1px solid black;">nvarchar(64)</td>
<td style="border:1px solid black;">Não NULL</td>
<td style="border:1px solid black;">Tipo da ID do par de chaves</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">s_CertGUID</td>
<td style="border:1px solid black;">nvarchar(128)</td>
<td style="border:1px solid black;">Não NULL</td>
<td style="border:1px solid black;">GUID da ID do par de chaves</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">i_CertificateID</td>
<td style="border:1px solid black;">int (FK)</td>
<td style="border:1px solid black;">Não NULL</td>
<td style="border:1px solid black;">Ponteiro para o certificado real</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">dt_DateUpdated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Actualizar carimbo de data/hora</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">dt_DateCreated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Criação do carimbo de data/hora</td>
</tr>
</tbody>
</table>
  
DRMS\_LicensorPrivateKey  
------------------------
  
A tabela seguinte lista as informações sobre a chave privada do certificado do licenciador de servidores activo.
  
###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Tipo de Dados</th>
<th>NULLs</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">PrivateKeyID</td>
<td style="border:1px solid black;">Int (PK)</td>
<td style="border:1px solid black;">IDENTITY (100,1) Não NULL</td>
<td style="border:1px solid black;">Índice interno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">CertGUIDType</td>
<td style="border:1px solid black;">nvarchar(64)</td>
<td style="border:1px solid black;">Não NULL</td>
<td style="border:1px solid black;">Tipo da ID do par de chaves</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">CertGUID</td>
<td style="border:1px solid black;">nvarchar(128)</td>
<td style="border:1px solid black;">Não NULL</td>
<td style="border:1px solid black;">GUID da ID do par de chaves</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">PrivateKey</td>
<td style="border:1px solid black;">varbinary(2048)</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Representação binária da chave</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">CSP</td>
<td style="border:1px solid black;">nvarchar(512)</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Nome do fornecedor do serviço criptográfico (CSP)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">CSPType</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Tipo do CSP</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">KeyContainerName</td>
<td style="border:1px solid black;">nvarchar(512)</td>
<td style="border:1px solid black;">Não especificado</td>
<td style="border:1px solid black;">Nome do contentor da chave</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">KeyNumber</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Número da chave</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DateUpdated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Actualizar carimbo de data/hora</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DateCreated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Criação do carimbo de data/hora</td>
</tr>
</tbody>
</table>
  
DRMS\_PassportDenyList  
----------------------
  
A tabela seguinte lista as informações sobre as contas do Microsoft® .NET Passport cujas licenças vão ser recusadas.
  
###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Tipo de Dados</th>
<th>NULLs</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">DenyID</td>
<td style="border:1px solid black;">Int (PK)</td>
<td style="border:1px solid black;">IDENTITY(100,1) Não NULL</td>
<td style="border:1px solid black;">Índice interno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DenyAddressPattern</td>
<td style="border:1px solid black;">nvarchar(500)</td>
<td style="border:1px solid black;">Não NULL</td>
<td style="border:1px solid black;">Nome de utilizador e de domínio</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DateUpdated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Actualizar carimbo de data/hora</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DateCreated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Criação do carimbo de data/hora</td>
</tr>
</tbody>
</table>
  
DRMS\_Plugin  
------------
  
A tabela seguinte mostra as informações relativas aos plug-ins.
  
###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Tipo de Dados</th>
<th>NULLs</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">PluginID</td>
<td style="border:1px solid black;">Int</td>
<td style="border:1px solid black;">IDENTITY(100,1) Não NULL</td>
<td style="border:1px solid black;">Índice interno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">PluginTypeID</td>
<td style="border:1px solid black;">int (FK)</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Tipo de plug-in</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">NameSpace</td>
<td style="border:1px solid black;">nvarchar(128)</td>
<td style="border:1px solid black;">Não NULL</td>
<td style="border:1px solid black;">Espaço de nome para este plug-in</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">PluginName</td>
<td style="border:1px solid black;">nvarchar(128)</td>
<td style="border:1px solid black;">Não NULL</td>
<td style="border:1px solid black;">Nome deste plug-in</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Ordinal</td>
<td style="border:1px solid black;">Int</td>
<td style="border:1px solid black;">Não NULL</td>
<td style="border:1px solid black;">Número da sequência em que o plug-in é executado</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Path</td>
<td style="border:1px solid black;">nvarchar(512)</td>
<td style="border:1px solid black;">Não NULL</td>
<td style="border:1px solid black;">Caminho para o ficheiro DLL</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">ObjectTypeName</td>
<td style="border:1px solid black;">nvarchar(50)</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Não utilizado</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DebugMode</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Especifica se o plug-in deve ser executado em modo de depuração</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">PublicKey</td>
<td style="border:1px solid black;">PublicKey</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Chave pública do plug-in</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Versão</td>
<td style="border:1px solid black;">nvarchar(64)</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Versão do plug-in</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DateUpdated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Actualizar carimbo de data/hora</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DateCreated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Criação do carimbo de data/hora</td>
</tr>
</tbody>
</table>
  
DRMS\_AllowedPluginVersions  
---------------------------
  
A tabela seguinte lista as informações sobre as versões do plug-in que podem participar no sistema do RMS.
  
###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Tipo de Dados</th>
<th>NULLs</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">RowID</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">Não NULL</td>
<td style="border:1px solid black;">Índice interno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">PluginID</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">IDENTITY(100,1) Não NULL</td>
<td style="border:1px solid black;">Índice interno</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">VersionInfo</td>
<td style="border:1px solid black;">nvarchar(64)</td>
<td style="border:1px solid black;">Não especificado</td>
<td style="border:1px solid black;">Versão do plug-in</td>
</tr>
</tbody>
</table>
  
DRMS\_PluginProperties  
----------------------
  
A tabela seguinte lista as informações sobre as propriedades do plug-in.
  
###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Tipo de Dados</th>
<th>NULLs</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">PropertyID</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">IDENTITY(100,1) Não NULL</td>
<td style="border:1px solid black;">Índice interno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">PluginID</td>
<td style="border:1px solid black;">int (FK)</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">ID do plug-in ao qual pertence a propriedade</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">PropertyName</td>
<td style="border:1px solid black;">nvarchar(256)</td>
<td style="border:1px solid black;">Não NULL</td>
<td style="border:1px solid black;">O nome da propriedade para estes dados da configuração</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">PropertyValue</td>
<td style="border:1px solid black;">texto</td>
<td style="border:1px solid black;">Não NULL</td>
<td style="border:1px solid black;">O valor da propriedade para estes dados da configuração</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DateUpdated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Actualizar carimbo de data/hora</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DateCreated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Criação do carimbo de data/hora</td>
</tr>
</tbody>
</table>
  
DRMS\_PluginType  
----------------
  
A tabela seguinte lista as informações sobre o tipo de plug-in.
  
###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Tipo de Dados</th>
<th>NULLs</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">PluginTypeID</td>
<td style="border:1px solid black;">Int (PK)</td>
<td style="border:1px solid black;">Não NULL</td>
<td style="border:1px solid black;">Índice interno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">PluginTypeName</td>
<td style="border:1px solid black;">nvarchar(256)</td>
<td style="border:1px solid black;">Não NULL</td>
<td style="border:1px solid black;">Nome deste plug-in</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DateUpdated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Actualizar carimbo de data/hora</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DateCreated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Criação do carimbo de data/hora</td>
</tr>
</tbody>
</table>
  
DRMS\_RightsTemplate  
--------------------
  
A tabela seguinte lista as informações sobre os modelos da política de direitos.
  
###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Tipo de Dados</th>
<th>NULLs</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Guid</td>
<td style="border:1px solid black;">nvarchar(128) (PK)</td>
<td style="border:1px solid black;">Não NULL</td>
<td style="border:1px solid black;">GUID do modelo da política de direitos</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">TemplateData</td>
<td style="border:1px solid black;">ntext</td>
<td style="border:1px solid black;">Não NULL</td>
<td style="border:1px solid black;">Este campo contém os dados do modelo XrML.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DateUpdated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Actualizar carimbo de data/hora</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DateCreated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Criação do carimbo de data/hora</td>
</tr>
</tbody>
</table>
  
DRMS\_TrustedCertificateAuthorities  
-----------------------------------
  
A tabela seguinte lista as informações sobre as autoridades de certificação fidedigna.
  
###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Tipo de Dados</th>
<th>NULLs</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">ID</td>
<td style="border:1px solid black;">Int (PK)</td>
<td style="border:1px solid black;">IDENTITY(1,1) Não NULL</td>
<td style="border:1px solid black;">Índice interno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">CertificateID</td>
<td style="border:1px solid black;">int (FK)</td>
<td style="border:1px solid black;">Não NULL</td>
<td style="border:1px solid black;">ID do certificado</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">CertificateGUID</td>
<td style="border:1px solid black;">nvarchar(128)</td>
<td style="border:1px solid black;">Não NULL</td>
<td style="border:1px solid black;">GUID do certificado</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">CaTypeID</td>
<td style="border:1px solid black;">int (FK)</td>
<td style="border:1px solid black;">Não NULL</td>
<td style="border:1px solid black;">Tipo de autoridade de certificação</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DateUpdated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Actualizar carimbo de data/hora</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DateCreated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Criação do carimbo de data/hora</td>
</tr>
</tbody>
</table>
  
DRMs\_TrustedEmailDomains  
-------------------------
  
A tabela seguinte lista as informações sobre os domínios de correio electrónico que são fidedignos no ambiente do RMS
  
###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Tipo de Dados</th>
<th>NULLs</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">ID</td>
<td style="border:1px solid black;">int (PK)</td>
<td style="border:1px solid black;">IDENTITY(100,1) Não NULL</td>
<td style="border:1px solid black;">Índice interno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">i_TrustedIdentityDomainID</td>
<td style="border:1px solid black;">int (FK)t</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Índice interno</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">s_EmailDomainName</td>
<td style="border:1px solid black;">nvarchar(256)</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Lista de nomes do domínio de correio electrónico que são válidos para o domínio de utilizador fidedigno</td>
</tr>
</tbody>
</table>
  
DRMS\_TrustedIdentityDomain  
---------------------------
  
A tabela seguinte lista as informações sobre os domínios de utilizadores e os domínios de publicação fidedignos.
  
###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Tipo de Dados</th>
<th>NULLs</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">i_TrustedIdentityDomainID</td>
<td style="border:1px solid black;">Int (PK)</td>
<td style="border:1px solid black;">IDENTITY(100,1) Não NULL</td>
<td style="border:1px solid black;">Índice interno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">s_DomainType</td>
<td style="border:1px solid black;">nvarchar(64)</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Tipo de domínio</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">CertGUIDType</td>
<td style="border:1px solid black;">nvarchar(64)</td>
<td style="border:1px solid black;">Não NULL</td>
<td style="border:1px solid black;">Tipo do GUID do certificado</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">CertGUID</td>
<td style="border:1px solid black;">nvarchar(128)</td>
<td style="border:1px solid black;">Não NULL</td>
<td style="border:1px solid black;">GUID do certificado</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">i_CertificateID</td>
<td style="border:1px solid black;">int (FK)</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">ID do certificado</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">i_allowsID</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">Não NULL</td>
<td style="border:1px solid black;">SID do domínio</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">s_friendlyname</td>
<td style="border:1px solid black;">nvarchar(255)</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Nome simples do certificado</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">dt_DateUpdated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Actualizar carimbo de data/hora</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">dt_DateCreated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Criação do carimbo de data/hora</td>
</tr>
</tbody>
</table>
  
DRMS\_XrML\_Certificate  
-----------------------
  
A tabela seguinte lista as informações sobre os certificados de licenciadores de servidores XrML que são referenciados na tabela DRMS\_LicensorCertificate. Também mapeia a cadeia de certificados.
  
###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Tipo de Dados</th>
<th>NULLs</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">i_CertificateID</td>
<td style="border:1px solid black;">Int (PK)</td>
<td style="border:1px solid black;">IDENTITY(100,1) Não NULL</td>
<td style="border:1px solid black;">Ponteiro para o certificado real</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">s_Certificate</td>
<td style="border:1px solid black;">ntext</td>
<td style="border:1px solid black;">Não NULL</td>
<td style="border:1px solid black;">Ponteiro para o certificado real</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">i_ParentCertificateID</td>
<td style="border:1px solid black;">int (FK)</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Ponteiro para o certificado real</td>
</tr>
</tbody>
</table>
