---
TOCTitle: Manter a Base de Dados de Registo
Title: Manter a Base de Dados de Registo
ms:assetid: 'de55058b-0d1a-4997-8a45-e14678ddd13f'
ms:contentKeyID: 18124212
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc747691(v=WS.10)'
---

Manter a Base de Dados de Registo
=================================

As entradas de registo incluem também cópias de licenças emitidas para diversas operações do RMS, tais como a inscrição dos utilizadores e a atribuição de licenças de utilização. No pior cenário — no qual cada entrada de registo é uma inscrição de utilizador com êxito ou uma tentativa com êxito de aquisição de uma licença de utilização — cada entrada de registo adiciona cerca de 200 KB ao tamanho da base de dados de registo.

Por exemplo, assuma que uma mensagem de correio electrónico protegida pelo RMS foi enviada a todos os empregados de uma empresa com 50.000 utilizadores e todos eles abrem a mensagem. Se cada empregado abrisse esta mensagem de correio electrónico num período de um dia, a base de dados de registo cresceria 10 GB. É possível configurar o serviço de escuta para não registar dados XrML reais, o que reduziria o montante de informações registadas.

Considere criar scripts para arquivar informações mais antigas a partir da base de dados de registo para uma base de dados secundária. Exemplos de scripts de registo estão disponíveis no RMS Toolkit que pode ser transferido a partir do [Web site da Microsoft](http://go.microsoft.com/fwlink/?linkid=26724) (http://go.microsoft.com/fwlink/?LinkId=26724).

Variáveis que Afectam o Crescimento da Base de Dados de Registo
---------------------------------------------------------------

Calcular o tamanho de uma base de dados de registo depende do ambiente. É possível calcular diversas entradas de "arranque" no registo, incluindo:

-   Inscrição do servidor do RMS
-   Inscrição do utilizador (um pedido exclusivo para cada computador utilizado por cada utilizador)
-   Pedidos automatizados dos utilizadores para certificados de publicação offline

A maior parte das entradas da base de dados de registo após as entradas de arranque iniciais estão associadas à emissão de licenças de utilização para conteúdo protegido. Diversas condições afectam o crescimento desta base de dados:

-   Necessidade de uma nova licença sempre que um utilizador acede a conteúdo protegido. Não é o método predefinido para documentos protegidos mas sim uma definição opcional. Se optar por implementar este requisito, as bases de dados crescem mais rapidamente.
-   Número previsto de mensagens de correio electrónico protegidas enviadas a cada pessoa por dia.
-   Número previsto de utilizadores exclusivos que irão ler estas mensagens de correio electrónico protegidas.
-   Número previsto de documentos do Microsoft Office 2003 (Word, PowerPoint e Excel) produzidos por cada pessoa por dia.
-   Destinatários previstos dos documentos protegidos.

O tamanho inicial da base de dados de registo é de cerca de 1,7 MB, incluindo o pedido de um certificado efectuado pelo servidor do RMS. Sempre que um novo utilizador se inscreve, obtém um certificado de conta de direitos (RAC) e um certificado de licenciador de clientes (CLC). Estas duas acções são registadas, fazendo crescer a base de dados cerca de 0,06 MB. Sempre que um utilizador adquire com êxito uma licença para conteúdo protegido, a base de dados cresce 0,19 MB.

Para perceber como funciona este cálculo, considere uma organização com 5.000 utilizadores que implementa o RMS para todos. Cada utilizador tem um computador e a organização utiliza dois servidores do RMS. Após a implementação, cada utilizador cria em média uma mensagem de correio electrónico protegida pelo RMS por dia e envia-a para cinco utilizadores. Cada utilizador cria também um documento protegido pelo RMS durante um dia que é acedido por três outros utilizadores. A tabela seguinte calcula quanto esta actividade aumenta o tamanho da base de dados de registo.

###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Acção</th>
<th>Crescimento do Registo</th>
<th>Tamanho Acumulado do Registo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">O servidor do RMS é aprovisionado com êxito</td>
<td style="border:1px solid black;">1,7 MB</td>
<td style="border:1px solid black;">1,7 MB</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">5000 empregados inscritos (5000*0,06)</td>
<td style="border:1px solid black;">300 MB</td>
<td style="border:1px solid black;">301,7 MB</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Mensagens de correio electrónico protegidas acedidas (25000*0,19)</td>
<td style="border:1px solid black;">4.750 MB</td>
<td style="border:1px solid black;">5.051,7 MB</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Documentos protegidos acedidos (15000*0,19)</td>
<td style="border:1px solid black;">2.850 MB</td>
<td style="border:1px solid black;">7.901,7 MB</td>
</tr>
</tbody>
</table>
  
Assim, após a inscrição, a base de dados de registo tem um tamanho estático de cerca de 300 MB. No entanto, o crescimento diário deste exemplo é de 7,6 GB — próximo do limite de 8 GB da instalação predefinida da Colocação de Mensagens em Fila. Se a base de dados de registo ficar indisponível durante mais de um dia, as entradas de registo começam a ser eliminadas.
  
Controlar o Tamanho da Base de Dados de Registo  
-----------------------------------------------
  
O plano de implementação tem de incluir um método de gestão da base de dados de registo. A seguir são apresentadas as abordagens mais comuns.
  
-   **Eliminar e arquivar**  
    Este método envolve a utilização de scripts do SQL Server para arquivar informações seleccionadas na base de dados de registo para uma base de dados secundária quando as entradas de registo atingem uma determinada idade. Envolve também filtrar as informações irrelevantes das bases de dados para que o espaço não seja desperdiçado.  
-   **Limitar as informações registadas**  
    A base de dados de registo é composta por três tabelas principais. Uma delas é a **DRMS\_Log\_Filter**, que identifica o campo na tabela principal que deve ser registado quando o filtro de registo está activo.  
    As entradas de tabela activado/desactivado indicam os campos da tabela principal que são registados pelo Serviço de Escuta de Registo no servidor do RMS. Dois destes campos (relacionados com o XrML) já foram definidos como 0 para desactivarem o registo pois representam cerca de 99% do tamanho de cada linha de pedido de licença.  
    Outra tabela da base de dados **DRMS\_Config\_ServerName\_Port** denominada **DRMS\_ClusterPolicies** contém **PolicyName** de **LoggingFiltering**. **LoggingFiltering** não é activado por predefinição. Se alterar o valor de **LoggingFiltering** para 1 e reiniciar o Serviço de Escuta de Registo, o crescimento diário da base de dados do exemplo anterior diminui de 7,6 GB cada dia para 160 MB cada dia.  
-   **Mover a base de dados de registo**  
    Outra opção de gerir uma base de dados de registo em crescimento é movê-la para um servidor com mais espaço em disco. A base de dados de registo pode existir num servidor de bases de dados diferente do utilizado para a base de dados de configuração. Para mover a base de dados para um servidor diferente, siga estes passos:  
    1.  Pare o serviço de escuta de registo em cada servidor do RMS.  
    2.  Copie a base de dados (ou crie uma nova) para um servidor diferente.  
    3.  Edite a base de dados **DRMS\_Config\_ServerName\_Port** do RMS seleccionando a tabela **DRMS\_ClusterPolicies** e editando os valores de **LoggingDatabaseName** (nome do servidor da base de dados) e de **LoggingDatabaseServer** (nome da base de dados).  
    4.  Reinicie o IIS executando o IISRESET.exe a partir da linha de comandos.
