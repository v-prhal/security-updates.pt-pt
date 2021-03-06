---
TOCTitle: Para Editar um Modelo de Política de Direitos
Title: Para Editar um Modelo de Política de Direitos
ms:assetid: '9580b934-bd6f-4097-9d3c-4fc14a3147fa'
ms:contentKeyID: 18124094
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc747684(v=WS.10)'
---

Para Editar um Modelo de Política de Direitos
=============================================

Para efectuar este procedimento, tem de iniciar sessão localmente no Web site Administração com uma conta de utilizador de domínio que seja membro do grupo Administradores no computador a que está a aceder. Os membros do grupo de administradores de domínio também podem efectuar este procedimento. Como uma boa prática de segurança, considere a utilização do comando **Executar como** para efectuar este procedimento.

Para abrir a página **Administração Global**, clique em **Iniciar**, aponte para **Todos os programas**, aponte para **Windows RMS** e clique em **Administração do Windows RMS**.

Editar um Modelo de Política de Direitos
----------------------------------------

#### Para Editar um Modelo de Política de Direitos

1.  Abra a página **Administração Global** e, em seguida, no Web site em que pretende editar o modelo de política de direitos, clique em **Administrar o RMS neste Web site**.

2.  Na área **Ligações da administração**, clique em **Modelos de política de direitos**.

3.  Em **Nome do modelo**, clique no nome do modelo que pretende editar.

4.  Na área **Identificação do modelo**, modifique as informações nas áreas **Nome do modelo**, **Descrição do modelo** e **URL de pedido de direitos**, conforme apropriado.

5.  Na área **Utilizadores e grupos**, proceda de uma das seguintes formas:

    -   Para adicionar um utilizador ou um grupo, em **Adicionar utilizadores ou grupos**, escreva o endereço válido de correio electrónico de um determinado utilizador ou grupo a adicionar, clique em **Adicionar** e, em seguida, seleccione o nome em **Utilizadores ou grupos actuais**. Na área **Direitos**, seleccione todos os direitos a serem concedidos ao utilizador ou grupo seleccionado.
    -   Para modificar os direitos de um utilizador ou grupo existente, seleccione o nome em **Utilizadores ou grupos actuais** e, em seguida, seleccione ou desmarque as caixas de verificação referentes aos direitos, conforme apropriado.
    -   Para remover um utilizador ou um grupo, seleccione o nome em **Utilizadores ou grupos actuais** e, em seguida, clique em **Remover**.

6.  Na área **Política de expiração**, edite as informações para alterar a data de expiração e de renovação das licenças, conforme apropriado.

7.  Na área **Política expandida**, edite as informações para alterar a forma como as licenças de conteúdo devem ser implementadas, incluindo a persistência dos direitos de autor, se os browsers fidedignos devem ou não ser suportados, persistência da licença dentro do conteúdo e a imposição de dados específicos a qualquer aplicação, conforme apropriado.

8.  Na área **Política de revogações**, seleccione se é ou não necessária uma lista de revogações para o conteúdo criado com este modelo. Se seleccionar **Requerer a revogação**, especifique as seguintes definições, conforme apropriado:

    -   Em **URL**, escreva o URL para onde o ficheiro da lista de revogação foi enviado. Se for necessário suportar utilizadores desligados ou externos, o URL deve estar acessível a partir da rede empresarial e da Internet. Para mais informações, consulte "[Implementar uma Revogação](https://technet.microsoft.com/4735f060-7197-4ae2-830a-f91bcc4de30a)" anteriormente nesta secção.
    -   Em **Intervalo de actualização da lista de revogações**, escreva o número de dias que a lista de revogações deve permanecer válida. Se um utilizador tiver uma cópia da lista de revogações com uma data anterior a esse valor, o utilizador deve obter uma lista de revogações actualizada para poder consumir o conteúdo.
    -   Em **Ficheiro da chave pública**, escreva o caminho e o nome do ficheiro da chave pública para a lista de revogações. Para mais informações sobre este ficheiro, consulte "Inserir uma Assinatura numa Lista de Revogações" anteriormente nesta secção.

    | ![](images/Cc747684.Caution(WS.10).gif)Atenção                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
    |----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Tenha cuidado ao implementar a revogação. Com base no intervalo de actualização que especificar, terá de renovar a lista de revogações periodicamente; se não o fizer, a lista expira automaticamente, impedindo os utilizadores de consumir conteúdo que necessite dessa lista. Para garantir que não impede, inadvertidamente, os utilizadores de consumirem conteúdo, determine cuidadosamente o intervalo necessário para actualizar a lista de revogações. Para mais informações, consulte "[Gerir Revogações](https://technet.microsoft.com/df732a7d-1fb0-4845-87ca-fab4bc5f98a0)" anteriormente nesta secção. |

9.  Clique em **Submeter**.

Para mais informações sobre a execução deste procedimento, consulte "[Criar e Modificar Modelos de Política de Direitos](https://technet.microsoft.com/6014176f-ef71-4d29-b3e3-da129c18563d)" anteriormente nesta secção.
