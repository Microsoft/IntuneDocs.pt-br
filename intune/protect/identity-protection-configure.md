---
title: Usar um PIN para entrar em dispositivos Windows 10 usando o Microsoft Intune – Azure | Microsoft Docs
description: Use o Windows Hello para Empresas para permitir que os usuários entrem em seus dispositivos usando um PIN, uma impressão digital ou outros recursos. Crie um perfil de configuração de proteção de identidade nos dispositivos do Intune para Windows 10 com essas configurações e atribua o perfil a grupos de usuários e grupos de dispositivos.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/29/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 333b94bf3226c99ed50c4b433f4b477814b8e4bb
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72509539"
---
# <a name="use-windows-hello-for-business-on-windows-10-devices-with-microsoft-intune"></a>Usar o Windows Hello para Empresas em dispositivos Windows 10 com o Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

O Windows Hello para Empresas é um método para entrar em dispositivos Windows que substitui senhas, cartões inteligentes e cartões inteligentes virtuais. O Intune inclui configurações internas para que os administradores possam configurar e usar o Windows Hello para Empresas. Por exemplo, você pode usar essas configurações para:

- Habilitar o Windows Hello para Empresas para dispositivos e usuários
- Definir requisitos de PIN do dispositivo, incluindo um comprimento mínimo ou máximo do PIN
- Permitir gestos, como uma impressão digital, que os usuários podem usar (ou não) para entrar em dispositivos

Esse recurso aplica-se a dispositivos que executam:

- Windows 10 e posterior
- Windows 10 Mobile
- Windows Holographic for Business

O Intune usa "perfis de configuração" para criar e personalizar essas configurações de acordo com as necessidades de sua organização. Depois de adicionar esses recursos em um perfil, envie ou implante essas configurações para grupos de usuários e dispositivos em sua organização.

Este artigo mostra como criar um perfil de configuração de dispositivos. Para obter uma lista de todas as configurações e o que elas fazem, confira [Configurações do dispositivo Windows 10 para habilitar o Windows Hello para Empresas](identity-protection-windows-settings.md).

## <a name="create-the-device-profile"></a>Criar o perfil de dispositivo

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
3. Insira as seguintes propriedades:

    - **Nome**: insira um nome descritivo para o novo perfil.
    - **Descrição**: Insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
    - **Plataforma**: Selecione **Windows 10 e posterior**. O Windows Hello para Empresas apenas é compatível com dispositivos que executam o Windows 10 e posteriores.
    - **Tipo de perfil**: Escolha **Proteção de identidade**.
    - **Configure o Windows Hello para Empresas**: Escolha como você deseja configurar o Windows Hello para Empresas. Suas opções:

        - **Não configurado**: [Provisiona o Windows Hello para Empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-how-it-works-provisioning) no dispositivo. Durante a atribuição de perfis de proteção de identidade somente a usuários, o contexto do dispositivo padrão é **Não configurado**.
        - **Desabilitado**: Se você não quiser usar o Windows Hello para Empresas, escolha esta opção. Essa opção desabilita o Windows Hello para Empresas para todos os usuários.
        - **Habilitado**: Escolha essa opção para [provisionar](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-how-it-works-provisioning) e definir as configurações do Windows Hello para Empresas no Intune. Insira as configurações que você deseja definir. Para obter uma lista de todas as configurações e o que elas fazem, confira:

            - [Configurações do dispositivo Windows 10 para habilitar o Windows Hello para Empresas](identity-protection-windows-settings.md)

4. Quando terminar, selecione **OK** > **Criar** para salvar suas alterações.

O perfil é criado e exibido na lista de perfis. Em seguida, [atribua](../configuration/device-profile-assign.md) esse perfil a grupos de usuários e dispositivos para atender às suas necessidades.

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/identity-protection-configure/disable-android-camera.png)

-->

## <a name="next-steps"></a>Próximas etapas

- Veja uma lista de todas [as configurações e o que elas fazem](identity-protection-windows-settings.md).
- [Atribuir o perfil](../configuration/device-profile-assign.md) e [monitorar seu status](../configuration/device-profile-monitor.md).
