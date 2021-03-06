---
TOCTitle: Migrar de uma Implementação Piloto do RMS para uma Implementação de Produção
Title: Migrar de uma Implementação Piloto do RMS para uma Implementação de Produção
ms:assetid: 'ea151946-22fb-4cba-a3ef-fd7a4bf0d292'
ms:contentKeyID: 18124213
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc747789(v=WS.10)'
---

Migrar de uma Implementação Piloto do RMS para uma Implementação de Produção
============================================================================

Diversas organizações optam por implementar o RMS numa implementação piloto antes de implementarem a tecnologia na organização. Normalmente, o programa piloto tem um número limitado de utilizadores e o servidor pode ser mantido localmente por um administrador dedicado em vez de fazer parte de um centro de dados mantido por um grupo de TI. Quando a organização implementa o RMS no centro de dados para todos os clientes após a conclusão da implementação piloto, os novos servidores do RMS são implementados para suportarem um número maior de possíveis utilizadores.

No entanto, o conteúdo protegido pelo RMS está associado ao servidor do RMS utilizado na respectiva criação. Assim, se um servidor for removido ou substituído, será necessário aplicar as acções necessárias que permitam aos servidores de produção do RMS desencriptar e licenciar o conteúdo encriptado através dos servidores piloto do RMS.

Se tiver implementado o RMS como um programa piloto e pretender mover o servidor do RMS para o ambiente de produção da organização e, em simultâneo, manter a integridade do conteúdo protegido pelo servidor piloto do RMS, deve criar um plano de migração que assegure uma transição sem problemas e contemple a capacidade de reverter para o programa piloto se for necessário recuperar dados.

Os passos a seguir são apenas um exemplo do alguns dos itens que o plano de migração deve incluir. Cada implementação pode ter requisitos adicionais.

###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Servidor</th>
<th>Passo</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Piloto</td>
<td style="border:1px solid black;">Efectue uma cópia de segurança da base de dados de configuração do RMS.</td>
<td style="border:1px solid black;">Se for necessário, isto permite restaurar o servidor piloto.
A base de dados de configuração inclui a chave privada do RMS.
Certifique-se de que conhece a palavra-passe da chave privada.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Piloto</td>
<td style="border:1px solid black;">Se utilizou um Módulo de Segurança por Hardware (HSM) para proteger a chave privada do RMS, efectue uma cópia de segurança da configuração do HSM de acordo com as instruções do fabricante.</td>
<td style="border:1px solid black;">O HSM será restaurado no novo servidor.
Certifique-se de que tem todos os componentes necessários para instalar e configurar o HSM disponível.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Piloto</td>
<td style="border:1px solid black;">Exporte o ficheiro do Domínio de Publicação Fidedigno.</td>
<td style="border:1px solid black;">Assim, outro servidor do RMS poderá desencriptar as licenças de publicação criadas por este servidor e emitir licenças de utilização para o conteúdo protegido.
O domínio de publicação fidedigno inclui o certificado de licenciador de servidores, a chave privada do RMS e quaisquer modelos de política de direitos estabelecidos por este servidor.
O ficheiro do domínio de publicação fidedigno é um ficheiro XML encriptado por uma palavra-passe segura especificada quando o ficheiro foi criado. Esta palavra-passe também é necessária para a importação do ficheiro do domínio de publicação fidedigno.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Piloto</td>
<td style="border:1px solid black;">Exporte o Domínio de Utilizador Fidedigno.</td>
<td style="border:1px solid black;">Isto permite a outro servidor do RMS conceder licenças a utilizadores cujos certificados de contas de direitos (RAC) foram concedidos pelo servidor piloto do RMS.
O domínio de utilizador fidedigno é estabelecido através da importação do certificado de licenciador de servidores deste servidor para o outro servidor do RMS.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Produção</td>
<td style="border:1px solid black;">Prepare o novo servidor para se tornar no servidor de certificação de raiz.</td>
<td style="border:1px solid black;">Certifique-se de que acede ao servidor de bases de dados e de que os Serviços de Informação Internet (IIS) e a Colocação de Mensagens em Fila estão instalados.
Se for possível, utilize o mesmo nome para este servidor.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Produção</td>
<td style="border:1px solid black;">Se utilizar um HSM, instale-o e restaure a configuração a partir da cópia de segurança criada no servidor piloto.</td>
<td style="border:1px solid black;">Estabelece as credenciais necessárias à desencriptação da chave privada do RMS.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Produção</td>
<td style="border:1px solid black;">Instale o RMS.</td>
<td style="border:1px solid black;">O RMS verifica se todos os serviços de pré-requisitos estão instalados e configurados correctamente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Produção</td>
<td style="border:1px solid black;">Aprovisione o RMS utilizando uma chave privada nova. Se estiver a utilizar a inscrição online, o servidor é inscrito durante o processo de aprovisionamento utilizando a Internet para estabelecer ligação ao Serviço de Inscrição da Microsoft. Se não existir uma ligação à Internet para este servidor, tem de utilizar a inscrição offline.</td>
<td style="border:1px solid black;">Se o nome deste servidor for diferente do nome do servidor piloto, pode modificar a definição de URL do cluster para o URL do servidor piloto.
Caso contrário, terá de configurar um redireccionamento do URL de cluster anterior para o URL de cluster novo para que os utilizadores com conteúdo pré-existente obtenham as licenças de utilização.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Produção</td>
<td style="border:1px solid black;">Se estiver a utilizar a inscrição offline, conclua o processo de inscrição manual para o novo servidor do RMS. Para mais informações, consulte “Para Inscrever Manualmente um Servidor de Certificação de Raiz” em “Utilizar um Servidor do RMS” nesta colecção de documentação.</td>
<td style="border:1px solid black;">O servidor do RMS só pode ser utilizado depois de ter sido inscrito.
As páginas de administração do RMS também só podem ser acedidas depois de o servidor ter sido inscrito.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Produção</td>
<td style="border:1px solid black;">Importe o ficheiro do domínio de publicação fidedigno exportado no passo 3.</td>
<td style="border:1px solid black;">A conta de serviço do RMS tem de ter permissões de leitura para a localização de armazenamento do ficheiro para que este seja importado com êxito.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Produção</td>
<td style="border:1px solid black;">Volte a assinar cada modelo importado com o domínio de publicação fidedigno.</td>
<td style="border:1px solid black;">Os modelos são assinados com a chave privada do servidor. Como este servidor tem uma chave privada nova, os modelos têm de ser assinados novamente para serem válidos. Para mais informações, consulte “Para Voltar a Assinar um Modelo de Política de Direitos” em “Utilizar um Servidor do RMS” nesta colecção de documentação.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Produção</td>
<td style="border:1px solid black;">Redistribua os modelos para os computadores clientes que participaram na implementação piloto.</td>
<td style="border:1px solid black;">Os modelos antigos necessitam de ser removidos e substituídos pelos modelos assinados por este servidor.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Produção</td>
<td style="border:1px solid black;">Importe o ficheiro do domínio de utilizador fidedigno exportado no passo 4.</td>
<td style="border:1px solid black;">Permite a utilização dos certificados de licenciador de cliente antigos e dos RAC.
Se as contas de utilizadores estiverem a ser movidas entre florestas como parte desta migração, não se esqueça de que as contas devem ter proxies SMTP correspondentes.</td>
</tr>
</tbody>
</table>
 

Depois de concluir a configuração do servidor de produção, verifique se os utilizadores piloto continuam a poder criar e ler mensagens de correio electrónico anteriormente protegidas. Em seguida, pode adicionar os servidores do RMS ao cluster de que necessita para suportar os utilizadores da organização.
