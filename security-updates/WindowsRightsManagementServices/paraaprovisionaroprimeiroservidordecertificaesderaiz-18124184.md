---
TOCTitle: Para Aprovisionar o Primeiro Servidor de Certificações de Raiz
Title: Para Aprovisionar o Primeiro Servidor de Certificações de Raiz
ms:assetid: 'debc42f3-74ff-4c99-b7a4-4921fccdabc2'
ms:contentKeyID: 18124184
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc747768(v=WS.10)'
---

Para Aprovisionar o Primeiro Servidor de Certificações de Raiz
==============================================================

Para efectuar este procedimento, tem de iniciar sessão localmente no Web site Administração com uma conta de utilizador de domínio que seja membro do grupo Administradores no computador a que está a aceder. Os membros do grupo de administradores de domínio também podem efectuar este procedimento. Se estiver a utilizar uma base de dados remota do SQL Server, esta conta também deve ter a função de criadores de base de dados no SQL Server. Como uma boa prática de segurança, considere a utilização do comando **Executar como** para efectuar este procedimento.

Para abrir a página **Administração Global**, clique em **Iniciar**, aponte para **Todos os programas**, aponte para **Windows RMS** e clique em **Administração do Windows RMS**.

Em cada servidor, só pode aprovisionar o RMS num único Web site. Se desejar aprovisionar o RMS num Web site diferente do predefinido, utilize o Gestor de Serviços de Informação Internet para adicionar o Web site antes de iniciar este processo de aprovisionamento. Se o Web site que pretende aprovisionar não aparecer na lista de Web sites, feche a página **Administração Global**, adicione o Web site e, depois, inicie novamente o processo de aprovisionamento.

Se estiver a implementar o RMS num ambiente em que o nível funcional de domínio do Active Directory utiliza o modo nativo do Microsoft Windows 2000, o Windows RMS poderá não conseguir ler o atributo **memberOf** nos objectos do Active Directory quando tentar expandir os membros do grupo. Para permitir que o RMS leia o atributo **memberOf**, a conta de serviço do RMS deve utilizar uma conta de domínio que seja membro do grupo de Acesso compatível com versões anteriores ao Windows 2000 (incorporado) existente na floresta.

Se escrever um URL personalizado para o cluster, não se esqueça de o registar no seu sistema de nomes de domínios (DNS) e confirmar se está a funcionar. Se esta for uma implementação activada pela Internet, verifique se o URL está disponível a partir tanto da Internet como de dentro da sua organização. Deve especificar HTTPS para o URL do cluster caso tenha activado o SSL para os ficheiros de serviços Web.

Aprovisionar o Primeiro Servidor de Certificações de Raiz
---------------------------------------------------------

#### Para Aprovisionar o Primeiro Servidor de Certificações de Raiz

1.  Depois de instalar o RMS num servidor destinado a ser o primeiro servidor de certificações de raiz numa floresta do Active Directory, abra a página **Administração Global**.

2.  No Web site em que pretende aprovisionar o RMS, clique em **Aprovisionar o RMS neste Web site**. Pode seleccionar o Web site predefinido ou outro Web site que tenha criado nos Serviços de Informação Internet (IIS) para esse fim.

    | ![](images/Cc747768.Warning(WS.10).gif)Aviso                                                                                                                                                                               |
    |---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Não é suportada a execução de outros Web sites ou serviços no mesmo servidor do RMS. Se tal ocorresse, poderiam ser executados vários serviços e aplicações sob a mesma conta do RMS, o que poderia expor as chaves privadas a operações sem garantias. |

3.  Na área **Base de dados de configuração**, a opção predefinida é a de criar a base de dados de configuração no servidor local. Pode utilizar um servidor de bases de dados como o SQL Server™ 2000 com o SP3 ou o Microsoft SQL Server 2000 Desktop Engine (MSDE) para uma base de dados local. Se estiver a utilizar uma base de dados remota, ou se estiver a utilizar o servidor de bases de dados no servidor local, mas a instância do servidor das bases de dados tiver um nome diferente deste servidor, seleccione **Base de dados remota** e introduza o nome do servidor de bases de dados.

    | ![](images/Cc747768.Important(WS.10).gif)Importante                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
    |---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | É recomendável utilizar o Microsoft SQL Server Desktop Engine para suportar bases de dados do RMS apenas em ambientes de teste, visto que o Microsoft SQL Server Desktop Engine não suporta interfaces de rede. Além disso, os termos de utilização do Microsoft SQL Server Desktop Engine especificam que não é possível utilizar ferramentas de cliente de SQL Server para manipular bases de dados do Microsoft SQL Server Desktop Engine. Com esta restrição não é possível ver informações relativas ao registo nem alterar dados armazenados na base de dados de configuração.  |

