---
TOCTitle: Para Renovar um Certificado de Licenciador de Servidores
Title: Para Renovar um Certificado de Licenciador de Servidores
ms:assetid: 'affce9cf-8b46-4293-8e1c-ee06f2ca6537'
ms:contentKeyID: 18124124
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc747636(v=WS.10)'
---

Para Renovar um Certificado de Licenciador de Servidores
========================================================

Para efectuar este procedimento, tem de iniciar sessão localmente no Web site Administração com uma conta de utilizador de domínio que seja membro do grupo Administradores no computador a que está a aceder. Os membros do grupo de administradores de domínio também podem efectuar este procedimento. Como uma boa prática de segurança, considere a utilização do comando **Executar como** para efectuar este procedimento.

Para abrir a página **Administração Global**, clique em **Iniciar**, aponte para **Todos os programas**, aponte para **Windows RMS** e clique em **Administração do Windows RMS**.

Se seleccionou a utilização da renovação Offline e se estiver a utilizar um computador com uma configuração de segurança do browser melhorada, como um computador com o Windows Server 2003 ou o Windows XP Service Pack 2, para efectuar a ligação à Internet e pedir um certificado de licenciador de servidores, certifique-se de que adiciona o URL do Web site do Serviço de Inscrição à zona de Sites Fidedignos para permitir a transferência do certificado de licenciador de servidores. Este URL é URL https://activation.drm.microsoft.com.

Se estiver a utilizar o processo de inscrição offline, certifique-se de que o computador que está a utilizar para submeter o pedido de inscrição ao Serviço de Inscrição da Microsoft Enrollment Service tem a CA GTE Cyber Trust Root instalada no armazenamento de certificados. Esta autoridade de certificação é considerada fidedigna por predefinição em máquina com o Windows Server 2003. Se o computador tiver outra versão do Windows, pode tornar fidedigna esta CA instalando as actualizações mais recentes do certificado a partir do Windows Update.

Renovar um Certificado de Licenciador de Servidores
---------------------------------------------------

#### Para Renovar um Certificado de Licenciador de Servidores

1.  Abra a página **Administração Global** e, em seguida, no Web site em que pretende renovar um certificado, clique em **Administrar o RMS neste Web site**.

2.  Na página **Administração**, na área **Recursos de cluster**, clique no botão **Renovar**. Aparece a caixa de diálogo Renovar.

3.  Se o servidor estiver ligado à Internet, seleccione a opção **Online** e clique em **Renovar** para renovar automaticamente o certificado de licenciador do servidor.

4.  Se o servidor não estiver ligado à Internet, seleccione a opção **Offline** e clique no botão **Exportar**. Aparece a caixa de diálogo **Transferência de ficheiros**.

5.  Clique em **Guardar**. Aparece a caixa de diálogo **Guardar como**.

    | ![](images/Cc747636.note(WS.10).gif)Nota                                                                                                                |
    |--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Na caixa de diálogo **Transferência de Ficheiros**, não clique em **Abrir**. Se clicar em **Abrir** aparece uma mensagem de erro e o ficheiro de pedido de inscrição não é guardado. |

6.  Clique em **Guardar** para exportar o pedido de renovação para um ficheiro. Por predefinição, o ficheiro é guardado no ambiente de trabalho e é-lhe atribuído o nome *Nome\_servidor*RenewalRequest.xml, em que *nome\_servidor* é substituído pelo nome do servidor do RMS. Pode guardar o ficheiro numa localização diferente seleccionando a localização que deseja a partir do menu pendente Guardar em. Também pode alterar o nome de ficheiro em **Nome de ficheiro**.

7.  Depois de guardar o ficheiro de pedido de renovação, aparece a caixa de diálogo **Transferência concluída**. Pode clicar em **Abrir** para ver o código XML no ficheiro, mas não pode fazer alterações no ficheiro. Para abrir a pasta onde o ficheiro está armazenado, clique em **Abrir pasta**. Clique em **Fechar** se terminou a procura no ficheiro e a verificação da sua localização.

8.  Transfira o ficheiro de pedido de renovação do servidor para um computador que possa efectuar a ligação à Internet e, em seguida, navegue para o Web site [Serviço de Inscrição]() (https://go.microsoft.com/fwlink/?LinkId=25828).

9.  Siga as instruções no Web site para obter um certificado de licenciador de servidores.

10. Volte a colocar o certificado de licenciador de servidores na certificação de raiz.

11. Na área de recursos **Cluster**, clique em **Renovar**. A caixa de diálogo **Renovar** abre-se.

12. Na caixa de diálogo **Renovar**, clique no botão **Procurar** e localize o certificado de licenciador de servidores que transferiu e clique no botão **Importar**.

13. Clique em **Sim** para confirmar que deseja importar este certificado.

14. Depois de ter renovado o certificado de licenciador de servidores com sucesso, a área **Recursos de cluster** é actualizada para exibir a nova data de validade do certificado de licenciador de servidores.

Para mais informações sobre a renovação de certificados de licenciador de servidores, consulte "[Gerir Certificados de Licenciador de Servidores](https://technet.microsoft.com/549979ad-13ee-4abc-8281-3e002a5a9561)" anteriormente nesta secção.
