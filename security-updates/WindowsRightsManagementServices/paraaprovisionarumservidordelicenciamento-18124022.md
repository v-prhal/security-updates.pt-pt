---
TOCTitle: Para Aprovisionar um Servidor de Licenciamento
Title: Para Aprovisionar um Servidor de Licenciamento
ms:assetid: '4d67b898-0ba9-4eef-ab7d-ee0ca55a688e'
ms:contentKeyID: 18124022
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc747563(v=WS.10)'
---

Para Aprovisionar um Servidor de Licenciamento
==============================================

Para efectuar este procedimento, tem de iniciar sessão localmente no Web site Administração com uma conta de utilizador de domínio que seja membro do grupo Administradores no computador a que está a aceder. Os membros do grupo de administradores de domínio também podem efectuar este procedimento. Além disso, o processo de pré-inscrição requer permissões de leitura e de execução tanto para a conta de utilizador de domínio como para o RMS Service Group. Para mais informações, consulte "[Definir Permissões no Ficheiro do Serviço de Pré-inscrição](https://technet.microsoft.com/737bb69b-fe26-4057-9569-e632f7bbf295)" anteriormente nesta secção. Se estiver a utilizar uma base de dados remota do SQL Server, a conta utilizada para iniciar a sessão também deve ter a função de criadores de base de dados no SQL Server. Como uma boa prática de segurança, considere a utilização do comando **Executar como** para efectuar este procedimento.

Para abrir a página **Administração Global**, clique em **Iniciar**, aponte para **Todos os programas**, aponte para **Windows RMS** e clique em **Administração do Windows RMS**.

Em cada servidor, só pode aprovisionar o RMS num único Web site. Se desejar aprovisionar o RMS num Web site diferente do predefinido, utilize o Gestor de Serviços de Informação Internet para adicionar o Web site antes de iniciar este processo de aprovisionamento. Se o Web site que pretende aprovisionar não aparecer na lista de Web sites, feche a página **Administração Global**, adicione o Web site e, depois, inicie novamente o processo de aprovisionamento.

Se estiver a implementar o RMS num ambiente em que o nível funcional de domínio do Active Directory utiliza o modo nativo do Microsoft Windows 2000, o Windows RMS poderá não conseguir ler o atributo **memberOf** nos objectos do Active Directory quando tentar expandir os membros do grupo. Para permitir que o RMS leia o atributo **memberOf**, a conta de serviço do RMS deve utilizar uma conta de domínio que seja membro do grupo de Acesso compatível com versões anteriores ao Windows 2000 (incorporado) existente na floresta.

Se escrever um URL personalizado para o cluster, não se esqueça de o registar no seu sistema de nomes de domínios (DNS) e confirmar se está a funcionar. Se esta for uma implementação activada pela Internet, verifique se o URL está disponível a partir tanto da Internet como de dentro da sua organização. Deve especificar HTTPS para o URL do cluster caso tenha activado o SSL para os ficheiros de serviços Web.

Aprovisionar um Servidor de Licenciamento
-----------------------------------------

#### Para aprovisionar um servidor de licenciamentos

1.  Abra a página **Administração Global** e, no Web site em que pretende aprovisionar o RMS, clique em **Aprovisionar o RMS neste Web site**.

    Pode seleccionar o Web site predefinido ou outro Web site que tenha criado nos Serviços de Informação Internet (IIS) para esse fim.

    | ![](images/Cc747563.Warning(WS.10).gif)Aviso                                                                                                                                                                               |
    |---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Não é suportada a execução de outros Web sites ou serviços no mesmo servidor do RMS. Se tal ocorresse, poderiam ser executados vários serviços e aplicações sob a mesma conta do RMS, o que poderia expor as chaves privadas a operações sem garantias. |