4.  Na área **Conta de serviço do RMS**, especifique a conta de serviço do RMS sob a qual o RMS será executado para a maior parte das operações normais. Para a instalação de um único servidor, pode especificar a conta de sistema local ou uma conta de domínio. Para todas as outras instalações, tem de especificar uma conta de domínio. Para uma conta de domínio, proporcione o nome da conta sob a forma *nome\_domínio*\\*nome\_utilizador* e a palavra-passe.

    | ![](images/Cc747768.Warning(WS.10).gif)Aviso                                                                                                                                                                                                                                                                                                                                                                                                                                              |
    |------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | A conta de sistema local tem acesso a quase todos os recursos do sistema operativo e, por conseguinte, tem sérias implicações sobre a segurança. Sempre que possível, procure evitar a utilização da conta de Sistema Local como conta de serviço do RMS. Como alternativa, crie uma conta de utilizador de domínio especial para utilizar como conta de serviço do RMS e não lhe conceda permissões especiais. A conta de serviço do RMS não pode ser a mesma conta de domínio que foi utilizada para instalar o RMS. |

    | ![](images/Cc747768.Important(WS.10).gif)Importante                                                                                                                                                                                                                                       |
    |------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Por questões de segurança, é recomendável criar uma conta especial de utilizador de domínio para utilizar como conta de serviço do RMS e à qual não serão concedidas permissões especiais. A conta de serviço do RMS não pode ser a mesma conta de domínio que foi utilizada para instalar o RMS com o Service Pack 1. |

5.  Na área **URL do cluster**, indique o URL do servidor ou cluster que será utilizado para os clientes na rede interna. A entrada predefinida utiliza o nome do servidor, por exemplo Contoso-cert. Pode editá-la sempre que necessário como, por exemplo, para configurar um URL para o cluster ou um balanceador de carga que sirva o cluster. Também pode seleccionar HTTP ou HTTPS. Para mais informações sobre a forma de configurar o URL de um cluster, consulte a secção **Notas** no fim desta lista de procedimentos. Após o aprovisionamento, pode configurar nas páginas Web de administração um URL de cluster externo para ser utilizado pelos clientes que se encontrem fora da rede interna.

6.  Na área **Protecção da chave privada e inscrição**, seleccione o mecanismo de protecção da chave privada do servidor escolhendo uma destas opções:

    -   **Utilizar a protecção predefinida de chave privada por meio de software**. Se seleccionar esta opção, a chave privada é armazenada na base de dados de configuração do RMS. Deve escolher uma palavra-passe segura para encriptar a chave na base de dados.

    | ![](images/Cc747768.Important(WS.10).gif)Importante                                                                                                                                                                                                                                                                                                                                                                                                                                      |
    |-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Guarde essa palavra-passe num arquivo seguro para referência futura. Guarde uma cópia de segurança da base de dados de configuração (também protegida por esta palavra-passe) no arquivo seguro. Isto proporciona uma forma de restaurar o RMS no caso de a base de dados do SQL Server ficar danificada. Se, por qualquer razão, alterar a palavra-passe, faça uma nova cópia de segurança da base de dados de configuração que está protegida por essa palavra-passe e, em seguida, guarde ambas no arquivo seguro. |

    -   **Utilizar um fornecedor de serviço criptográfico (CSP)**. Para utilizar um CSP ou um módulo de segurança por hardware (HSM), desmarque a caixa de verificação **Utilizar a protecção predefinida de chave privada por meio de software**. Na lista **Seleccione o fornecedor de serviço criptográfico**, seleccione o CSP ou o HSM que tem instalado.

    | ![](images/Cc747768.note(WS.10).gif)Nota                                           |
    |-----------------------------------------------------------------------------------------------------------------|
    | O RMS requer um fornecedor RSA (Rivest-Shamir-Adleman); só esses fornecedores estão incluídos na lista de CSPs. |

    | ![](images/Cc747768.note(WS.10).gif)Nota                                                                                                                                                                                                                                                                              |
    |----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | É recomendável que utilize a protecção predefinida de chave privada por meio de software ou a de HSM. Se utilizar outro CSP baseado em software, certifique-se de que possui práticas organizacionais de gestão de chaves (tais como procedimentos de cópias de segurança e de restauro) apropriadas para esse CSP, antes de o utilizar com o RMS. |

