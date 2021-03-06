---
TOCTitle: Definir Políticas de Revogação
Title: Definir Políticas de Revogação
ms:assetid: 'e2fffe9f-def7-439b-a8aa-43f8a065813d'
ms:contentKeyID: 18124195
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc747782(v=WS.10)'
---

Definir Políticas de Revogação
==============================

A definição de políticas de revogação numa organização requer consideração e planeamento cuidadosos porque, apesar de a revogação da implementação proporcionar maior segurança para o conteúdo protegido, pode afectar a capacidade do utilizador para consumir conteúdos. As políticas de revogação relacionadas com a implementação do RMS poderão ser definidas a partir do Web site de administração.

Revogação de Terceiros.
-----------------------

Como é o Serviço de Inscrição da Microsoft que emite o certificado de licenciador de servidores do servidor de certificações de raiz da implementação do seu RMS, a Microsoft poderá revogar o seu certificado do licenciador de servidores. No entanto, a Microsoft apenas revogará um certificado de licenciador de servidores se tal lhe for ordenado por um tribunal.

Além do Serviço de Inscrição da Microsoft, pode especificar uma outra entidade com capacidade para revogar o certificado de licenciador de servidores do servidor do RMS. Esta terceira entidade tanto poderá ser uma entidade externa como um par de chave pública que seja gerado pelo administrador em nome da organização. A chave privada da entidade que é especificada poderá assinar uma lista de revogações que revogue o certificado do licenciador de servidores. Essa terceira entidade é especificada pela sua chave pública durante o aprovisionamento do RMS. Os modelos de políticas de direitos do seu servidor também poderão ser configurados para permitir a outras entidades a revogação de conteúdos, manifestos de aplicações, licenças e certificados que sejam emitidos pela instalação do RMS. Para mais informações, consulte "[Criar e Modificar Modelos de Política de Direitos](https://technet.microsoft.com/6014176f-ef71-4d29-b3e3-da129c18563d)" posteriormente nesta secção.

| ![](images/Cc747782.Important(WS.10).gif)Importante                                                                                                                                     |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Se decidir gerar o seu próprio par de chaves para que ele seja utilizado na revogação do certificado do licenciador de servidores do servidor de certificações de raiz, não se esqueça de o guardar em local seguro. |

A revogação de um certificado de licenciador de servidores é uma decisão importante, porque todos os certificados e licenças que são emitidos pela instalação do RMS se tornam inválidos quando esse certificado é revogado. Para mais informações sobre a revogação de certificados de licenciador de servidores, consulte "[Revogar Certificados de Licenciador de Servidores](https://technet.microsoft.com/8020861d-d196-4431-8282-044675ef5616)" anteriormente nesta secção.

Considerar a Forma como as Listas de Revogações Entram em Vigor
---------------------------------------------------------------

A partir do momento em que é necessária uma revogação para uma determinada peça de conteúdo protegido, todas as listas de revogações que se encontram registadas em computadores cliente serão utilizadas e entrarão em vigor no caso de ser detectada uma condição especificada. Por isso, tenha o maior cuidado quando implementar revogações, porque desta operação resultará o registo de listas de revogações em computadores cliente, podendo essas listas ser aplicadas de forma mais alargada do que aquilo que se pretende. Para mais informações sobre a configuração desta opção, consulte "[Criar e Modificar Modelos de Política de Direitos](https://technet.microsoft.com/6014176f-ef71-4d29-b3e3-da129c18563d)" anteriormente nesta secção.

Equilíbrio entre Segurança e Facilidade de Utilização
-----------------------------------------------------

Quando se especifica a política de revogações num modelo de política de direitos, convém ponderar a necessidade de proporcionar maior segurança para documentos contra a hipótese de os utilizadores poderem encontrar problemas quando estão a consumir o conteúdo, conforme se descreve no seguinte exemplo.

Como parte da configuração de uma lista de revogações num modelo de política de direitos, especifique também um intervalo de actualização para a lista de revogações. Para consumir conteúdo publicado utilizando esse modelo de política de direitos, é necessário que exista uma lista de revogações no computador do utilizador, não podendo a lista ser mais antiga do que o intervalo de actualização especificado. Por exemplo, se o intervalo de actualização for 10, a lista de revogações tem de ter sido criada nos últimos 10 dias. Se não existir uma lista de revogações no computador cliente, ou se a lista tiver uma data de criação anterior ao intervalo de actualização, a aplicação activada pelo RMS obtém a lista de revogações mais recente a partir do local especificado na licença de utilização. No entanto, um utilizador que não esteja ligado à rede poderá não ser capaz de obter uma lista de revogações corrente, e por isso pode não conseguir consumir o conteúdo.

As sugestões que apresentamos a seguir poderão ajudar a resolver este problema:

-   Ter cuidado ao especificar o intervalo de actualização de uma lista de revogações, e tomar medidas para assegurar que está sempre prontamente acessível para os utilizadores uma lista de revogações actualizada.
-   Manter listas de revogações em URLs que sejam acessíveis tanto a partir do interior como do exterior da rede da empresa.
-   Utilizar o SMS (Systems Management Server) da Microsoft® ou um mecanismo semelhante para distribuir cópias actualizadas de listas de revogações a cada computador cliente a intervalos definidos, por exemplo, todas as noites.
-   Requerer revogações apenas para os tipos mais sensíveis de documentos.