2.  Na área **Base de dados de configuração**, a opção predefinida é a de criar a base de dados de configuração no servidor local. Pode utilizar um servidor de bases de dados como o SQL Server™ 2000 com o SP3 ou o Microsoft SQL Server 2000 Desktop Engine (MSDE) para uma base de dados local. Se estiver a utilizar uma base de dados remota, ou se estiver a utilizar o servidor de bases de dados no servidor local, mas a instância do servidor das bases de dados tiver um nome diferente deste servidor, seleccione **Base de dados remota** e introduza o nome do servidor de bases de dados.

    | ![](images/Cc747563.Important(WS.10).gif)Importante                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
    |---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | É recomendável utilizar o Microsoft SQL Server Desktop Engine para suportar bases de dados do RMS apenas em ambientes de teste, visto que o Microsoft SQL Server Desktop Engine não suporta interfaces de rede. Além disso, os termos de utilização do Microsoft SQL Server Desktop Engine especificam que não é possível utilizar ferramentas de cliente de SQL Server para manipular bases de dados do Microsoft SQL Server Desktop Engine. Com esta restrição não é possível ver informações relativas ao registo nem alterar dados armazenados na base de dados de configuração.  |

3.  Na área **Conta de serviço do RMS**, especifique a conta de serviço do RMS sob a qual o RMS será executado para a maior parte das operações normais. Para a instalação de um único servidor, pode especificar a conta de sistema local ou uma conta de domínio. Para todas as outras instalações, tem de especificar uma conta de domínio. Para uma conta de domínio, proporcione o nome da conta sob a forma *nome\_domínio*\\*nome\_utilizador* e a palavra-passe.

    | ![](images/Cc747563.Warning(WS.10).gif)Aviso                                                                                                                                                                                                                                                                                                                                                                                                                                              |
    |------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | A conta de sistema local tem acesso a quase todos os recursos do sistema operativo e, por conseguinte, tem sérias implicações sobre a segurança. Sempre que possível, procure evitar a utilização da conta de Sistema Local como conta de serviço do RMS. Como alternativa, crie uma conta de utilizador de domínio especial para utilizar como conta de serviço do RMS e não lhe conceda permissões especiais. A conta de serviço do RMS não pode ser a mesma conta de domínio que foi utilizada para instalar o RMS. |

4.  Na área **URL do cluster**, indique o URL do servidor ou cluster que será utilizado para os clientes na rede interna. A entrada predefinida utiliza o nome do servidor, por exemplo Contoso-cert. Pode editá-la sempre que necessário como, por exemplo, para configurar um URL para o cluster ou um balanceador de carga que sirva o cluster. Também pode seleccionar HTTP ou HTTPS. Para mais informações sobre a forma de configurar o URL de um cluster, consulte a secção **Notas** no fim desta lista de procedimentos. Após o aprovisionamento, pode configurar nas páginas Web de administração um URL de cluster externo para ser utilizado pelos clientes que se encontrem fora da rede interna.

5.  Na área **Protecção da chave privada e pré-inscrição**, seleccione o mecanismo de protecção da chave privada do servidor escolhendo uma destas opções:

    -   **Utilizar a protecção predefinida de chave privada por meio de software**. Se seleccionar esta opção, a chave privada é armazenada na base de dados de configuração do RMS. Deve escolher uma palavra-passe segura para encriptar a chave na base de dados.

    | ![](images/Cc747563.Important(WS.10).gif)Importante                                                                                                                                                                                                                                                                                                                                                                                                                                      |
    |-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Guarde essa palavra-passe num arquivo seguro para referência futura. Guarde uma cópia de segurança da base de dados de configuração (também protegida por esta palavra-passe) no arquivo seguro. Isto proporciona uma forma de restaurar o RMS no caso de a base de dados do SQL Server ficar danificada. Se, por qualquer razão, alterar a palavra-passe, faça uma nova cópia de segurança da base de dados de configuração que está protegida por essa palavra-passe e, em seguida, guarde ambas no arquivo seguro. |

    -   **Utilizar um fornecedor de serviço criptográfico (CSP)**. Para utilizar um CSP ou um módulo de segurança por hardware (HSM), desmarque a caixa de verificação **Utilizar a protecção predefinida de chave privada por meio de software**. Na lista **Seleccione o fornecedor de serviço criptográfico**, seleccione o CSP ou o HSM que tem instalado.

    | ![](images/Cc747563.note(WS.10).gif)Nota                                           |
    |-----------------------------------------------------------------------------------------------------------------|
    | O RMS requer um fornecedor RSA (Rivest-Shamir-Adleman); só esses fornecedores estão incluídos na lista de CSPs. |

    | ![](images/Cc747563.note(WS.10).gif)Nota                                                                                                                                                                                                                                                                              |
    |----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | É recomendável que utilize a protecção predefinida de chave privada por meio de software ou a de HSM. Se utilizar outro CSP baseado em software, certifique-se de que possui práticas organizacionais de gestão de chaves (tais como procedimentos de cópias de segurança e de restauro) apropriadas para esse CSP, antes de o utilizar com o RMS. |