7.  Este passo só é aplicado se tiver seleccionado um CSP. Para especificar o par de chaves de servidor a ser utilizado, proceda de uma das seguintes formas:

    -   Para uma nova instalação, seleccione **Criar um novo par de chaves públicas/privadas**.
    -   Se estiver a recuperar ou a actualizar um servidor existente do RMS, seleccione **Utilizar um par de chaves públicas/privadas existente**. Em **Contentor de chaves existentes**, clique em **Procurar** e, em seguida, seleccione o contentor de chaves para o par de chaves do servidor.

    | ![](images/Cc747768.note(WS.10).gif)Nota                               |
    |-----------------------------------------------------------------------------------------------------|
    | Os Microsoft Base, Enhanced, e Strong CSPs partilham a mesma localização de armazenamento da chave. |

    | ![](images/Cc747768.note(WS.10).gif)Nota                                                                                                                                                                                                                                                              |
    |------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Se não utilizar um par de chaves existente ao restaurar ou actualizar um servidor do RMS existente, é necessário limpar todos os armazenamentos de licenças (licenças de utilização e certificados de conta eliminados) de todos os clientes do RMS e terão de obter novas licenças a partir do servidor para consumir o conteúdo. |

8.  Em **Ligação à Internet do Servidor** especifique se deseja ligar este servidor à Internet para obter um certificado de licenciador de servidores.

    -   Seleccione **Online** para ligar imediatamente ao Serviço de Inscrição da Microsoft e obter um certificado de licenciador de servidores durante o processo de aprovisionamento.
    -   Seleccione **Offline** se o servidor do RMS não tiver uma ligação à Internet ou se desejar obter o certificado de licenciador de servidores manualmente e importá-lo para o servidor do RMS depois de concluir o processo de aprovisionamento.

9.  Em **Nome do certificado de licenciador de servidores**, especifique o nome a ser utilizado dentro do certificado de licenciador de servidores. Por predefinição, esse é o nome do servidor.

10. Se a sua organização utiliza um servidor proxy para ligar à Internet, seleccione a caixa de verificação **Este computador utiliza um servidor proxy para se ligar à Internet** e escreva o endereço e a porta do servidor proxy.

    Se o servidor proxy requerer a autenticação, seleccione o tipo de autenticação e especifique um nome de utilizador e uma palavra-passe que possam ser autenticados pelo servidor proxy. Se estiver a utilizar a autenticação integrada do Windows, também deve especificar um domínio.

    | ![](images/Cc747768.note(WS.10).gif)Nota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
    |------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Esta definição pode ser modificada após o aprovisionamento a partir da página **Definições de segurança** do Web site Administração do RMS. No entanto, essa página não está disponível até o servidor estar inscrito no Serviço de Inscrição da Microsoft. Se a sua organização necessitar que utilize um servidor proxy para efectuar a ligação à Internet e não configurar um servidor proxy porque seleccionou **Offline** para a **Ligação à Internet do Servidor**, não poderá alterar as definições do processo de inscrição ou do servidor proxy até ter concluído o processo de inscrição manual ou o reaprovisionamento do RMS |

11. Em **Contacto administrativo**, escreva o endereço de correio electrónico do administrador a ser contactado caso ocorram problemas com o aprovisionamento de outros servidores. Após o aprovisionamento, pode alterar este endereço de correio electrónico.

12. Na área **Revogação**, seleccione se pretende ou não permitir que uma outra entidade possa revogar o certificado de licenciador de servidores deste servidor. Se seleccionar esta opção, escreva o caminho e o nome do ficheiro da chave pública da outra entidade.

13. Clique em **Submeter**.

    Clicando em **Submeter**, aprovisiona o serviço. Se seleccionar a inscrição online, também é possível efectuar o processo de inscrição para o servidor de certificações de raiz. Neste processo, o RMS gera um par de chaves pública/privada e envia a chave pública para o Serviço de Inscrição da Microsoft. O Serviço de Inscrição da Microsoft cria um certificado licenciador de servidores e devolve-o à base de dados de configuração dentro de minutos. Se estiver a utilizar a inscrição offline, deve concluir a tarefa descrita em "[Para Inscrever Manualmente um Servidor de certificações de Raiz](https://technet.microsoft.com/aecdebb5-b28b-4b58-937a-392bb6ce9643)" posteriormente nesta secção antes de configurar o servidor do RMS.

    | ![](images/Cc747768.note(WS.10).gif)Nota                                                                                                                                                                                                                                                                        |
    |----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Este servidor só poderá ser utilizado depois de o ponto de ligação do serviço (SCP) do RMS ter sido registado no Active Directory. Siga os passos descritos em "[Para Registar um Ponto de Ligação do Serviço](https://technet.microsoft.com/630cc3c3-9ed9-4423-8874-cbaceb43b353)" posteriormente nesta secção para concluir este processo. |

Para mais instruções sobre o aprovisionamento de outros servidores de certificações de raiz e como adicioná-los a um cluster, consulte "[Para Adicionar um Servidor a um Cluster](https://technet.microsoft.com/db635238-5528-4bec-9cc6-8244e2b3d733)" posteriormente nesta secção.
