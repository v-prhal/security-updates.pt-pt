---
TOCTitle: Serviço de Servidor do RMS
Title: Serviço de Servidor do RMS
ms:assetid: '772d0a89-c9fb-4430-9434-38cd5add1e86'
ms:contentKeyID: 18124052
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc747566(v=WS.10)'
---

Serviço de Servidor do RMS
==========================

O serviço de Servidor só é executado no cluster de raiz do RMS. O serviço de Servidor expõe um pedido efectuado por um cliente, utilizando a publicação online para obter um certificado de licenciador de servidores.

O ficheiro da aplicação do serviço de servidor, Server.asmx, encontra-se no directório virtual Certification que está no IIS.

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
