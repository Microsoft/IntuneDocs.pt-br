---
title: Importar configurações de Wi-Fi para dispositivos Windows no Microsoft Intune – Azure | Microsoft Docs
description: Exporte as configurações de Wi-Fi de um dispositivo Windows como um arquivo XML usando netsh wlan. Em seguida, importe esse arquivo no Intune para criar um perfil de Wi-Fi para dispositivos que executam o Windows 8.1, o Windows 10 e o Windows Holographic for Business.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/18/2018
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2ce2813702d9b2b3cb91f5531308cbb58b1f9f80
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66050604"
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
3. Execute o comando `netsh wlan show profiles` e tome nota do nome do perfil que você deseja exportar. Neste exemplo, o nome do perfil é **WiFiName**.
4. Execute o comando `netsh wlan export profile name="ProfileName" folder=c:\Wifi`. Esse comando cria um arquivo de perfil Wi-Fi chamado **Wi-Fi-NomeWiFi.xml** na pasta de destino.

## <a name="import-the-wi-fi-settings-into-intune"></a>Importar as configurações de Wi-Fi para o Intune

1. No [Portal do Azure](https://portal.azure.com), selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
2. Selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
3. Insira um **Nome** e uma **Descrição** para o perfil de restrição de dispositivo.

    > [!IMPORTANT]
    > - O nome **precisa** ser o mesmo que o atributo name no XML do perfil de Wi-Fi. Caso contrário, falhará.
    > - Se você estiver exportando um perfil de Wi-Fi que inclua uma chave pré-compartilhada, você **precisará** adicionar `key=clear` ao comando. Por exemplo, insira: `netsh wlan export profile name="ProfileName" key=clear folder=c:\Wifi`
    > - Usar uma chave pré-compartilhada com Windows 10 faz com que um erro de correção apareça no Intune. Quando isso acontece, o perfil de Wi-Fi é adequadamente atribuído ao dispositivo, e o perfil funciona conforme o esperado.
    > - Se você exportar um perfil de Wi-Fi que inclua uma chave pré-compartilhada, o arquivo deverá estar protegido. A chave está em texto sem formatação, portanto, é sua responsabilidade protegê-la.

4. Em **plataforma**, selecione **Windows 8.1 e posterior**.
5. Em **Tipo de perfil**, selecione **Importação de Wi-Fi**.
6. Defina as seguintes configurações:
    - **Nome da conexão**: insira um nome para a conexão Wi-Fi. Esse nome é exibido aos usuários finais ao procurarem por redes Wi-Fi disponíveis.
    - **Perfil XML**: selecione o botão Procurar e escolha o arquivo XML que contém as configurações de perfil de Wi-Fi que você deseja importar.
    - **Conteúdo do arquivo**: mostra o código XML para o perfil de configuração selecionado.
7. Quando terminar, selecione **OK** > **Criar** para salvar suas alterações. O perfil será criado e exibido na lista de perfis.

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada. Em seguida, [atribua esse perfil](device-profile-assign.md).

## <a name="more-resources"></a>Mais recursos

[Visão geral das configurações de Wi-Fi](wi-fi-settings-configure.md), incluindo outras plataformas disponíveis.
