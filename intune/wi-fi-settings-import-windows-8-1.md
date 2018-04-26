---
title: Importar configurações de Wi-Fi para Windows 8.1 e posterior
titleSuffix: Microsoft Intune
description: Como importar configurações de Wi-Fi do Windows para um perfil de Wi-Fi do Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 157416738e4607d5022f1c3c7ed8251a8e32fe3e
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2018
---
# <a name="import-wi-fi-settings-for-windows-81-and-later-devices-in-microsoft-intune"></a>Importar configurações de Wi-Fi para dispositivos Windows 8.1 e posteriores no Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Para dispositivos que executam Windows 8.1 e Windows 10 para área de trabalho ou dispositivos móveis, ou Windows Holographic for Business, você pode importar um perfil de configuração de Wi-Fi que já foi exportado em um arquivo.

## <a name="export-wi-fi-settings-from-a-windows-device"></a>Exportar configurações Wi-Fi de um dispositivo do Windows

No Windows, você pode usar o utilitário **netsh wlan** para exportar um perfil de Wi-Fi existente para um arquivo XML legível pelo Intune. A chave deve ser exportada em texto sem formatação para usar o perfil com êxito.

Em um computador Windows que já tenha o perfil WiFi necessário instalado, siga estas etapas:

1. Crie uma pasta local para os perfis Wi-Fi exportados, como **c:\WiFi**.
2. Abra um Prompt de Comando como Administrador.
3. Execute o comando `netsh wlan show profiles` e tome nota do nome do perfil que você deseja exportar. Neste exemplo, o nome do perfil é **WiFiName**.
4. Execute o comando `netsh wlan export profile name="ProfileName" folder=c:\Wifi`. Isso cria um arquivo de perfil Wi-Fi chamado **"Wi-Fi-WiFiName.xml"** na pasta de destino.

## <a name="import-the-wi-fi-settings-into-intune"></a>Importar as configurações de Wi-Fi para o Intune

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
3. Selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
4. Insira um **Nome** e uma **Descrição** para o perfil de restrição de dispositivo.

    > [!IMPORTANT]
    > - O nome **precisa** ser o mesmo que o atributo name no XML do perfil de Wi-Fi. Caso contrário, falhará.
    > - Se você estiver exportando um perfil de Wi-Fi que inclua uma chave pré-compartilhada, você **precisará** adicionar `key=clear` ao comando. Por exemplo, insira: `netsh wlan export profile name="ProfileName" key=clear folder=c:\Wifi`
    > - Usar uma chave pré-compartilhada com Windows 10 faz com que um erro de correção apareça no Intune. Quando isso acontece, o perfil de Wi-Fi é adequadamente atribuído ao dispositivo, e o perfil funciona conforme o esperado.
    > - Se você exportar um perfil de Wi-Fi que inclua uma chave pré-compartilhada, o arquivo deverá estar protegido. A chave está em texto sem formatação, portanto, é sua responsabilidade protegê-la.

5. Em **plataforma**, selecione **Windows 8.1 e posterior**.
6. Em **Tipo de perfil**, selecione **Importação de Wi-Fi**.
7. Defina as seguintes configurações:
  - **Nome da conexão**: insira um nome para a conexão Wi-Fi. Esse nome é exibido aos usuários finais ao procurarem por redes Wi-Fi disponíveis.
  - **Perfil XML**: selecione o botão Procurar para selecionar o arquivo XML que contém as configurações de perfil Wi-Fi que você deseja importar para o Intune.
  - **Conteúdo do arquivo**: mostra o código XML para o perfil de configuração selecionado.
8. Quando terminar, escolha **OK** e, em seguida, **Criar** o perfil.

O perfil é criado e está na lista de perfis.
