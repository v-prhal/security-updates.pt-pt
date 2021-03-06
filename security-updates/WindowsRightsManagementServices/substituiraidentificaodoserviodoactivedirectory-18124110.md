---
TOCTitle: Substituir a Identificação do Serviço do Active Directory
Title: Substituir a Identificação do Serviço do Active Directory
ms:assetid: '9d97e7fb-5b05-4853-ad7b-6cc82b9729f0'
ms:contentKeyID: 18124110
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc747614(v=WS.10)'
---

Substituir a Identificação do Serviço do Active Directory
=========================================================

Os serviços e clientes do RMS detectam as localizações de serviços procurando primeiramente no registo local. Se determinadas chaves no registo não possuírem um valor, os serviços e clientes do RMS procuram o ponto de ligação do serviço (SCP) no Active Directory. Isto significa que é possível substituir a definição de detecção do Active Directory predefinida se introduzir determinadas chaves no servidor ou no registo do cliente.

| ![](images/Cc747614.note(WS.10).gif)Nota                                                                                                                                    |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Se o cluster de raiz do RMS estiver configurado de forma a que o SCP não seja publicado no Active Directory, pode utilizar estas chaves para direccionar os clientes do RMS para a localização correcta. |

Esta secção descreve as entradas de registo e fornece detalhes sobre como as criar.

Substituir a Detecção de Serviços para Subinscrição de Cluster apenas de Licenciamento
--------------------------------------------------------------------------------------

Se estiver a aprovisionar um cluster apenas de licenciamento e pretender que este seja subinscrito num cluster de raiz diferente do cluster de raiz implementado na floresta do Active Directory do cluster apenas de licenciamento, será necessário substituir a detecção dos serviços de subinscrição e de certificação de contas.

#### Descrições de entradas de registo

As seguintes entradas de registo são utilizadas para substituir os serviços de subinscrição e certificação de contas.

-   **SubEnrollmentURL**. Esta entrada especifica o caminho para o cluster de raiz que o servidor de licenciamento utiliza ao solicitar o respectivo certificado de servidor licenciador.
-   **GicURL**. Esta entrada especifica o caminho para o serviço de certificação de contas para este cluster apenas de licenciamento.

#### Detalhes da entrada

Em computadores a executar a versão de 32 bits do Windows Server 2003, o caminho completo da subchave de registo para as entradas de detecção de serviços para subinscrição de cluster apenas de licenciamento é:

**HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\DRMS\\1.0**

Em computadores a executar a versão de 64 bits do Windows Server 2003, o caminho completo da subchave de registo para as entradas de detecção de serviços para subinscrição de cluster apenas de licenciamento é:

**HKEY\_LOCAL\_MACHINE\\SoftwareWOW6432Node\\Microsoft\\DRMS\\1.0**

A tabela seguinte lista as entradas que pode adicionar para substituir a detecção de serviços.

###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Tipo</th>
<th>Valor</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">SubEnrollmentURL</td>
<td style="border:1px solid black;">Cadeia</td>
<td style="border:1px solid black;">http(ou https)://<em>nome_servidor</em>/_wmcs/certification/subenrollservice.asmx</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">GicURL</td>
<td style="border:1px solid black;">Cadeia</td>
<td style="border:1px solid black;">http(ou https)://<em>nome_servidor</em>/_wmcs/certification/certification.asmx</td>
</tr>
</tbody>
</table>
  
Substituir a Detecção de Serviços do Lado do Cliente para Publicação  
--------------------------------------------------------------------
  
Se os utilizadores vão publicar conteúdo dos seus computadores, poderá querer substituir as localizações dos servidores utilizados para publicação consoante a topologia utilizada na empresa. As localizações dos servidores utilizados para publicação são normalmente detectadas pelo cliente utilizando o Active Directory. Ao adicionar as chaves de registo adequadas nos computadores clientes, os clientes irão contornar esses métodos e, em alternativa, utilizar os URLs especificados no valor de entrada de registo.
  
