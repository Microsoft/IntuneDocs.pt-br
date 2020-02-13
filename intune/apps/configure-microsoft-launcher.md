---
title: Configurar o Microsoft Launcher para Android Enterprise com Intune
titleSuffix: ''
description: Use as políticas de configuração do Intune com o Microsoft Launcher.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: priyar
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b0145a17434d8b309806f468bf066d54ae117144
ms.sourcegitcommit: 1aaff35fddb3d06458d739968d28971fed0bb2ba
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "77155353"
---
# <a name="configure-microsoft-launcher"></a>Configurar o Microsoft Launcher

O Microsoft Launcher é um aplicativo Android que permite que os usuários personalizem seu telefone, se organizem em qualquer lugar e transfiram o trabalho do telefone para o PC. 

Nos dispositivos totalmente gerenciados do Android Enterprise, o Launcher permite que os administradores de TI da empresa personalizem as telas iniciais dos dispositivos gerenciados selecionando o papel de parede, os aplicativos e as posições dos ícones. Isso padroniza a aparência de todos os dispositivos Android gerenciados em diferentes dispositivos OEM e versões do sistema. 

## <a name="how-to-configure-the-microsoft-launcher-app"></a>Como configurar o aplicativo Microsoft Launcher 

Navegue até o [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431) e selecione **Aplicativos** > **Políticas de configuração de aplicativo**. Adicione uma política de configuração para **Dispositivos gerenciados** em execução no **Android** e escolha **Microsoft Launcher** como o aplicativo associado. Clique em **Definições de configuração** para definir as diferentes configurações do Microsoft Launcher disponíveis. 

## <a name="choosing-a-configuration-settings-format"></a>Como escolher um formato de definições de configuração 

Há dois métodos que você pode usar para definir as configurações do Microsoft Launcher: 

- O **Designer de configuração** permite que você defina as configurações com uma interface do usuário fácil de usar, que permite ativar e desativar recursos e definir valores. Nesse método, há algumas chaves de configuração desabilitadas com o tipo de valor BundleArray. Essas chaves de configuração só podem ser configuradas inserindo dados JSON. 

- **Dados JSON** permitem que você defina todas as chaves de configuração possíveis usando um script JSON. 

Se adicionar propriedades com o **Designer de Configuração**, você poderá converter automaticamente essas propriedades em JSON, selecionando **Inserir dados JSON** na lista suspensa **Formato das configurações** como mostrado abaixo.

   ![Formato de definições de configuração - Usar o designer de configuração](./media/configure-microsoft-launcher/configure-microsoft-launcher-01.png)

## <a name="using-configuration-designer"></a>Como usar o designer de configuração

O designer de configuração permite que você selecione configurações preenchidas previamente e seus valores associados.

   ![Formato de definições de configuração - Inserir editor de JSON](./media/configure-microsoft-launcher/configure-microsoft-launcher-02.png)

A tabela a seguir lista as chaves de configuração, tipos de valor, valores padrão e descrições disponíveis no Microsoft Launcher. A descrição fornece o comportamento esperado do dispositivo com base nos valores selecionados. Chaves de configuração que estão desabilitadas no designer de configuração não estão listadas na tabela.

