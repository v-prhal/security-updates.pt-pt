---
TOCTitle: 'Serviço de Pré-inscrição do RMS'
Title: 'Serviço de Pré-inscrição do RMS'
ms:assetid: '6b05e71c-5e7d-467c-9e13-35ac14d3718a'
ms:contentKeyID: 18124016
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc720289(v=WS.10)'
---

Serviço de Pré-inscrição do RMS
===============================

O serviço de pré-inscrição apenas é executado no cluster de raiz do RMS. Responde a pedidos de certificados de licenciadores de servidores, submetidos durante o aprovisionamento por servidores dos clusters de licenciamento.

O ficheiro de aplicação do serviço de pré-inscrição SubEnrollService.asmx está localizado no directório virtual Certification em *Web\_Site\_RMS*\\\_wmcs\\Certification\\, em que *Web\_Site\_RMS* é substituído pelo nome do Web site de aprovisionamento do RMS.

Por predefinição, o acesso a este serviço está restrito à conta SISTEMA local. Para aprovisionar e inscrever um servidor subordinado num cluster de licenciamento, a conta de utilizador do administrador do servidor de licenciamento deve ser adicionada à lista de controlo de acesso discricionário (DACL) SubEnrollService.asmx, com privilégios de controlo total.

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
<td style="border:1px solid black;">SISTEMA</td>
<td style="border:1px solid black;">Controlo total</td>
</tr>
</tbody>
</table>
