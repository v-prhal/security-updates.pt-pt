---
TOCTitle: Serviço de Localização de Serviços do RMS
Title: Serviço de Localização de Serviços do RMS
ms:assetid: '6f410cc9-5d5b-4df3-bf4f-7b13811eb52f'
ms:contentKeyID: 18124036
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc747548(v=WS.10)'
---

Serviço de Localização de Serviços do RMS
=========================================

O serviço de Localização de Serviços é executado nos servidores de raiz e licenciamento do RMS. O serviço de Localização de Serviços fornece o URL da ligação de serviço do cluster do Active Directory para permitir a identificação pelos clientes activados pelo RMS.

O ficheiro da aplicação do serviço de localização de serviços, ServiceLocator.asmx, encontra-se nos directórios virtuais Certification e Licensing que estão no IIS.

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
<tr class="even">
<td style="border:1px solid black;">Utilizadores</td>
<td style="border:1px solid black;">Ler e executar</td>
</tr>
</tbody>
</table>
