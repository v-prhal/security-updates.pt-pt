---
TOCTitle: Remover a Protecção de Conteúdo Oferecida pelo RMS
Title: Remover a Protecção de Conteúdo Oferecida pelo RMS
ms:assetid: 'c30361e3-50d2-4474-a87d-d38de502cf9e'
ms:contentKeyID: 18124167
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc747658(v=WS.10)'
---

Remover a Protecção de Conteúdo Oferecida pelo RMS
==================================================

Decida antecipadamente quais os ficheiros que necessitam de ser recuperados, por quem e quando para que todas as informações importantes sejam preservadas quando o processo de desactivação terminar. Quando a protecção do RMS tiver sido removida de todos os ficheiros necessários protegidos pelo RMS, pode remover o servidor da infra-estrutura.

O processo de remoção da protecção de conteúdo oferecida pelo RMS é o seguinte:

1.  O utilizador deve remover todas as licenças de utilização existentes no computador. Isto força o cliente do RMS a aceder ao servidor para adquirir uma licença que lhe permite abrir o conteúdo. As licenças de utilização são armazenadas na pasta %USERPROFILE%\\Definições Locais\\Application Data\\Microsoft\\DRM no computador cliente e têm um prefixo EUL no nome de ficheiro.
2.  Um utilizador com acesso ao servidor de desactivação tenta abrir um ficheiro protegido pelo RMS.
3.  A aplicação liga-se ao servidor de desactivação e recebe a chave de conteúdo.
4.  O conteúdo é desencriptado e pode ser editado, guardado, reencaminhado ou impresso.
5.  O utilizador guarda o conteúdo sem protecção do RMS. Todos os utilizadores podem agora abrir o conteúdo sem terem de ligar ao servidor do RMS.
