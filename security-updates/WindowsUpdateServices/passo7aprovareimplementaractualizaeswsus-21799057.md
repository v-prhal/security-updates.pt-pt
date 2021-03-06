---
TOCTitle: 'Passo 7: Aprovar e implementar actualizações WSUS'
Title: 'Passo 7: Aprovar e implementar actualizações WSUS'
ms:assetid: 'c4e58e17-d5e3-4194-8f26-b459e0c03b86'
ms:contentKeyID: 21799057
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Dd939909(v=WS.10)'
---

Passo 7: Aprovar e implementar actualizações WSUS
=================================================

Neste passo, aprova uma actualização para quaisquer computadores do grupo de teste para o Windows Server Update Services 3.0 Service Pack 2 (WSUS 3.0 SP2). Os computadores no grupo contactam automaticamente o servidor WSUS durante as 24 horas seguintes para obterem a actualização. Pode utilizar a funcionalidade de relatórios do WSUS para determinar se as actualizações foram implementadas nos computadores de teste. Quando os testes tiverem sido concluídos com êxito, pode aprovar as actualizações para os respectivos grupos de computadores da sua organização.

Passo 7 Procedimentos
---------------------

-   Aprovar e implementar uma actualização.
-   Verificar o estado de uma actualização.

**Para aprovar e implementar uma actualização**
1.  Na Consola de Administração do WSUS, clique em **Actualizações**. É apresentado um resumo de estado de actualização para **Todas as Actualizações**, **Actualizações Críticas**, **Actualizações de Segurança** e **Actualizações WSUS**.

2.  Na secção **Todas as Actualizações**, clique em **Actualizações necessárias para computadores**.

3.  Na lista de actualizações, seleccione as actualizações que pretende aprovar para instalação no seu grupo de computadores de teste. No painel mais abaixo do painel Actualizações estão disponíveis informações sobre uma actualização seleccionada. Para seleccionar várias actualizações seguidas, mantenha premida a tecla **SHIFT** enquanto clica nas actualizações; para seleccionar várias actualizações alternadas, mantenha premida a tecla **CTRL** enquanto clica nas actualizações.

4.  Clique com o botão direito do rato na selecção e clique em **Aprovar**.

5.  Na caixa de diálogo **Aprovar Actualizações**, seleccione o seu grupo de teste e clique na seta para baixo.

6.  Clique em **Aprovado para Instalação** e clique em **OK**.

7.  A janela Evolução da Aprovação aparece, mostrando a evolução das tarefas que afectam a aprovação da actualização. Quando a aprovação estiver concluída, clique em **Fechar**.

Após 24 horas, poderá utilizar a funcionalidade Relatórios do WSUS para determinar se as actualizações foram implementadas nos computadores do grupo de teste.

**Para verificar o estado de uma actualização**
1.  No painel de navegação da Consola de Administração do WSUS, clique em **Relatórios**.

2.  Na página **Relatórios**, clique no relatório **Resumo de Estado de Actualização**. Aparece a janela **Relatório de Actualizações**.

3.  Se quiser filtrar a lista de actualizações, seleccione os critérios que deseja utilizar, por exemplo, **Incluir actualizações nestas classificações**, e clique em **Executar Relatório** na barra de ferramentas da janela.

4.  Verá o painel **Relatório de Actualizações**. Pode verificar o estado de actualizações individuais seleccionando a actualização na secção esquerda do painel. A última secção do painel do relatório mostra o resumo do estado da actualização.

5.  Pode guardar ou imprimir este relatório clicando no ícone respectivo na barra de ferramentas.

6.  Depois de testar as actualizações, pode aprová-las para instalação nos grupos de computadores respectivos da sua organização.

Recursos adicionais
-------------------

[Manual Passo a Passo do Windows Server Update Services 3.0 SP2](https://technet.microsoft.com/4b504edc-93b3-45b0-a7e8-d0107f1a4442)

Para obter mais informações sobre como utilizar o WSUS 3.0 SP2, consulte:

O Guia de Distribuição de WSUS em [http://go.microsoft.com/fwlink/?LinkId=139832](http://go.microsoft.com/fwlink/?linkid=139832).

O Guia de Funcionamento do WSUS em [http://go.microsoft.com/fwlink/?LinkId=139838](http://go.microsoft.com/fwlink/?linkid=139838).