|    Chave de Configuração    |    Tipo de valor    |    Valor padrão    |    Descrição     |
|---------------------------------------------------|------------------|---------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Tipo de registro    |    Cadeia de caracteres     |    Padrão    |    Permite que você defina o tipo de registro ao qual essa política deve se aplicar. Atualmente, o valor **Padrão** refere-se a **CorporateOwnedBuisnessOnly**. Atualmente, não há outros tipos de registro com suporte.        Nome de chave JSON: management_mode_key        |
|    Alteração do usuário da Ordem do aplicativo da tela inicial   Permitida    |    Booliano    |    verdadeiro    |    Permite especificar se a configuração **Ordem do aplicativo na tela inicial** pode ser alterada pelo usuário final.<ul><li>Se definida como **Verdadeira**, a ordem do aplicativo definida na política será aplicada apenas para a implantação inicial. Posteriormente, a política não será aplicada para respeitar as alterações que o usuário possa ter feito.</li><li>Se definida como **Falsa**, a ordem do aplicativo será imposta a cada sincronização.</li></ul><br>**Observação:** A ordem do Aplicativo na Tela Inicial pode ser configurada apenas por meio do editor JSON.<br><br>Nome da chave JSON:<br>`com.microsoft.launcher.HomeScreen.AppOrder.UserChangeAllowed`    |
|    Definir tamanho da grade    |    Cadeia de caracteres    |    Auto    |    Permite que você defina o tamanho da grade para que aplicativos sejam posicionados na tela inicial. Você pode definir o número de linhas e colunas de aplicativo para definir o tamanho da grade no seguinte formato: `columns;rows`. Se você definir o tamanho da grade, o número máximo de aplicativos que serão mostrados em uma linha na tela inicial será o número de linhas definidas e o número máximo de aplicativos que serão mostrados em uma coluna na tela inicial o número de colunas que você definiu.<br><br>        Nome da chave JSON:<br>`com.microsoft.launcher.HomeScreen.GridSize`    |
|    Definir papel de parede do dispositivo    |    Cadeia de caracteres    |    Null    |    Permite que você defina um papel de parede de sua preferência, inserindo a URL da imagem que você deseja definir como um papel de parede.<br><br>Nome da chave JSON:<br>`com.microsoft.launcher.Wallpaper.URL`    |
|    Alteração do usuário Definir papel de parede do dispositivo   Permitida    |    Bool    |    verdadeiro    |    Permite especificar se a configuração Definir papel de parede do dispositivo pode ser alterada pelo usuário final.<ul><li>Se definida como **Verdadeira**, o papel de parede na política será aplicado apenas para a implantação inicial. Posteriormente, a política não será aplicada para respeitar as alterações que o usuário possa ter feito.</li><li>Se definida como **Falsa**, o papel de parede será aplicado a cada sincronização.</li></ul><br>Nome da chave JSON:<br>`com.microsoft.launcher.Wallpaper.URL.UserChangeAllowed`        |
|    Habilitar feed    |    Booliano    |    verdadeiro    |    Permite ativar o feed do iniciador no dispositivo quando o usuário desliza para a direita na tela inicial.<ul><li>Se definida como **Verdadeira**, o feed será habilitado.</li><li>Se definida como **Falsa**, o feed será desabilitado.</li></ul><br>Nome da chave JSON:<br>`com.microsoft.launcher.Feed.Enabled`    |
|    Alteração do usuário Habilitar feed Permitida    |    Booliano    |    verdadeiro    |     Permite especificar se a configuração **Habilitar feed** pode ser alterada pelo usuário final.<ul><li>Se definida como **Verdadeira**, o feed será aplicado apenas para a implantação inicial. Posteriormente, a política não será aplicada para respeitar as alterações que o usuário possa ter feito.</li><li>Se definida como **Falsa**, o feed será imposto a cada sincronização.</li></ul><br>Nome da chave JSON:`com.microsoft.launcher.Feed.Enabled.UserChangeAllowed`    |

## <a name="enter-json-data"></a>Inserir dados JSON

Digite os dados JSON para definir todas as configurações disponíveis para o Microsoft Launcher, bem como as configurações desabilitadas no **Designer de Configuração**, como mostrado abaixo.

   ![Designer de configuração - dados JSON](./media/configure-microsoft-launcher/configure-microsoft-launcher-03.png)

Além da lista de definições configuráveis listadas na tabela do Designer de configuração (acima), a tabela a seguir fornece as chaves de configuração que você só pode configurar por meio de dados JSON.

