---
TOCTitle: Domínios de Utilizadores Fidedignos
Title: Domínios de Utilizadores Fidedignos
ms:assetid: 'a09b883f-f455-4c46-a4fd-d37b689e1d24'
ms:contentKeyID: 18124114
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc747618(v=WS.10)'
---

Domínios de Utilizadores Fidedignos
===================================

Por predefinição, o RMS não emite licenças de utilização para utilizadores cujos certificados de conta de direitos foram emitidos por um domínio de utilizadores diferentes. Um domínio de utilizadores é uma instalação do RMS composta por um cluster de certificações de raiz, servidores ou clusters de licenciamento opcionais e bases de dados associadas.

Pode configurar o RMS para processar este tipo de pedido importando o certificado de licenciador de servidores de outro domínio de utilizadores e adicionando-o à lista de domínios de utilizadores fidedignos. Neste caso, os utilizadores cujos certificados de contas foram emitidos pelo domínio de utilizadores fidedignos podem submeter pedidos de licenças de utilização à sua instalação. Essas licenças de utilização serão processadas como se fossem pedidos de utilizadores internos.

| ![](images/Cc747618.note(WS.10).gif)Nota                                                                                                            |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| O cluster de certificações de raiz é apresentado automaticamente na lista de domínios de utilizadores fidedignos para todos os servidores do RMS existentes na mesma instalação. |

Pode permitir que utilizadores de diferentes domínios de utilizadores partilhem conteúdo protegido. Esta situação encontra-se descrita nos seguintes exemplos:

-   A sua organização está a trabalhar em conjunto com outra organização em documentos confidenciais, os quais pretende partilhar e proteger. A outra organização está também a executar o RMS. As duas organizações podem adicionar a instalação do RMS de cada uma à lista de domínios de utilizadores fidedignos para que os utilizadores de ambas as organizações possam trabalhar no conteúdo protegido e partilhá-lo na Internet ou numa extranet.
-   Só pode existir uma instalação do RMS em cada floresta do Active Directory. A organização implementou mais do que uma floresta do Active Directory e todas as florestas executam o RMS. Os utilizadores pretendem partilhar conteúdo protegido com outros utilizadores, independentemente da floresta em que residem. Para tal, pode adicionar a instalação do RMS das outras florestas à lista de domínios de utilizadores fidedignos de cada floresta.
-   Os utilizadores da sua organização estão a trabalhar com utilizadores de outra organização em documentos confidenciais que pretendem proteger. A outra organização não está a executar o RMS. Os utilizadores da outra organização podem estabelecer contas do .NET Passport e pode adicionar o .NET Passport à lista de domínios de utilizadores fidedignos da instalação do RMS. Os utilizadores de ambas as empresas podem, desta forma, trabalhar com conteúdo protegido e trocá-lo através da Internet.

Para mais informações sobre domínios de utilizadores fidedignos e obter instruções detalhadas, consulte "Adicionar e Remover Domínios de Utilizadores Fidedignos" e "Estabelecer Políticas de Fidedignidade" em "Utilizar um Servidor do RMS" nesta colecção de documentação.
