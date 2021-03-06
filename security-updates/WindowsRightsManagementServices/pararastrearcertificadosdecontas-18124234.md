---
TOCTitle: Para Rastrear Certificados de Contas
Title: Para Rastrear Certificados de Contas
ms:assetid: 'f9efac9f-c725-4bce-a89f-7691b0d8ffc0'
ms:contentKeyID: 18124234
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc747752(v=WS.10)'
---

Para Rastrear Certificados de Contas
====================================

Para efectuar este procedimento, tem de iniciar sessão localmente no Web site Administração com uma conta de utilizador de domínio que seja membro do grupo Administradores no computador a que está a aceder. Os membros do grupo de administradores de domínio também podem efectuar este procedimento. Como uma boa prática de segurança, considere a utilização do comando **Executar como** para efectuar este procedimento.

Para abrir a página **Administração Global**, clique em **Iniciar**, aponte para **Todos os programas**, aponte para **Windows RMS** e clique em **Administração do Windows RMS**.

Esta funcionalidade está disponível apenas no cluster de certificações de raiz; não está disponível em quaisquer outros clusters ou servidores de licenciamentos.

Este procedimento só pode ser utilizado para estimar o número de licenças de utilização e é útil apenas se essas licenças forem facturadas. O número apresentado na página Relatório de certificação de contas de gestão de direitos (RM) é uma aproximação. Se a base de dados de configuração não for actualizada, de forma a eliminar os utilizadores que já não estão activos, este número não reflecte a realidade. Além disso, se existirem utilizadores a quem foram emitidas várias licenças em várias florestas, as licenças adicionais não estão incluídas no número apresentado.

Rastrear Certificados de Conta
------------------------------

#### Para Rastrear Certificados de Contas

1.  Abra a página **Administração Global** e, em seguida, no Web site em que pretende rastrear os certificados, clique em **Administrar o RMS neste Web site**.

2.  Na área de ligações **Administração**, clique em Relatório de certificação de contas do RM.

3.  Sob **Número total de utilizadores certificados**, veja o número de utilizadores que receberam certificados de contas a partir deste cluster de certificações de raiz.

Para mais informações, consulte "[Rastrear Certificados de Conta](https://technet.microsoft.com/5bb0f3cf-fc44-4e60-a93f-c789d6f8a902)" posteriormente nesta secção.
