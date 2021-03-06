---
TOCTitle: Hierarquia de Fidedignidade do RMS
Title: Hierarquia de Fidedignidade do RMS
ms:assetid: '2d44182f-a653-4383-aba1-dade53f7cf9a'
ms:contentKeyID: 18123920
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc720232(v=WS.10)'
---

Hierarquia de Fidedignidade do RMS
==================================

Os componentes envolvidos num sistema do RMS incluem o Serviço de Inscrição da Microsoft, os servidores organizacionais do RMS, os computadores clientes e os utilizadores do sistema. Para cada componente é emitido um certificado que estabelece a sua identificação no sistema. Uma hierarquia fidedigna define a relação de fidedignidade entre esses certificados e as entidades que os possuem. Define também a relação de fidedignidade entre as entidades fidedignas e as licenças que elas emitem para outras entidades consideradas fidedignas.

A hierarquia de fidedignidade liga certificados e licenças numa cadeia de fidedignidade que o RMS pode seguir sempre a partir de um certificado ou de uma licença específicos até ao par de chaves fidedignas. A cadeia de fidedignidade inclui o certificado actual, o certificado da entidade que o emitiu, o certificado da entidade que emitiu o certificado dessa entidade, e por aí fora, até à raiz da fidedignidade.

Para o RMS, a raiz da fidedignidade ou a "âncora de fidedignidade" é um par chaves da Microsoft. Esta raiz comum de fidedignidade permite a uma organização construir um ecossistema fidedigno que contém entidades fidedignas, tais como utilizadores e parceiros, tanto dentro como fora da organização.

O seguinte diagrama apresenta a hierarquia fidedigna numa organização. A cadeia de fidedignidade vai até aos serviços da Microsoft que emitem os certificados de base.

![](images/Cc720232.6c169175-94fb-4ec0-93bc-12748aae3ac4(WS.10).gif)
1.  Para cada computador cliente é emitido um cofre exclusivo que contém a chave pública raiz da Microsoft.
2.  Quando recebe um pedido de licença, o RMS valida os principais seguindo o caminho da hierarquia de fidedignidade até à raiz de fidedignidade.
3.  O RMS verifica a autenticidade da entidade fidedigna designada na licença.
4.  O RMS verifica o certificado da entidade fidedigna que foi emitido por um servidor existente na hierarquia de fidedignidade.

Em cada nível da cadeia de certificados, o RMS valida a licença ou o certificado e, em seguida, verifica a associação a uma raiz de fidedignidade conhecida através de uma cadeia de fidedignidade. Cada licença ou certificado da cadeia pode ser verificado pelo RMS para validação das seguintes condições:

-   Se o XrML é válido.
-   Se a assinatura do emissor é válida.
-   Se a semântica da licença é a apropriada para o fim a que se destina.
-   Se as condições (como as datas de validade) estão satisfeitas.
-   Se a licença não foi revogada.
-   Se a chave da assinatura da licença corresponde à chave do emissor certificado.