6.  Este passo só é aplicado se tiver seleccionado um CSP. Para especificar o par de chaves de servidor a ser utilizado, proceda de uma das seguintes formas:

    -   Para uma nova instalação, seleccione **Criar um novo par de chaves públicas/privadas**.
    -   Se estiver a recuperar ou a actualizar um servidor existente do RMS, seleccione **Utilizar um par de chaves públicas/privadas existente**. Em Contentor de chaves existentes, clique em **Procurar** e, em seguida, seleccione o contentor de chaves para o par de chaves do servidor.

    | ![](images/Cc747563.note(WS.10).gif)Nota                               |
    |-----------------------------------------------------------------------------------------------------|
    | Os Microsoft Base, Enhanced, e Strong CSPs partilham a mesma localização de armazenamento da chave. |

    | ![](images/Cc747563.note(WS.10).gif)Nota                                                                                                                                                                                                                                                              |
    |------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Se não utilizar um par de chaves existente ao restaurar ou actualizar um servidor do RMS existente, é necessário limpar todos os armazenamentos de licenças (licenças de utilização e certificados de conta eliminados) de todos os clientes do RMS e terão de obter novas licenças a partir do servidor para consumir o conteúdo. |

7.  Em **Nome do certificado de licenciador de servidores**, especifique o nome a ser utilizado dentro do certificado de licenciador de servidores. Por predefinição, esse é o nome do servidor.

8.  Se a sua organização utiliza um servidor proxy para ligar à Internet, seleccione a caixa de verificação **Este computador utiliza um servidor proxy para se ligar à Internet** e escreva o endereço e a porta do servidor proxy.

    Se o servidor proxy requerer a autenticação, seleccione o tipo de autenticação e especifique um nome de utilizador e uma palavra-passe que possam ser autenticados pelo servidor proxy. Se estiver a utilizar a autenticação integrada do Windows, também deve especificar um domínio.

9.  Clique em **Submeter**.

    O serviço de pré-inscrição do RMS gera um par de chaves pública/privada para o servidor de licenciamentos e assina a chave pública com a chave privada do servidor de certificações de raiz. Também cria um certificado de licenciador de servidores para o servidor de licenciamentos. O serviço envia, depois, esses itens para a base de dados de configuração dentro de poucos minutos.

    | ![](images/Cc747563.Important(WS.10).gif)Importante                                                                                                                                                                                                                                                                                                                                                                                            |
    |-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Se aparecerem mensagens de erro, não feche a página. Em vez disso, corrija os erros, utilize IISReset na linha de comandos para parar e reiniciar o IIS, volte à página anterior, volte a introduzir as informações de aprovisionamento e, em seguida, clique novamente em **Submeter**. Se receber um erro "Tempo limite do pedido esgotado", feche a janela, verifique se o sistema satisfaz os requisitos mínimos de hardware e tente aprovisionar novamente o servidor. |

Para mais instruções sobre o aprovisionamento de outros servidores de licenciamento e como adicioná-los a um cluster, consulte [Para Adicionar um Servidor a um Cluster](https://technet.microsoft.com/db635238-5528-4bec-9cc6-8244e2b3d733) posteriormente nesta secção.