|    Chave de Configuração    |    Tipo de valor    |    Valor padrão    |    Descrição     |
|----------------------------------------------------------------------------------------------------|-------------------|-------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Definir aplicativos para a lista de permissões<br>Chave JSON:`com.microsoft.launcher.HomeScreen.Applications`    |    BundleArray    | Consulte: [Definir aplicativos para a lista de permissões](configure-microsoft-launcher.md#set-allow-listed-applications)</sup>    |    Permite definir o conjunto de aplicativos visíveis na tela inicial entre os aplicativos instalados no dispositivo. Você pode definir os aplicativos inserindo o nome do pacote dos aplicativos que você deseja tornar visíveis, por exemplo, `com.android.settings` torna as configurações acessíveis na tela inicial. Os aplicativos da lista de permissões nesta seção já devem estar instalados no dispositivo para que fiquem visíveis na tela inicial.<p>Propriedades:<ul><li>**Pacote:** O nome do pacote de aplicativos</li><li>**Classe:** A atividade do aplicativo, específica de uma determinada página de aplicativo. A página do aplicativo padrão é usada se esse valor estiver vazio.</li></ul>      |
|    Ordem do aplicativo na tela inicial<br>Chave JSON: `com.microsoft.launcher.HomeScreen.AppOrder`    |    BundleArray    |    Consulte: [Ordem do aplicativo na tela inicial](configure-microsoft-launcher.md#home-screen-app-order)      |    Permite especificar a ordem do aplicativo na tela inicial.<p>Propriedades:<br><ul><li>**Tipo:** O único tipo com suporte é `application`.</li><li>**Posição:** O slot do ícone do aplicativo na tela inicial. Tem início na posição 1 no canto superior esquerdo e vai da esquerda para a direita, de cima para baixo.</li><li>**Pacote:** O nome do pacote de aplicativos.</li><li>**Classe:** A atividade do aplicativo, específica de uma determinada página de aplicativo. A página do aplicativo padrão será usada se esse valor estiver vazio.</li></ul>    |

### <a name="set-allow-listed-applications"></a>Definir aplicativos para a lista de permissões

```JSON
{
    "key": "com.microsoft.launcher.HomeScreen.Applications",
    "valueBundleArray": 
    [
        {
            "managedProperty": [
                {
                    "key": "package",
                    "valueString": ""
                },
                {
                    "key": "class",
                    "valueString": ""
                }
            ]
        }
    ]
}
```

### <a name="home-screen-app-order"></a>Ordem do aplicativo na tela inicial

```JSON
{
    "key": "com.microsoft.launcher.HomeScreen.AppOrder",
    "valueBundleArray": 
    [
        {
            "managedProperty": [
                {
                    "key": "type",
                    "valueString": "application"
                },
                {
                    "key": "position",
                    "valueInteger": 0
                },
                {
                    "key": "package",
                    "valueString": ""
                },
                {
                    "key": "class",
                    "valueString": ""
                }
            ]
        }
    ]
}
```

Este é um exemplo de script JSON com todas as chaves de configuração disponíveis incluídas:

```JSON
{
    "kind": "androidenterprise#managedConfiguration", 
    "productId": "app:com.microsoft.launcher", 
    "managedProperty": [
        {
            "key": "management_mode_key", 
            "valueString": "Default"
        }, 
        {
            "key": "com.microsoft.launcher.Feed.Enable.UserChangeAllowed", 
            "valueBool": false
        }, 
        {
            "key": "com.microsoft.launcher.Feed.Enable", 
            "valueBool": true
        }, 
        {
            "key": "com.microsoft.launcher.Wallpaper.Url.UserChangeAllowed", 
            "valueBool": false
        }, 
        {
            "key": "com.microsoft.launcher.Wallpaper.Url", 
            "valueBool": "http://www.contoso.com/wallpaper.png"
        }, 
        {
            "key": "com.microsoft.launcher.HomeScreen.GridSize", 
            "valueString": "5;5"
        }, 
        {
            "key": "com.microsoft.launcher.HomeScreen.Applications", 
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "package", 
                            "valueString": "com.ups.mobile.android"
                        }, 
                        {
                            "key": "class", 
                            "valueString": ""
                        }
                    ]
                }, 
                {
                    "managedProperty": [
                        {
                            "key": "package", 
                            "valueString": "com.microsoft.teams"
                        }, 
                        {
                            "key": "class", 
                            "valueString": ""
                        }
                    ]
                }, 
                {
                    "managedProperty": [
                        {
                            "key": "package", 
                            "valueString": "com.microsoft.bing"
                        }, 
                        {
                            "key": "class", 
                            "valueString": ""
                        }
                    ]
                }
            ]
        }, 
        {
            "key": "com.microsoft.launcher.HomeScreen.AppOrder.UserChangeAllowed", 
            "valueBool": false
        }, 
        {
            "key": "com.microsoft.launcher.HomeScreen.AppOrder", 
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "type", 
                            "valueString": "application"
                        }, 
                        {
                            "key": "position", 
                            "valueInteger": 17
                        }, 
                        {
                            "key": "package", 
                            "valueString": "com.ups.mobile.android"
                        }, 
                        {
                            "key": "class", 
                            "valueString": ""
                        }
                    ]
                }, 
                {
                    "managedProperty": [
                        {
                            "key": "type", 
                            "valueString": "application"
                        }, 
                        {
                            "key": "position", 
                            "valueInteger": 18
                        }, 
                        {
                            "key": "package", 
                            "valueString": "com.microsoft.teams"
                        }, 
                        {
                            "key": "class", 
                            "valueString": ""
                        }
                    ]
                }, 
                {
                    "managedProperty": [
                        {
                            "key": "type", 
                            "valueString": "application"
                        }, 
                        {
                            "key": "position", 
                            "valueInteger": 19
                        }, 
                        {
                            "key": "package", 
                            "valueString": "com.microsoft.bing"
                        }, 
                        {
                            "key": "class", 
                            "valueString": ""
                        }
                    ]
                }
            ]
        }
    ]
}
```

## <a name="next-steps"></a>Próximas etapas

- Para saber mais sobre dispositivos Android Enterprise totalmente gerenciados, confira [Configurar o registro do Intune para dispositivos Android Enterprise totalmente gerenciados](../enrollment/android-fully-managed-enroll.md).
