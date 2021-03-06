---
TOCTitle: Implementar o RMS nas Florestas
Title: Implementar o RMS nas Florestas
ms:assetid: 'd531dfdc-efff-4eb0-8d99-f1fd19d7a963'
ms:contentKeyID: 18124172
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc747685(v=WS.10)'
---

Implementar o RMS nas Florestas
===============================

Se a organização incluir múltiplas florestas do Active Directory e pretender activar a utilização do RMS na organização, certifique-se de que configurou a rede de forma a que o RMS consiga identificar e autenticar as contas de utilizador e os grupos de distribuição que residem em florestas diferentes.

O RMS utiliza o Active Directory para identificar utilizadores e grupos de distribuição. Quando a implementação do Active Directory da organização inclui múltiplas florestas, o RMS utiliza objectos de contacto para obter as identidades dos utilizadores e dos grupos que integram uma floresta diferente da floresta do servidor do RMS. Para tal, é necessário satisfazer as seguintes três condições:

1.  Os servidores de certificação do RMS têm de existir noutra floresta e os objectos de contacto têm de ser definidos para cada grupo remoto.
2.  As extensões de esquema têm de existir nas florestas que contêm objectos de contacto para poderem apontar para as florestas que contêm os objectos reais.
3.  Os atributos dos objectos de contacto têm de ser sincronizados para apontarem para as florestas que contêm o objecto real.

Por exemplo, suponha que os grupos são definidos e geridos numa floresta e os utilizadores são definidos e geridos noutra floresta. Um utilizador pretende atribuir direitos a conteúdo baseado nos membros de um grupo específico. Neste cenário, o *Servidor\_RMS\_U* é o servidor da floresta que contém as contas de utilizador e o *Servidor\_RMSr\_G* é o servidor da floresta que contém as contas de grupo. Foi estabelecido um domínio de utilizador fidedigno entre estes dois servidores do RMS. Para que o *Servidor\_RMSr\_U* expanda com êxito o membro do grupo especificado na licença de publicação nos limites da floresta, tem de existir um objecto de contacto na floresta local do Active Directory que represente o grupo existente na floresta remota. O RMS pode consultar os atributos do objecto de contacto e detectar que este objecto representa um grupo existente numa floresta diferente. Então, pode procurar um servidor do RMS nessa floresta e determinar se existe uma relação de fidedignidade entre ele e outro servidor do RMS. Quando o *Servidor\_RMS\_U* consulta o Active Directory em relação ao grupo especificado na licença de publicação, o objecto de contacto indica que o grupo pertence a outra floresta. Quando o *Servidor\_RMS\_U* reencaminha o pedido para o servidor do RMS listado no ponto de ligação do serviço (SCP) para esse domínio. O SCP identifica o *Servidor\_RMS\_G* como o servidor de certificação do RMS para o domínio. *O Servidor\_RMS\_U* consulta o *Servidor\_RMS\_G* para obter o membro do grupo.

O atributo que o RMS consulta para estas informações é **msExchOriginatingForest**. Este atributo é instalado por predefinição no esquema do Active Directory se o Exchange Server 2003 estiver instalado na floresta. É necessário ter este atributo na floresta de cada esquema do Active Directory que vai participar no RMS. Se não estiver a utilizar o Exchange Server 2003, pode adicionar as extensões de esquema transferindo o RMS Administration Toolkit. O toolkit contém um ficheiro de esquema e instruções para a adição ao Active Directory.

Estes atributos devem ser sincronizados para que o objecto de contacto aponte para o objecto real nas outras florestas. Depois de o atributo ser adicionado ao esquema do Active Directory, tem de configurar o respectivo valor para ser o nome de domínio totalmente qualificado (FQDN) da floresta na qual o grupo reside; por exemplo corp.fabrikam.com.

Para tal pode utilizar o Microsoft Identity Integration Server (MIIS) 2003 ou o Identity Integration Feature Pack (IIFP) e o agente de gestão para a lista de endereços global (GAL) do Active Directory.

Tem de activar o servidor local do RMS para obter privilégios suficientes para procurar o Active Directory remoto e chamar as interfaces remotas .NET existentes na instalação remota do RMS.

Para suportar a expansão dos grupos nas florestas, a conta utilizada para a conta de serviço do RMS em cada floresta deve também ter permissões de leitura e execução para o Active Directory. O RMS concede automaticamente acesso de leitura para o Active Directory a todos os utilizadores autenticados com credenciais de domínio. Para aumentar a segurança, pode remover este acesso da lista de controlo de acesso discricionário (DACL) e substituí-la por contas de serviço individuais a partir das diferentes florestas.

