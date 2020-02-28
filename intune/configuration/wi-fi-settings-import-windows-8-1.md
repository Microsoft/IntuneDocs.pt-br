---
title: Importar configurações de Wi-Fi para dispositivos Windows no Microsoft Intune – Azure | Microsoft Docs
description: Exporte as configurações de Wi-Fi de um dispositivo Windows como um arquivo XML usando netsh wlan. Em seguida, importe esse arquivo no Intune para criar um perfil de Wi-Fi para dispositivos que executam o Windows 8.1, o Windows 10 e o Windows Holographic for Business.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/18/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f79ccdc71ddbfa3f25daef629515fb612de01852
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "75207002"
---
# <a name="import-wi-fi-settings-for-windows-devices-in-intune"></a>Importar configurações de Wi-Fi para dispositivos Windows no Intune

Para dispositivos que executam o Windows, você pode importar um perfil de configuração de Wi-Fi que já foi exportado para um arquivo. **Para dispositivos com Windows 10 e posteriores, você também pode [criar um perfil de Wi-Fi](wi-fi-settings-windows.md) diretamente no Intune**.

Aplica-se a:  
- Windows 8.1 e posterior
- Windows 10 e posterior
- Windows 10 Desktop ou Mobile
- Windows Holographic for Business

## <a name="export-wi-fi-settings-from-a-windows-device"></a>Exportar configurações Wi-Fi de um dispositivo do Windows

No Windows, use `netsh wlan` para exportar um perfil de Wi-Fi existente para um arquivo XML legível pelo Intune. A chave deve ser exportada em texto sem formatação para usar o perfil com êxito.

Em um computador Windows que já tenha o perfil WiFi necessário instalado, siga estas etapas:

1. Crie uma pasta local para os perfis Wi-Fi exportados, como **c:\WiFi**.
2. Abra um Prompt de Comando como Administrador.
3. Execute o comando `netsh wlan show profiles`. Observe o nome do perfil que você deseja exportar. Neste exemplo, o nome do perfil é **WiFiName**.
4. Execute o comando `netsh wlan export profile name="ProfileName" folder=c:\Wifi`. Esse comando cria um arquivo de perfil Wi-Fi chamado **Wi-Fi-NomeWiFi.xml** na pasta de destino.

## <a name="import-the-wi-fi-settings-into-intune"></a>Importar as configurações de Wi-Fi para o Intune

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Dispositivos** > **Perfis de configuração** > **Criar perfil**.
3. Insira as seguintes configurações:

    - **Nome**: Insira um nome descritivo para o perfil. O nome **precisa** ser o mesmo que o atributo name no XML do perfil de Wi-Fi. Caso contrário, falhará.
    - **Descrição**: insira uma descrição que proporciona uma visão geral da configuração e demais detalhes importantes.
    - **Plataforma**: selecione **Windows 8.1 e posterior**.
    - **Tipo de perfil**: selecione **Importação por Wi-Fi**.

    > [!IMPORTANT]
    > - Se você estiver exportando um perfil de Wi-Fi que inclua uma chave pré-compartilhada, você **precisará** adicionar `key=clear` ao comando. Por exemplo, insira: `netsh wlan export profile name="ProfileName" key=clear folder=c:\Wifi`
    > - Usar uma chave pré-compartilhada com Windows 10 faz com que um erro de correção seja exibido no Intune. Quando isso acontece, o perfil de Wi-Fi é adequadamente atribuído ao dispositivo, e o perfil funciona conforme o esperado.
    > - Se você exportar um perfil de Wi-Fi que inclua uma chave pré-compartilhada, o arquivo deverá estar protegido. A chave está em texto sem formatação, portanto, é sua responsabilidade protegê-la.

4. Insira as seguintes configurações:

    - **Nome da conexão**: insira um nome para esta conexão Wi-Fi. Esse nome é mostrado aos usuários quando eles navegam por redes Wi-Fi disponíveis.
    - **Perfil XML**: selecione o botão Procurar e escolha o arquivo XML que contém as configurações de perfil de Wi-Fi que você deseja importar.
    - **Conteúdo de arquivo**: mostra o código XML para o perfil de configuração selecionado.

5. Selecione **OK** para salvar suas alterações.
6. Quando terminar, escolha **OK** > **Criar** para criar o perfil do Intune. Após a conclusão, seu perfil será mostrado na lista **Dispositivos – Perfis de configuração**.

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada. Em seguida, [atribua o perfil](../device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).

Veja a [Visão geral das configurações de Wi-Fi](wi-fi-settings-configure.md), incluindo outras plataformas disponíveis.
