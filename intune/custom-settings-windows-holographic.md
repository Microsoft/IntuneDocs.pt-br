---
title: Configurações personalizadas do Microsoft Intune para dispositivos Windows Holographic for Business
titlesuffix: ''
description: Saiba mais sobre as configurações que você pode usar em um perfil personalizado do Windows Holographic for Business.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.article: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d5cdba24c10b90756d9a2b9f08fd7d4dcd727303
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-windows-holographic-for-business"></a>Configurações de dispositivo personalizadas do Microsoft Intune para dispositivos que executam o Windows Holographic for Business

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 Use o perfil **personalizado** do Microsoft Intune para Windows Holographic for Business para implantar configurações de OMA-URI (Open Mobile Alliance Uniform Resource Identifier), que podem ser usadas para controlar recursos em dispositivos. O Windows Holographic for Business disponibiliza muitas configurações de CSPs (Provedores de Serviço de Configuração). Para uma visão geral sobre CSP, consulte [Introdução aos CSPs (Provedores de Serviço de Configuração) para profissionais de TI](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers). Para CSPs específicos compatíveis com o Windows Holographic, consulte [CSPs compatíveis com o Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).

Se você estiver procurando uma configuração específica, lembre-se que o [perfil de restrição de dispositivo do Windows Holographic for Business](device-restrictions-windows-holographic.md) contém várias configurações internas e não necessita que você especifique valores personalizados.

1. Use as instruções em [Como definir configurações personalizadas do dispositivo no Microsoft Intune](custom-settings-configure.md) para começar.
2. Em **Criar Perfil**, escolha **Configurações** para adicionar uma ou mais configurações OMA-URI.
3. Em **Configurações personalizadas de OMA-URI**, clique em **Adicionar** para adicionar um novo valor. Você também pode clicar em **Exportar** para criar uma lista de todos os valores configurados em um arquivo de valores separados por vírgulas (.csv).
4. Para cada configuração de OMA-URI que você desejar adicionar, insira as informações a seguir:
    - **Nome da configuração** - insira um nome exclusivo para a configuração de OMA-URI para ajudar a identificá-la na lista de configurações.
    - **Descrição da configuração** - opcionalmente, insira uma descrição para a configuração.
    - **Tipo de dados** - escolha dentre:
        - **Cadeia de caracteres**
        - **Cadeia de caracteres (XML)**
        - **Data e hora**
        - **Inteiro**
        - **Ponto flutuante**
        - **Booliano**
    - **OMA-URI (com distinção entre maiúsculas e minúsculas)** - especifique o OMA-URI para o qual você deseja fornecer uma configuração.
    - **Valor** - especifique o valor para associar ao OMA-URI que você inseriu.
1. Quando terminar, volte para **Criar Perfil** e clique em **Criar**.
O perfil é criado e exibido na lista de perfis.

## <a name="recommended-custom-settings"></a>Configurações personalizadas recomendadas

As configurações a seguir são úteis para dispositivos que executam o Windows Holographic for Business:


|Nome da configuração|OMA-URI|Tipo de dados  |
|---------|---------|---------|
|[AllowFastReconnect](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-allowfastreconnect)|./Vendor/MSFT/Policy/Config/Authentication/AllowFastReconnect|Inteiro<br>0 – não permitido<br>1 – permitido (padrão)|
|[AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)|./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Inteiro<br>0 – não permitido<br>1 – permitido (padrão)|
|[AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)|./Vendor/MSFT/Policy/Config/Update/AllowUpdateService|Inteiro<br>0 – serviço de atualização não é permitido <br>1 – serviço de atualização é permitido (padrão).|
|[UpdateServiceURL](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)|./Vendor/MSFT/Policy/Config/Update/UpdateServiceUrl|Cadeia de caracteres<br>URL – o dispositivo verifica atualizações no servidor do WSUS na URL especificada.<br>Não configurado – o dispositivo verifica se há atualizações no Microsoft Update.|
|[RequireUpdatesApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)|./Vendor/MSFT/Policy/Config/Update/RequireUpdateApproval|Inteiro<br>0 – não configurado. O dispositivo instala todas as atualizações aplicáveis.<br>1 – o dispositivo instala somente as atualizações que são aplicáveis e que estão na lista de Atualizações Aprovadas. Defina essa política como 1 se o TI deseja controlar a implantação de atualizações em dispositivos, como quando há necessidade de testes antes da implantação.|
|[ApprovedUpdates](https://docs.microsoft.com/windows/client-management/mdm/update-csp)|./Vendor/MSFT/Update/ApprovedUpdates<br><br>**Importante**<br>Você deve ler e aceitar os Termos de Licença atualizados em nome dos usuários finais. Se não fizer isso, ocasionará uma violação de obrigações contratuais ou legais.|Nó para aprovações de atualização e aceitação de Termos de Licença em nome do usuário final.|
[ApplicationLaunchRestrictions](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp)|./Vendor/MSFT/AppLocker/ApplicationLaunchRestrictions/*Grouping*/*ApplicationType*/Policy<br><br>**Importante**<br>O artigo AppLocker CSP usa exemplos com XML de escape. Para definir as configurações com perfis personalizados do Intune, você deve usar XML sem formatação.|Cadeia de caracteres<br>Para obter mais informações, consulte o artigo [AppLocker CSP](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp).

## <a name="how-to-find-the-policies-you-can-configure"></a>Como localizar as políticas que você pode configurar

Você pode encontrar uma lista completa de todos os CSPs (Provedores de Serviço de Configuração) compatíveis com o Windows Holographic em [CSPs compatíveis com o Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens). Nem todas as configurações são compatíveis com todas as versões do Windows Holographic. A tabela no artigo do Windows informa quais versões são compatíveis com cada CSP.

Além disso, o Intune não é compatível com todas as configurações listadas no artigo. Para saber se o Intune é compatível com a configuração desejada, abra o artigo dessa configuração. Cada página de configuração mostra a operação de suporte correspondente. Para trabalhar com o Intune, a configuração deve oferecer suporte às operações **Adicionar** ou **Substituir**.
