---
TOCTitle: Para Activar a Certificação de Dispositivos Móveis
Title: Para Activar a Certificação de Dispositivos Móveis
ms:assetid: '93ec088e-9056-4c3c-bd97-1173fb194578'
ms:contentKeyID: 18124100
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc747603(v=WS.10)'
---

Para Activar a Certificação de Dispositivos Móveis
==================================================

Para efectuar este procedimento necessita de ter iniciado a sessão localmente no Web site de Administração com uma conta de utilizador de domínio que seja membro do grupo de administradores no computador a que está a aceder. Os membros do grupo de administradores de domínio também podem efectuar este procedimento. Como uma boa prática de segurança, considere a utilização do comando **Executar como** para efectuar este procedimento.

Este procedimento só é aplicável no cluster de certificações de raiz.

Este procedimento assume que criou um grupo de utilizadores com as contas dos utilizadores de dispositivos móveis que consumem conteúdo protegido pelo RMS.

Activar a Certificação de Dispositivos Móveis
---------------------------------------------

#### Para Activar a Certificação de Dispositivos Móveis

1.  No servidor de certificações de raiz, abra um browser do sistema de ficheiros e vá para a &lt;unidade do sistema&gt;:\\Inetpub\\wwwroot\\\_wmcs\\Certification.

2.  Para activar os dispositivos móveis para a recepção de certificados de contas de direitos (RACs), clique com o botão direito do rato no ficheiro MobileDeviceCertification.asmx e, em seguida, clique em **Propriedades**..

3.  No separador **Segurança**, clique em **Adicionar** e adicione o grupo criado para esta categoria de utilizadores e o **RMS Service Group**.

4.  Na lista **Permissões** dos grupos, seleccione a caixa de verificação **Permitir** para as permissões **Leitura** e **Leitura & Execução** e, em seguida, clique em **OK**.
