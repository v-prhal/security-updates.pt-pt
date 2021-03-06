---
TOCTitle: Para Adicionar um Modelo de Política de Direitos
Title: Para Adicionar um Modelo de Política de Direitos
ms:assetid: '1a5555cd-6d39-4078-a879-4106864674be'
ms:contentKeyID: 18123907
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc720206(v=WS.10)'
---

Para Adicionar um Modelo de Política de Direitos
================================================

Para efectuar este procedimento, tem de iniciar sessão localmente no Web site Administração com uma conta de utilizador de domínio que seja membro do grupo Administradores no computador a que está a aceder. Os membros do grupo de administradores de domínio também podem efectuar este procedimento. Como procedimento de segurança recomendado, considere utilizar o comando **Executar como** para efectuar este procedimento.

Para abrir a página **Administração Global**, clique em **Iniciar**, aponte para **Todos os Programas**, aponte para **Windows RMS** e, em seguida, clique em **Administração do Windows RMS**.

Adicionar um Modelo de Política de Direitos
-------------------------------------------

#### Para Adicionar um Modelo de Política de Direitos

1.  Abra a página **Administração Global** e, em seguida, no Web site em que pretende adicionar um modelo de política de direitos, clique em **Administrar o RMS neste Web site**.

2.  Na área **Ligações da administração**, clique em **Modelos de política de direitos**.

3.  Em **Idioma**, clique para seleccionar o idioma que deseja que seja utilizado pelo modelo.

4.  Clique em **Adicionar um modelo de política de direitos**

5.  Na área **Identificação do modelo**, especifique um nome, uma descrição e o URL de pedido de direitos para o modelo.

6.  Na área **Utilizadores e grupos**, em **Adicionar utilizadores ou grupos**, escreva o endereço de correio electrónico válido de um utilizador ou grupo a adicionar e, em seguida, clique em **Adicionar**. Repita esta acção para adicionar outros utilizadores ou grupos.

7.  Em **Utilizadores ou grupos actuais**, seleccione o endereço de correio electrónico de um utilizador ou grupo ao qual vai atribuir direitos.

8.  Seleccione as caixas de verificação de todos os direitos a serem concedidos ao utilizador ou grupo seleccionado. Repita essa acção para conceder direitos aos restantes utilizadores ou grupos.

9.  Na área **Política de expiração**, seleccione uma das três opções de expiração e, em seguida, especifique uma data ou hora de validade, consoante o mais apropriado. Se apropriado, seleccione **As licenças de utilização de conteúdo devem ser renovadas a cada** e especifique o número de dias a decorrer entre as renovações.

10. Na área **Política expandida**, seleccione pelo menos uma ou mais das quatro opções. Se seleccionar **Impor dados específicos à aplicação**, especifique um nome e um valor para os dados a serem impostos e, em seguida, clique em **Adicionar**.

11. Para implementar a revogação, na área **Política de revogações**, seleccione a caixa de verificação **Requerer a revogação** e, em seguida, execute os seguintes passos:

    1.  Em **URL ou UNC**, escreva o URL para onde o ficheiro da lista de revogação foi enviado. Se for necessário suportar utilizadores desligados ou externos, o URL deve estar acessível a partir da rede empresarial e da Internet.
    2.  Em **Intervalo de actualização da lista de revogações**, escreva o número de dias que a lista de revogações deve permanecer válida. Se um utilizador tiver uma cópia da lista de revogações com uma data anterior a esse valor, o utilizador deve obter uma lista de revogações actualizada para poder consumir o conteúdo.
    3.  Em **Ficheiro da chave pública**, escreva o caminho e o nome do ficheiro ou clique em **Procurar**, para localizar o ficheiro da chave pública para a lista de revogações. Para mais informações sobre este ficheiro, consulte "Inserir uma assinatura numa lista de revogações" anteriormente nesta secção.

    | ![](images/Cc720206.Caution(WS.10).gif)Atenção                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
    |----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Tenha cuidado ao implementar a revogação. Com base no intervalo de actualização que especificar, terá de renovar a lista de revogações periodicamente; se não o fizer, a lista expira automaticamente, impedindo os utilizadores de consumir conteúdo que necessite dessa lista. Para garantir que não impede, inadvertidamente, os utilizadores de consumirem conteúdo, determine cuidadosamente o intervalo necessário para actualizar a lista de revogações. Para mais informações, consulte "[Gerir Revogações](https://technet.microsoft.com/df732a7d-1fb0-4845-87ca-fab4bc5f98a0)" anteriormente nesta secção. |

12. Clique em **Submeter**.

Para mais informações sobre as revogações, consulte "[Gerir Revogações](https://technet.microsoft.com/df732a7d-1fb0-4845-87ca-fab4bc5f98a0)" anteriormente nesta secção.

Para mais informações sobre a especificação de opções de revogação, consulte "[Definir Políticas de Revogação](https://technet.microsoft.com/e2fffe9f-def7-439b-a8aa-43f8a065813d)" anteriormente nesta secção.

Para mais informações sobre a execução deste procedimento, consulte "[Criar e Modificar Modelos de Política de Direitos](https://technet.microsoft.com/6014176f-ef71-4d29-b3e3-da129c18563d)" anteriormente nesta secção.
