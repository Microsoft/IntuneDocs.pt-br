---
title: Configurações de restrição de dispositivo do Microsoft Intune para Windows 8.1
titleSuffix: ''
description: Conheça as definições do Intune que você pode usar para controlar as configurações e as funcionalidades do dispositivo nos dispositivos que executam o Windows Phone 8.1.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 343b15e13a944cb519451a14c299d66444b17569
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57230356"
---
# <a name="microsoft-intune-windows-phone-81-device-restriction-settings"></a>Configurações de restrição de dispositivo Windows Phone 8.1 no Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Este artigo mostra as configurações de restrições de dispositivo do Microsoft Intune que podem ser definidas para dispositivos que executam o Windows Phone 8.1.


## <a name="general"></a>Geral

-   **Câmera** – Habilita ou bloqueia a câmera do dispositivo.
-   **Copiar e colar** – Habilita ou bloqueia a funcionalidade de copiar e colar nos dispositivos.
-   **Armazenamento removível** – Permite que o dispositivo use armazenamento removível, como cartões SD.
-   **Geolocalização** – Permite que o dispositivo utilize informações de localização.
-   **Conta da Microsoft** – Habilitar ou impedir que o usuário vincule uma conta da Microsoft ao dispositivo.
-   **Captura de tela** – Permite que o usuário capture o conteúdo da tela como um arquivo de imagem.
-   **Envio de dados de diagnóstico** – Permite que o dispositivo envie informações de diagnóstico à Microsoft.
-   **Sincronizar contas de email personalizadas** – Permite que o dispositivo se conecte a contas de email não Microsoft.

## <a name="password"></a>Senha

-   **Senha** – Exige que o usuário final insira uma senha para acessar o dispositivo.
    -   **Tipo de senha exigida** – Especifica o tipo de senha que será necessária, como apenas caracteres numéricos ou alfanuméricos.
    -   **Tamanho mínimo da senha** – Especifica o número mínimo de caracteres necessários na senha.
    -   **Senhas simples** – Especifica que senhas simples, como “0000” e “1234”, podem ser usadas.
    -   **Número de falhas de entrada antes de apagar o dispositivo** – Especifica o número de vezes que uma senha incorreta pode ser inserida antes que o dispositivo seja apagado.
    -   **Máximo de minutos de inatividade para o bloqueio de tela** – Especifica o período que um dispositivo deve permanecer ocioso antes da tela ser bloqueada automaticamente.
    -   **Expiração da senha (dias)** – Especifica o número de dias antes que a senha do dispositivo precise ser alterada.
    -   **Impedir a reutilização de senhas anteriores** – Especifica quantas senhas usadas anteriormente são lembradas.
-   **Criptografia** – Exige que os dados em dispositivos móveis com suporte sejam criptografados.

## <a name="app-store"></a>Loja de aplicativos

-   **Loja de aplicativos** – Permite que os usuários se conectem à loja de aplicativos do dispositivo.

## <a name="restricted-apps"></a>Aplicativos restritos

Na lista de aplicativos restritos, você pode configurar uma das seguintes listas:

Uma lista de **Aplicativos bloqueados** – Lista os aplicativos (não gerenciados pelo Intune) que os usuários não têm permissão para instalar e executar.
Uma lista de **Aplicativos permitidos** – Lista os aplicativos que os usuários têm permissão para instalar. Aplicativos que são gerenciados pelo Intune são permitidos automaticamente.

Para configurar a lista, clique em **Adicionar**, especifique um nome de sua preferência, o editor do aplicativo (opcional) e a URL para o aplicativo na loja de aplicativos.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Como especificar a URL de um aplicativo na loja

Para especificar uma URL de aplicativo na lista de aplicativos permitidos e bloqueados, use o seguinte formato:

Na página da [Windows Phone Store](https://www.microsoft.com/store/apps/windows-phone), pesquise o aplicativo que você deseja usar.

Abra a página do aplicativo e copie a URL para a área de transferência. Agora você pode usar isso como a URL em uma lista de aplicativos permitidos ou bloqueados.

Exemplo: Procure o aplicativo Skype na loja. A URL usada é `http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51`.



### <a name="additional-options"></a>Opções adicionais

Você também pode clicar em **Importar** para popular a lista de um arquivo csv no formato <*url do aplicativo*>, <*nome do aplicativo*>, <app publisher> ou clicar em **Exportar** para criar um arquivo csv que inclui o conteúdo da lista de aplicativos restritos no mesmo formato.


## <a name="browser"></a>Navegador

-   **Navegador da Web** – Habilita ou bloqueia o navegador da Web interno em dispositivos.

## <a name="cellular-and-connectivity"></a>Rede Celular e Conectividade

-   **Wi-Fi** – Habilita ou desabilita a funcionalidade Wi-Fi do dispositivo.
-   **Compartilhamento da Internet por Wi-Fi** – Habilita o uso de compartilhamento de Internet por Wi-Fi no dispositivo.
-   **Conectar automaticamente a hotspots Wi-Fi** – Permite que o dispositivo se conecte automaticamente a hotspots Wi-Fi gratuitos e aceite automaticamente os termos de uso.
-   **Relatórios de hotspot Wi-Fi** – Envia informações sobre conexões Wi-Fi para ajudar o usuário a descobrir conexões próximas.
-   **NFC** – Habilita ou desabilita as operações que usam comunicação a curta distância em dispositivos que dão suporte a ela.
-   **Bluetooth** – Habilita ou desabilita a funcionalidade Bluetooth do dispositivo.