| ![](images/Cc747614.note(WS.10).gif)Nota                                                                                                                                |  
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
| As substituições de cliente listadas nestas secções devem ser criadas como chaves e não como entradas individuais. O valor para estas chaves deve ser criado na entrada predefinida para cada chave. |
  
#### Descrições de chaves de registo
  
As seguintes chaves de registo podem ser utilizadas para substituir a detecção automática do cluster do RMS.
  
-   **Activation**. Esta chave de registo define o URL do serviço de activação da máquina. Se estiver a executar o cliente do RMS com Service Pack 1 ou posterior, esta entrada de registo deixa de ser utilizada.  
-   **EnterprisePublishing**. Esta chave de registo define o URL de uma instalação do RMS que pretende que este cliente utilize para pedidos de licença.  
-   **CloudPublishing**. Esta chave de registo define o URL do serviço de licenciamento alojado pela Microsoft que pode ser utilizado se o cliente não tiver acesso a uma instalação do RMS mas tiver acesso à Internet.
  
#### Detalhes da chave
  
O caminho completo da subchave de registo para entradas de detecção de serviços do lado do cliente para publicação é:
  
**HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\MSDRM\\ServiceLocation\\**
  
A tabela seguinte lista as chaves de registo que podem ser adicionadas num computador cliente do RMS para substituir a detecção de serviços.
  
###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Tipo</th>
<th>Valor</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Activation</td>
<td style="border:1px solid black;">Cadeia</td>
<td style="border:1px solid black;">http(ou https)://<em>nome_cluster_RMS</em>/_wmcs/Certification em que <em>nome_cluster_RMS</em> é o nome do cluster do RMS.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">EnterprisePublishing</td>
<td style="border:1px solid black;">Cadeia</td>
<td style="border:1px solid black;">http(ou https)://<em>nome_cluster_RMS</em>/_wmcs/Licensing em que <em>nome_cluster_RMS</em> é o nome do cluster do RMS.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">CloudPublishing</td>
<td style="border:1px solid black;">Cadeia</td>
<td style="border:1px solid black;">http(ou https)://<em>nome_cluster_FQDN</em>/_wmcs/Licensing em que <em>nome_cluster_FQDN</em> é o nome de domínio completamente qualificado do cluster do RMS.</td>
</tr>
</tbody>
</table>
  
Recomenda-se que implemente estas chaves de registo utilizando o Systems Management Server ou a Política de Grupo para se certificar de que todos os clientes na empresa utilizam os servidores de publicação correctos.
  
| ![](images/Cc747614.Caution(WS.10).gif)Atenção                                                                                                             |  
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
| A edição incorrecta do registo poderá danificar gravemente o sistema. Antes de efectuar alterações no registo, crie uma cópia de segurança de todos os dados importantes do computador. |
  
Pode ser utilizado um ficheiro de registo (.reg) exemplificativo para importar as chaves de registo adequadas em cada servidor no cluster do RMS.
  
**Para importar as chaves de registo adequadas em cada servidor no cluster do RMS**  
1.  Copie o seguinte ficheiro de registo exemplificativo para o Bloco de Notas.
  
    `Windows Registry Editor Version 5.00`
  
    `[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSDRM\ServiceLocation]`
  
    `[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSDRM\ServiceLocation\Activation]`
  
    `@="http://<RMS_cluster_name>/_wmcs/certification"`
  
    `[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSDRM\ServiceLocation\EnterprisePublishing]`
  
    `@="http://<RMS_cluster_name>/_wmcs/licensing"`
  
2.  Substitua &lt;nome\_cluster\_RMS&gt; pelo nome do seu cluster do RMS.
  
3.  Guarde o ficheiro com a extensão de nome de ficheiro .reg.
  
4.  Faça duplo clique no nome do ficheiro no Explorador do Windows.
  
5.  Se aparecer a caixa de diálogo de **Controlo de contas de utilizador**, confirme se a acção apresentada é a que pretende e depois clique em **Continuar**.. Quando for apresentada uma mensagem a perguntar se pretende adicionar a informação ao registo, clique em **Sim**.
