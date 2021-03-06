---
TOCTitle: Optimizar o Desempenho
Title: Optimizar o Desempenho
ms:assetid: '24dc9ca4-652b-41a6-9a99-95fdeca9120b'
ms:contentKeyID: 18123961
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc720220(v=WS.10)'
---

Optimizar o Desempenho
======================

Os tópicos desta secção contêm informações acerca da optimização do desempenho da implementação do RMS.

Optimizar o Desempenho dos Serviços de Directório
-------------------------------------------------

Pode controlar os contadores de desempenho dos serviços de directório que estão incluídos no RMS. Se necessário, o desempenho pode ser optimizado modificando as definições do registo que controlam os atributos da cache do Active Directory.

As definições do registo controlam os seguintes atributos da cache do Active Directory:

-   Número máximo de principais em cache
-   Período de validade das informações em cache para os principais
-   Número máximo de grupos em cache
-   Período de validade das informações em cache para os grupos
-   Número máximo de entradas de membros do grupo
-   Período de validade das informações em cache para os membros dos grupos

Em geral, quanto mais longo é o período de validade das informações em cache, ou quanto maior for o número de entradas em cache, tanto mais rapidamente o RMS pode responder a pedidos que requeiram a obtenção de informações dos serviços de directório. Se as informações estiverem guardadas na cache do Active Directory, não é necessário ir ao Active Directory efectuar pesquisas. Reduz-se assim o tempo de resposta ao pedido.

A desvantagem de guardar mais informações na cache do Active Directory reside no facto de se utilizar mais memória do sistema. Uma outra questão a considerar quando as definições do registo são configuradas diz respeito ao facto de, quanto maior é o período de validade especificado para um item, maiores as probabilidades de alguns dos resultados devolvidos pela cache do Active Directory serem inválidos. Isto pode acontecer enquanto as informações que são alteradas no Active Directory não se reflectem na cache do Active Directory. Se o Active Directory for alterado com frequência, pode ser necessário especificar um período de validade mais curto para as informações em cache; um período que reflicta essa mesma frequência.

Os contadores de desempenho dos serviços de directório são descritos em “[RMS: Contadores de Desempenho do DirectoryServices](https://technet.microsoft.com/37afea1d-f320-4040-96d8-57c0b45e6d46)" posteriormente nesta secção. Para obter as instruções de utilização, consulte "[Utilizar Contadores de Desempenho](https://technet.microsoft.com/096c3b17-c082-46c4-939c-4373af0c9dec)" anteriormente nesta secção. Os contadores a controlar são os "acertos" contra as "falhas". O RMS tem de efectuar uma pesquisa do Active Directory para cada falha.

Para mais informações sobre as definições dos registos e instruções para as modificar, consulte "[Alterar as Definições da Cache do Active Directory](https://technet.microsoft.com/8789a7a5-2065-4fae-9104-e0a70f1f2fb6)" posteriormente nesta secção.

Optimizar as Definições do Grupo de Ligações do Active Directory
----------------------------------------------------------------

Para melhorar o desempenho do sistema, é possível adicionar e modificar as chaves do registo que controlam as definições do grupo de ligação LDAP do Active Directory. A configuração das chaves de registo é descrita em “[Modificar as Definições do Registo do Grupo de Ligações](https://technet.microsoft.com/c61d91db-a1ad-4ca5-a492-015da629afbc)” posteriormente nesta secção.

O RMS foi concebido para optimizar as ligações LDAP. Estabelece uma ligação para cada catálogo global do Active Directory, e cada ligação pode servir vários threads. Para proporcionar robustez, mantém um grupo de ligações para servir pedidos. Para evitar colocar uma grande carga num só catálogo global, o RMS utiliza um algoritmo que permite distribuir pedidos executando o balanceamento de cargas entre os catálogos globais que se encontram na lista de catálogo globais a consultar. Trata automaticamente erros LDAP e reencaminha pedidos para catálogos globais diferentes, conforme seja necessário.

O RMS cria uma lista de catálogos globais que vão ser consultados utilizando o algoritmo de Identificação de Topologia. Pode especificar o número mínimo e máximo de catálogos globais disponíveis que têm de ser localizados pela Identificação de Topologia antes de os serviços do RMS poderem começar. A identificação de Topologia descobre em primeiro lugar os catálogos globais que se encontram no local actual. Se depois forem necessários catálogos globais adicionais, irá fazer procuras noutros locais. É também especificado o número máximo de ligações que podem ficar indisponíveis antes de o RMS deixar de aceitar pedidos. Se, mais tarde, um ou mais catálogos globais da lista de consultas fica indisponível, a Identificação de Topologia começa a procurar catálogos globais substitutos para serem adicionados à lista de consulta.

Em alternativa, pode criar uma lista dos catálogos globais que o RMS deve utilizar. Neste caso, a Identificação de Topologia não procura catálogos globais para serem adicionados à lista de consulta.

Pode também configurar definições para o modo como o RMS executa o balanceamento de cargas entre os catálogos globais. Pode especificar até que ponto são importantes, relativamente umas às outras, as seguintes considerações quando decidir se envia ou não um determinado pedido para um determinado catálogo global:

-   **Round robin (WtRoundRobin)**. Este parâmetro especifica a importância relativa do balanceamento de carga em que é utilizada a lógica round-robin. A definição de ponderação predefinida é 1, o que significa que esta é a consideração menos importante que o servidor deve ter em consideração quando selecciona um catálogo global.
-   **Número de threads durante a ligação (WtThreadCount)**. Este parâmetro especifica a importância relativa do número de threads que são atribuídos a uma ligação. A definição de ponderação predefinida é 100, o que significa que é 100 vezes mais importante que o número de threads de um catálogo global seja baixo para uma ligação a ser seleccionada do que efectuar o balanceamento da carga utilizando a lógica round-robin.
-   **Ligação lenta (WtSlow)**. Este parâmetro especifica a importância relativa de uma ligação lenta. A definição de ponderação predefinida é 1000, o que significa que é 10 vezes mais importante que uma ligação com um catálogo global seja lenta para ser seleccionada do que o número de threads ser baixo.
