---
title: "Configurar o Microsoft Intune para logon único de dispositivo iOS"
titlesuffix: 
description: "Saiba como configurar o Microsoft Intune para logon único de dispositivo iOS."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/2/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3bb7c3bdffb19e26f2f2178c1750d1ef31a02556
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2018
---
# <a name="configure-microsoft-intune-for-ios-device-single-sign-on"></a>Configurar o Microsoft Intune para logon único de dispositivo iOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A maioria dos aplicativos LOB (Linha de Negócios) exigem algum nível de autenticação de usuário para dar suporte à segurança. Em muitos casos, isso requer que o usuário digite as mesmas credenciais várias vezes, o que pode ser frustrante. Para melhorar a experiência do usuário, os desenvolvedores podem criar aplicativos que usam o logon único, reduzindo o número de vezes que um usuário deve fornecer credenciais.

Para aproveitar o Logon Único do dispositivo iOS, você deve ter as seguintes condições:

- Um aplicativo codificado para procurar o repositório de credenciais do usuário no conteúdo de logon único no dispositivo iOS.
- Intune configurado para logon único de dispositivo iOS.

## <a name="to-configure-intune-for-ios-device-single-sign-on"></a>Para configurar o Intune para logon único de dispositivo iOS


1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, escolha **Configuração do dispositivo**.
4. No painel **Configuração do dispositivo**, na seção **Gerenciar**, escolha **Perfis**.
5. No painel de perfis, escolha **Criar perfil**.
6. Forneça um nome e uma descrição e defina as seguintes configurações:
   - **Plataforma**: escolha **iOS**.
   - **Tipo de perfil**: escolha **recursos de dispositivo**.
7. No painel **Recursos do dispositivo**, escolha **Logon Único**.

   ![Painel de logon único](./media/sso-blade.png)

8. Use a seguinte tabela de resumo para ajudá-lo a preencher os campos no painel **Logon Único**. Para obter detalhes, consulte as seções após a tabela.

   |Campo  |Anotações|
   |---------|---------|
   |**Atributo de nome de usuário do AAD**|O atributo que o Intune procura para cada usuário no AAD e preenche o respectivo campo (como o UPN) antes de gerar a carga XML que é instalada no dispositivo.|
   |**Território**|A parte do domínio da URL.|
   |**Prefixos de URL que usarão Logon Único**|Quaisquer URLs em sua organização que exijam autenticação de logon único usuário|
   |**Os aplicativos que usarão o Logon Único**|Aplicativos no dispositivo do usuário final que usam o conteúdo de logon único.|
   |**Certificado de renovação de credencial**|Se estiver usando certificados para autenticação, selecione o certificado SCEP ou PFX implantado para o usuário como o certificado de autenticação.|

As seções a seguir dão mais detalhes sobre cada um dos campos de logon único.

### <a name="username-attribute-from-aad-and-realm"></a>Atributo de nome de usuário do AAD e do Realm

- Se **Nome do Princípio do Usuário** estiver selecionado para esse campo, ele é analisada da seguinte maneira:

   ![Atributo de nome de usuário](media/User-name-attribute.png)

   Você também tem a opção de substituir o realm pelo texto digitado na caixa de texto **Realm**.

   Por exemplo, Contoso pode ter várias sub-regiões, como América do Norte, Europa e Ásia. Ela talvez queira que os usuários na Ásia usem o conteúdo SSO e o aplicativo exige o UPN no formato *username@asia.contoso.com*. Nesse caso, se você selecionar **Nome do Princípio do Usuário**, por padrão, o realm para cada usuário será obtido do AAD, podendo ser apenas *contoso.com*. Especialmente para os usuários na Ásia, você pode criar esse conteúdo e substituir o realm pelo valor *asia.contoso.com*. Agora o UPN do usuário final se torna *username@asia.contoso.com* e não *username@contoso.com*.

- Se você selecionar **ID do Dispositivo**, o Intune selecionará automaticamente a ID do Dispositivo Intune.

   Por padrão, aplicativos precisam usar somente a ID do dispositivo. Porém, se seu aplicativo usar o realm além da ID do dispositivo, você poderá digitar o realm na caixa de texto **Realm**.

   > [!NOTE]
   > Por padrão, mantenha o realm vazio se você usar a ID do dispositivo.

### <a name="url-prefixes-that-will-use-single-sign-on"></a>Prefixos de URL que usarão Logon Único

Digite aqui qualquer URL que exista na sua organização e que exija autenticação de usuário.

Por exemplo, quando um usuário se conecta a qualquer um desses sites, o dispositivo iOS usa as credenciais de logon único e o usuário não precisa inserir credenciais adicionais. No entanto, se você tiver autenticação multifator habilitada, os usuários deverão digitar a segunda autenticação.

> [!NOTE]
> Essas URLs devem ter FQDN corretamente formatado. A Apple exige que estejam no formato `http://<yourURL.domain>`

Os padrões de correspondência de URL devem começar com um `http://` ou `https://`. Uma correspondência de cadeia de caracteres simples é executada, de modo que o prefixo URL `http://www.contoso.com/` não corresponde a `http://www.contoso.com:80/`. Com o iOS 9.0 ou posterior, no entanto, um único curinga \* pode ser usado para especificar todos os valores correspondentes. Por exemplo, `http://*.contoso.com/` corresponde tanto a `http://store.contoso.com/` quanto a `http://www.contoso.com`.
Os padrões `http://.com` e `https://.com` correspondem a todas as URLs HTTP e HTTPS, respectivamente.

### <a name="apps-that-will-use-single-sign-on"></a>Os aplicativos que usarão o Logon Único

Indique quais aplicativos no dispositivo do usuário final podem usar o Logon Único no conteúdo.

A matriz `AppIdentifierMatches` deve conter cadeias de caracteres que correspondam a IDs de pacote de aplicativo. Essas cadeias de caracteres podem ser correspondências exatas (por exemplo: `com.contoso.myapp`) ou podem especificar uma correspondência de prefixo na ID de pacote usando o caractere curinga *\. O caractere curinga deve aparecer após um caractere de ponto (.) e pode aparecer apenas uma vez, no final da cadeia de caracteres (por exemplo: `com.contoso.*`). Quando um caractere curinga for incluído, qualquer aplicativo cuja ID do pacote comece com o prefixo receberá acesso à conta.

O campo **Nome do Aplicativo** é usado para adicionar um nome amigável para ajudá-lo a identificar a ID do pacote.

### <a name="credential-renewal-certificate"></a>Certificado de renovação de credencial

Se você autenticar seus usuários finais com certificados (não senhas), use este campo para selecionar o certificado do SCEP ou PFX que é implantado para o usuário como o certificado de autenticação. Normalmente, esse é o mesmo certificado implantado para o usuário para outros perfis, como VPN, Wi-Fi ou Email.

## <a name="next-steps"></a>Próximas etapas

Para informações de configuração do recurso de dispositivos adicionais, consulte [Como definir configurações de recurso do dispositivo no Microsoft Intune](device-features-configure.md).