Dependendo se existem ou não relações de fidedignidade do Active Directory entre as florestas local e remota, as permissões necessárias para a conta de serviço do RMS podem ser diferentes. A lista seguinte identifica os modelos de fidedignidade e as permissões necessárias:

-   **Fidedignidade bidireccional existente**. A floresta local do RMS confia e é considerada fidedigna pela floresta de origem do grupo. A conta de serviço do RMS para o servidor do RMS existente em cada floresta pode ser qualquer conta de domínio válida da floresta. Certifique-se de que adiciona a conta de serviço local do RMS à DACL da pasta \\Inetpub\\wwwroot\\\_wmcs\\drmRemote em todos os servidores do RMS existentes na floresta de origem do grupo.
-   **Fidedignidade unidireccional existente**. A floresta local do RMS confia na floresta de origem do grupo, mas não é considerada fidedigna por esta. A conta de serviço do RMS para todos os servidores do RMS existentes na organização deve ter origem numa conta de domínio válida existente na floresta fidedigna. Adicione esta conta à DACL da pasta \\Inetpub\\wwwroot\\\_wmcs\\drmRemote em todos os servidores do RMS existentes na floresta de origem do grupo.
-   **Fidedignidade inexistente**. As florestas existentes na organização não podem autenticar utilizadores e grupos de outras florestas. Recomenda-se que não utilize a expansão de grupos em florestas quando estas não têm uma relação de fidedignidade. No entanto, se for um requisito operacional, pode activar este cenário configurando a conta de serviço do RMS como uma conta de domínio válida em ambas as florestas e utilizando obrigatoriamente o mesmo nome de utilizador e a mesma palavra-passe. É também necessário criar uma conta de computador local em cada servidor front-end do RMS com o mesmo nome de utilizador e a mesma palavra-passe que as contas de domínio utilizadas para a conta de serviço do RMS em ambas as florestas. Isto fornece automaticamente as permissões suficientes de serviço local necessárias à autenticação do Active Directory remoto e do servidor remoto do RMS.

Utilizar Políticas de Fidedignidade do RMS
------------------------------------------

Quando o RMS é implementado numa organização com múltiplas florestas, é necessário implementar um servidor de certificação do RMS em cada floresta que aloja as contas de utilizadores que participam no sistema do RMS. Se pretender que florestas diferentes partilhem conteúdo protegido pelo RMS, tem de configurar as políticas de fidedignidade do RMS para que os certificados e as licenças gerados pelo outro servidor do RMS possam ser considerados como fidedignos. Existem duas políticas de fidedignidade que podem ser utilizadas com o RMS: domínios de utilizadores fidedignos e domínios de publicação fidedignos. Os domínios de utilizadores fidedignos permitem ao servidor do RMS confiar nos certificados de conta de direitos (RACs) gerados por outro servidor de certificação do RMS e emitir licenças de utilização para os utilizadores com RACs de outro servidor. Os domínios de publicação fidedignos permitem ao servidor do RMS gerar licenças de utilização baseadas em licenças de publicação que especificam o outro servidor de licenciamento.

A seguir encontra algumas opções para a utilização das políticas de fidedignidade que suportam múltiplas florestas:

-   Um cluster de certificação do RMS em cada floresta com um cluster de licenciamento único partilhado por todos os utilizadores. O cluster de licenciamento do RMS seria configurado com um domínio de utilizador fidedigno que inclui todos os clusters de certificação do RMS. Os clientes do RMS seriam configurados com uma chave de registo para ligação ao cluster de licenciamento e obtenção de licenças de utilização.
-   Um cluster de certificação e licenciamento do RMS de cada floresta com um domínio de utilizador fidedigno configurado em cada cluster para confiar nos servidores do RMS das outras florestas. Cada utilizador utilizaria o servidor do RMS da respectiva floresta para obter licenças de utilização e poderia detectar o respectivo servidor de licenciamento através do ponto de ligação do serviço no Active Directory.
-   Se os consumidores do conteúdo protegido pelo RMS fizerem parte de uma floresta sem acesso à floresta a partir da qual o conteúdo foi publicado, um domínio de publicação fidedigno pode ser estabelecido para permitir o licenciamento e o consumo do conteúdo. Os domínios de publicação fidedignos requerem a importação da chave privada do servidor do RMS utilizada na publicação do conteúdo.

Para mais informações sobre a configuração da política de fidedignidade, consulte “Gerir a Confiança e a Política de Fidedignidade” na secção “Utilizar um Servidor do RMS” nesta colecção de documentação.
