---
TOCTitle: Para Especificar o Contacto Administrativo
Title: Para Especificar o Contacto Administrativo
ms:assetid: '31777458-5530-4ae0-ac1f-131b3d98dd35'
ms:contentKeyID: 18123929
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc720237(v=WS.10)'
---

Para Especificar o Contacto Administrativo
==========================================

Para efectuar este procedimento, tem de iniciar sessão localmente no Web site Administração com uma conta de utilizador de domínio que seja membro do grupo Administradores no computador a que está a aceder. Os membros do grupo de administradores de domínio também podem efectuar este procedimento. Como uma boa prática de segurança, considere a utilização do comando **Executar como** para efectuar este procedimento.

O administrador especificado neste procedimento deverá ser um administrador local no servidor de licenciador de servidores porque o utilizador que iniciou a sessão deve ter permissões no ficheiro SubEnrollService.asmx file no servidor de certificação de raiz para aprovisionar um servidor de licenciamento. No caso de o utilizador que está a tentar aprovisionar um servidor de licenciamentos não tiver permissões neste ficheiro, o utilizador pode enviar um pedido ao administrador designado nesta operação para conceder à conta do utilizador as permissões necessárias. Para mais informações, consulte "[Definir Permissões no Ficheiro do Serviço de Pré-inscrição](https://technet.microsoft.com/737bb69b-fe26-4057-9569-e632f7bbf295)" anteriormente nesta secção.

Para abrir a página **Administração Global**, clique em **Iniciar**, aponte para **Todos os programas**, aponte para **Windows RMS** e clique em **Administração do Windows RMS**.

Especificar o Contacto Administrativo
-------------------------------------

#### Para Especificar o Contacto Administrativo

1.  Abra a página **Administração Global** e, em seguida, no Web site em que pretende especificar um contacto administrativo, clique em **Administrar o RMS neste Web site**.

2.  Na área **Ligações da administração**, clique em **Definições de certificação**.

3.  Na área **Contacto administrativo**, escreva o endereço de correio electrónico do administrador a contactar no caso de ocorrerem problemas com a pré-inscrição durante o aprovisionamento de um servidor de licenciamento, sob a forma *nome\_utilizador*@*nome\_domínio.com*.

4.  No final da página, clique em **Submeter**.
