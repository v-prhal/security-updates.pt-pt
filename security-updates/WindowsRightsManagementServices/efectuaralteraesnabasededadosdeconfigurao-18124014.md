---
TOCTitle: Efectuar Alterações na Base de dados de Configuração
Title: Efectuar Alterações na Base de dados de Configuração
ms:assetid: '6a7bec73-09e4-4060-b551-5990836df4bc'
ms:contentKeyID: 18124014
ms:mtpsurl: 'https://technet.microsoft.com/pt-pt/library/Cc747606(v=WS.10)'
---

Efectuar Alterações na Base de dados de Configuração
====================================================

As alterações da configuração efectuadas através do Web site de administração reflectem-se na base de dados de configuração do servidor ou cluster. É recomendável que altere as definições de configuração a partir do Web site de administração, em vez de alterar manualmente os dados na base de dados de configuração. No entanto, existem duas situações que podem exigir a alteração manual da base de dados:

-   **Mudar a base de dados para outro servidor.** Por predefinição, a base de dados de registo está instalada no mesmo servidor que a base de dados de configuração. Se decidir mudar a base de dados de registo para outro servidor, deverá modificar a base de dados de configuração de forma a referir-se à nova localização. Para mais informações sobre como mudar uma base de dados de registo, incluindo a forma de actualizar a base de dados de configuração com a nova localização, consulte "[Mudar a Localização da Base de Dados de Registo](https://technet.microsoft.com/34ea8045-dc94-422e-9601-29927cfc1534)" anteriormente nesta secção.
-   **Remover chaves de utilizador associadas a certificados de contas de direitos**. Quando remover uma conta de utilizador do Active Directory, excluir ou revogar um certificado de conta de direitos utilizando o Web site de administração, não são removidas as chaves de utilizador associadas ao certificado de conta de direitos da base de dados de configuração. É necessário remover manualmente da base de dados de configuração as chaves de utilizador inactivas, em parte por razões de segurança, mas também para facilitar o rastreio do número de licenças de acesso de cliente (CAL). Para mais informações sobre como remover as chaves de utilizador da base de dados de configuração, consulte "[Eliminar Contas de Utilizadores](https://technet.microsoft.com/bf73b141-d4d1-4807-a773-3aaff58b0db6)" anteriormente nesta secção. Para mais informações sobre o rastreio das CALs, consulte “[Rastrear Certificados de Conta](https://technet.microsoft.com/5bb0f3cf-fc44-4e60-a93f-c789d6f8a902)” anteriormente nesta secção.

Se necessitar de efectuar alterações directamente à base de dados de configuração, consulte o administrador do servidor de base de dados.
