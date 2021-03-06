---
TOCTitle: Licenças de Utilização e Utilizadores Externos
Title: Licenças de Utilização e Utilizadores Externos
ms:assetid: '02db9bda-180e-438f-863d-26252083a471'
ms:contentKeyID: 18123894
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc720176(v=WS.10)'
---

Licenças de Utilização e Utilizadores Externos
==============================================

O RMS permite aos autores partilharem conteúdo protegido com utilizadores externos autorizados na Internet. O RMS oferece protecção igual à publicação de conteúdo para utilizadores internos e externos pois os direitos associados ao conteúdo têm de ser licenciados por um servidor do RMS. Isto permite que as organizações possam partilhar e trabalhar em conjunto com documentos confidenciais, tais como contratos, através da Internet.

Normalmente, um utilizador externo obtém acesso ao RMS através da Internet. (Se um utilizador externo consegue aceder directamente à rede interna, através, por exemplo, de uma ligação VPN, esse utilizador é funcionalmente equivalente a um utilizador interno.) Quer o utilizador pertença à organização de publicação quer seja externo, o processo de aquisição de uma licença de utilização é semelhante ao descrito em "[Aquisição da Licença de Utilização](https://technet.microsoft.com/0b6cde34-418a-4dee-9d27-b65b93b535ac)" anteriormente nesta secção. Não é necessário que um utilizador faça parte da rede do autor ou tenha uma conta de utilizador nessa rede para pedir uma licença de utilização.

Basta que:

-   O utilizador tenha um certificado de conta de direitos válido.
-   O utilizador tenha acesso ao servidor de licenciamento do RMS que emitiu a licença de publicação e que pode existir na intranet ou numa extranet.
-   A instalação do RMS que emitiu o certificado de conta do utilizador conste da lista de domínios de utilizadores fidedignos da instalação do RMS que emitiu a licença de utilização.

Os seguintes tipos de utilizadores externos podem obter licenças de utilização:

-   Utilizadores cujas contas pertencem a uma floresta diferente do Active Directory que também tem uma instalação do RMS. A instalação do RMS da outra floresta deve ser definida como domínios de utilizadores fidedignos para esta instalação.
-   Utilizadores de outra organização com uma instalação do RMS adicionada à lista de domínios de utilizadores fidedignos para esta instalação.
-   Utilizadores com certificados de contas de direitos baseados no .NET Passport quando o Serviço de Certificação do Microsoft RMS consta da lista de domínios de utilizadores fidedignos para esta instalação.

Pode adicionar uma organização separada ou outra instalação do RMS da organização à lista de domínios de utilizadores fidedignos. Depois de adicionar um domínio, pode definir quais os domínios de endereços de correio electrónico que podem ser considerados fidedignos nesse domínio, bem como seleccionar se deve ou não considerar fidedignos os identificadores de segurança (SIDs) presentes nesse domínio.

Outra organização ou uma instalação do RMS da organização pode adicionar a instalação do RMS à respectiva lista de domínios de utilizadores fidedignos para que os servidores do RMS consigam processar os pedidos de licenças de utilização dos utilizadores.

Para mais informações sobre como criar domínios de utilizadores fidedignos entre o RMS e outras organizações, consulte "[Domínios de Utilizadores Fidedignos](https://technet.microsoft.com/a09b883f-f455-4c46-a4fd-d37b689e1d24)" posteriormente nesta secção e "Adicionar e Remover Domínios de Publicação Fidedignos" em "Utilizar um Servidor do RMS" nesta colecção de documentação.
