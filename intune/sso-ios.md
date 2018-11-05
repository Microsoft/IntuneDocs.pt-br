---
title: Adicionar logon único para dispositivos iOS no Microsoft Intune – Azure | Microsoft Docs
description: No Microsoft Intune, crie, configure, permita ou habilite dispositivos iOS a usar SSO (logon único), em vez de senha, para autenticação aos recursos e dados de sua organização. Para usar SSO, crie um perfil de configuração do dispositivo e insira o UPN, a ID do dispositivo, seus aplicativos e um certificado para autenticar o usuário e o dispositivo.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d1add113222c2aa7eaea10679c329e877b1a136f
ms.sourcegitcommit: 437eaf364c3b8a38d294397310c770ea4d8a8015
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2018
ms.locfileid: "49992002"
---
# <a name="use-single-sign-on-ios-device-in-microsoft-intune"></a>Usar um dispositivo iOS de logon único no Microsoft Intune

A maioria dos aplicativos LOB (Linha de Negócios) exigem algum nível de autenticação de usuário para dar suporte à segurança. Em muitos casos, essa autenticação exige que o usuário insira as mesmas credenciais várias vezes, o que é frustrante. Para melhorar a experiência do usuário, os desenvolvedores podem criar aplicativos que usam o SSO (logon único), reduzindo o número de vezes que um usuário deve inserir credenciais.

Este artigo mostra como ativar o logon único para dispositivos iOS usando um perfil de configuração do dispositivo no Microsoft Intune.

## <a name="before-you-begin"></a>Antes de começar

Você deve ter um aplicativo codificado para procurar o repositório de credenciais do usuário no conteúdo de logon único no dispositivo iOS.

## <a name="create-the-sso-profile"></a>Criar o perfil de SSO

1. No [Portal do Azure](https://portal.azure.com), selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
2. Selecione **Configuração do dispositivo** > **Perfis** > **Criar Perfil**.
3. Insira as seguintes configurações:

    - **Nome**: insira um nome para o perfil, como `ios sso profile`.
    - **Descrição**: insira uma descrição com os principais termos para ajudá-lo a localizar o perfil na lista.
    - **Plataforma**: escolha **iOS**.
    - **Tipo de perfil**: escolha **recursos de dispositivo**.

4. Escolha **Logon Único**.

    ![Painel de logon único](./media/sso-blade.png)

5. Insira as seguintes configurações: 

    - **Atributo de nome de usuário do AAD**: o Intune procura esse atributo para cada usuário no Azure AD. O Intune então preenche o respectivo campo (como o UPN) antes de gerar o conteúdo XML instalado no dispositivo. Suas opções:
    
        - **Nome UPN**: o UPN é analisado da seguinte maneira:

            ![Atributo de nome de usuário](media/User-name-attribute.png)

            Você também pode substituir o realm pelo texto inserido na caixa de texto **Realm**.

            Por exemplo, Contoso pode ter várias sub-regiões, como América do Norte, Europa e Ásia. Ela talvez queira que os usuários na Ásia usem o conteúdo SSO e o aplicativo exige o UPN no formato `username@asia.contoso.com`. Nesse caso, se você selecionar **Nome UPN**, por padrão, o realm para cada usuário será obtido do Azure AD, podendo ser *contoso.com*. Especialmente para os usuários na Ásia, você pode criar esse conteúdo e substituir o realm pelo valor *asia.contoso.com*. Agora o UPN do usuário final torna-se username@asia.contoso.com, em vez de username@contoso.com.

        - **ID do Dispositivo do Intune**: o Intune seleciona automaticamente a ID do Dispositivo Intune. 

            Por padrão, aplicativos precisam usar somente a ID do dispositivo. Porém, se o aplicativo usar o realm **e** a ID do dispositivo, você poderá digitar o realm na caixa de texto *Realm*.

            > [!NOTE]
            > Por padrão, mantenha o realm vazio se você usar a ID do dispositivo.

    - **Realm**: a parte do domínio da URL.
    
    - **Prefixos de URL que usarão Logon Único**: escolha **Adicionar** todas as URLs em sua organização que exigem autenticação de logon único de usuário. 

        Por exemplo, quando um usuário se conecta a qualquer um desses sites, o dispositivo iOS usa as credenciais de logon único. O usuário não precisa inserir credenciais adicionais. No entanto, se você tiver autenticação multifator habilitada, os usuários deverão digitar a segunda autenticação.

        > [!NOTE]
        > Essas URLs devem ter FQDN corretamente formatado. A Apple exige URLs no formato `http://<yourURL.domain>`.

        Os padrões de correspondência de URL devem começar com um `http://` ou `https://`. Uma correspondência de cadeia de caracteres simples é executada, de modo que o prefixo da URL `http://www.contoso.com/` não corresponde a `http://www.contoso.com:80/`. Com o iOS 10.0 ou posterior, no entanto, um único curinga \* pode ser usado para inserir todos os valores correspondentes. Por exemplo, `http://*.contoso.com/` corresponde tanto a `http://store.contoso.com/` quanto a `http://www.contoso.com`.

        Os padrões `http://.com` e `https://.com` correspondem a todas as URLs HTTP e HTTPS, respectivamente.
    
    - **Aplicativos que usarão o Logon Único**: escolha **Adicionar** aplicativos em dispositivos dos usuários finais que podem usar logon único. 

        A matriz `AppIdentifierMatches` deve conter cadeias de caracteres que correspondam a IDs de pacote de aplicativo. Essas cadeias de caracteres podem ser correspondências exatas (como `com.contoso.myapp`), ou inserir uma correspondência de prefixo na ID de pacote usando o caractere curinga \*. O caractere curinga deve aparecer após um caractere de ponto (.) e pode aparecer apenas uma vez, no final da cadeia de caracteres (por exemplo: `com.contoso.*`). Quando um caractere curinga for incluído, qualquer aplicativo cuja ID do pacote comece com o prefixo receberá acesso à conta.

        Use **Nome do Aplicativo** para inserir um nome amigável para ajudá-lo a identificar a ID do pacote.
    
    - **Certificado de renovação de credencial**: se estiver usando certificados para autenticação (não senhas), selecione o certificado SCEP ou PFX implantado para o usuário como o certificado de autenticação. Normalmente, esse é o mesmo certificado implantado para o usuário para outros perfis, como VPN, Wi-Fi ou Email.

6. Selecione **OK** > **OK** > **Criar** para salvar suas alterações e criar o perfil. Depois de criada, ela é mostrada na lista **Configuração do dispositivo – perfis**. 

## <a name="next-steps"></a>Próximas etapas

Para informações de configuração do recurso de dispositivos adicionais, consulte [Como definir configurações de recurso do dispositivo no Microsoft Intune](device-features-configure.md).

[Atribua esse perfil](device-profile-assign.md) aos seus dispositivos iOS.
