---
TOCTitle: Determinar a Topologia do RMS
Title: Determinar a Topologia do RMS
ms:assetid: 'bf516f7d-b3a1-4e7f-971f-bfab1db41812'
ms:contentKeyID: 18124143
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc747651(v=WS.10)'
---

Determinar a Topologia do RMS
=============================

Na topologia básica do RMS, o servidor ou o cluster de certificações do RMS de cada floresta do Active Directory fornece todos os serviços do RMS para uma organização. Esta topologia do RMS funciona bem em organizações grandes e pequenas. Numa topologia distribuída do RMS, um ou mais servidores de licenciamento (por vezes denominados servidores de licenciamento departamental) podem fornecer alguns ou todos os serviços de licenciamento a utilizadores e grupos específicos da organização. Embora o servidor (ou cluster) de certificações de raiz continue a fornecer serviços de certificação de contas e de proxy de activação para toda a organização, a topologia distribuída do RMS foi estruturada para organizações com necessidades específicas de licenciamento que pretendem manter o controlo do RMS num segmento.

Apesar de existirem apenas duas topologias básicas para o RMS, os componentes das topologias podem ser muito diferentes. Para definir os componentes mais adequados à organização e criar a topologia correcta para a implementação do RMS, tem de:

-   Avaliar os requisitos e objectivos organizacionais.
-   Definir a forma como a gestão de direitos vai ser utilizada.
-   Analisar os padrões de tráfego projectados e as cargas para implementação de um nível de serviço apropriado.

Definir a topologia e tomar as decisões necessárias à implementação da estrutura constitui um processo interactivo e contínuo durante o planeamento da implementação do RMS.

Este tópico trata de:

-   [Identificar os Componentes Principais](https://technet.microsoft.com/c9ec225b-0e51-42f5-aff6-0aecb62e3b27)
-   [Estabelecer os Objectivos das Topologias](https://technet.microsoft.com/8275a04d-3e5b-40b0-be9d-2f31b7aeca6b)
-   [Definir o Âmbito da Implementação do RMS](https://technet.microsoft.com/4b5fe1be-643e-47c4-bf9b-50d1e97108fb)
-   [Avaliar os Requisitos de Dimensionamento](https://technet.microsoft.com/89f0138c-946d-47d7-a286-041d4d9606a8)
-   [Fornecer Redundância e Balanceamento de Carga](https://technet.microsoft.com/162d547c-78a7-4848-b43e-58e481832af2)
-   [Avaliar Requisitos de Migração](https://technet.microsoft.com/cec07f45-dc52-4004-860b-5cc33e5fc209)
-   [Planear a Infra-estrutura de Servidores de Bases de Dados](https://technet.microsoft.com/b12354bd-3143-4d1f-b5aa-450c4550653c)
-   [Planear a Implementação nas Florestas](https://technet.microsoft.com/2dfb40b7-95b1-4362-b32e-72867544b705)
-   [Planear os Utilizadores Externos do RMS](https://technet.microsoft.com/107e1338-4dcf-4ed5-a49d-e875cc883db1)
-   [Planear uma Topologia Básica do RMS](https://technet.microsoft.com/fec3201e-201f-4faf-910e-fa44132af83d)
-   [Planear uma Topologia Distribuída do RMS](https://technet.microsoft.com/8773a1e0-6ac3-41f5-9866-5890cef08d04)
