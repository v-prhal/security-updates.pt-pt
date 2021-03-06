---
TOCTitle: 'Passo 6: Criar um Grupo de Computadores'
Title: 'Passo 6: Criar um Grupo de Computadores'
ms:assetid: '6039e5dc-d2ce-4d4b-b737-17ebcadbd4a7'
ms:contentKeyID: 18142146
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc720536(v=WS.10)'
---

Passo 6: Criar um Grupo de Computadores
=======================================

Os grupos de computadores são uma parte importante das implementações do WSUS, mesmo que se trate de uma implementação básica. Os grupos de computadores permitem-lhe definir computadores específicos como alvos de actualizações. Existem dois grupos de computadores predefinidos: Todos os Computadores e Computadores Não Atribuídos. Por predefinição, quando cada computador cliente contacta inicialmente o servidor WSUS, o servidor adiciona-o a ambos os grupos.

É possível criar grupos de computadores personalizados. Uma vantagem da criação de grupos de computadores consiste em permitir-lhe testar as actualizações antes de as implementar amplamente. Se o teste correr bem, poderá expandir as actualizações ao grupo Todos os Computadores. Não há limite quanto ao número de grupos personalizados que pode criar.

A configuração de grupos de computadores é um processo de três passos. Primeiro, há que especificar a forma de atribuição de computadores a grupos de computadores. Existem duas opções: *alvos do lado do cliente* e *alvos do lado do servidor* A opção de alvos do lado do servidor envolve a adição manual de cada computador ao respectivo grupo utilizando-se o WSUS. A opção de alvos do lado do cliente envolve a adição automática dos clientes utilizando-se a Política de Grupo ou chaves de registo. Em segundo lugar, há que criar o grupo de computadores no WSUS. Em terceiro lugar, há que mover os computadores para grupos, utilizando-se o método escolhido no primeiro passo.

Este documento explica como utilizar alvos do lado do servidor e mover manualmente computadores para os respectivos grupos utilizando-se a consola WSUS. Se tivesse vários computadores cliente para atribuir a grupos de computadores, poderia utilizar alvos do lado do cliente, o que automatizaria a atribuição de computadores a grupos de computadores.

Pode seguir o Passo 6 para configurar um grupo de teste que contenha pelo menos um computador de teste.

Este passo contém os seguintes procedimentos:

-   Especificar alvos do lado do servidor.
-   Criar um grupo.
-   Mover computadores para o grupo.

**Para especificar o método para atribuir computadores a grupos**
1.  Na barra de ferramentas da consola WSUS, clique em **Opções** e, em seguida, clique em **Opções de Computador**.

2.  Na caixa **Opções de Computador**, clique em **Utilize a tarefa Mover Computadores em Windows Server Update Services**.

3.  Em **Tarefas**, clique em **Guardar definições** e, quando a caixa de diálogo de confirmação aparecer, clique em **OK**.

**Para criar um grupo**
1.  Na barra de ferramentas da consola WSUS, clique em **Computadores**.

2.  Em **Tarefas**, clique em **Criar um grupo de computadores**.

3.  Na caixa **Nome do grupo**, escreva **Teste** e clique em **OK**.

Utilize o próximo procedimento para atribuir um computador cliente apropriado para testes ao grupo de teste. Um computador cliente apropriado para testes é qualquer computador com software e hardware indicativo da maioria de computadores na rede, mas não um computador atribuído a uma função crítica. Desta forma, poderá saber de que forma os computadores comparáveis com o computador de teste irão lidar com as actualizações aprovadas.

**Para adicionar manualmente um computador ao grupo Teste**
1.  Na barra de ferramentas da consola WSUS, clique em **Computadores**.

2.  Na caixa **Grupos**, clique no grupo do computador que pretende mover.

3.  Na lista de computadores, clique no computador que pretende mover.

4.  Em **Tarefas**, clique em **Mover computador seleccionado**.

5.  Na caixa de diálogo **Grupo de computadores**, seleccione o grupo para o qual pretende mover o computador e clique em **OK**.
