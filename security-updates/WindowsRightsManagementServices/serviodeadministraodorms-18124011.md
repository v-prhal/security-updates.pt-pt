---
TOCTitle: Serviço de Administração do RMS
Title: Serviço de Administração do RMS
ms:assetid: '4bd3e142-f0f6-40e9-a160-deab28ce5b88'
ms:contentKeyID: 18124011
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc747560(v=WS.10)'
---

Serviço de Administração do RMS
===============================

O serviço de administração é executado no cluster de raiz do RMS, bem como em quaisquer clusters de licenciamento. O serviço de administração aloja o Web site Administração e permite-lhe administrar o RMS.

O ficheiro de aplicação do serviço de administração Default.aspx está localizado no directório virtual Admin em *Web site do RMS*\\\_wmcs\\Admin. Em que *Web site do RMS* é substituído pelo nome do Web site onde o RMS foi aprovisionado.

A lista de controlo de acessos predefinida neste serviço é apresentada na tabela seguinte:

###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Utilizador ou Grupo</th>
<th>Permissão predefinida</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Administradores</td>
<td style="border:1px solid black;">Controlo total</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Grupo de Serviços do RMS</td>
<td style="border:1px solid black;">Ler e executar</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">SISTEMA</td>
<td style="border:1px solid black;">Controlo total</td>
</tr>
</tbody>
</table>
