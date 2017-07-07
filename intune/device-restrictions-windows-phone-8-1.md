---
title: "Configurações de restrição de dispositivo do Intune para Windows Phone 8.1"
titleSuffix: Intune on Azure
description: "Conheça as configurações do Intune que você pode usar para controlar as configurações e as funcionalidades do dispositivo em dispositivos Windows Phone 8.1."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2d42714-49ca-43b3-b080-2e67a4268198
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e425b8a3c93c2f5dc73fbe9c75aa9adf49c5cdc8
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="windows-phone-81-device-restriction-settings-in-microsoft-intune"></a>Configurações de restrição de dispositivo Windows Phone 8.1 no Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="general"></a>Geral
-   **Aplicar todas as configurações somente ao Windows Phone 8.1** – Essa é uma configuração de pode ser definida no Portal Clássico do Intune. Não é possível alterar essa configuração no Portal do Azure. Se definido como **Configurado**, as configurações serão aplicadas somente aos dispositivos com Windows Phone 8.1. Se definido como **Não Configurado**, essas configurações também serão aplicadas aos dispositivos Windows 10 Mobile.
-   **Câmera** – Habilita ou bloqueia a câmera do dispositivo.
-   **Copiar e colar** – Habilita ou bloqueia a funcionalidade de copiar e colar nos dispositivos.
-   **Armazenamento removível** – Permite que o dispositivo use armazenamento removível, como cartões SD.
-   **Geolocalização** – Permite que o dispositivo utilize informações de localização.
-   **Conta da Microsoft** – Habilitar ou impedir que o usuário vincule uma conta da Microsoft ao dispositivo.
-   **Captura de tela** – Permite que o usuário capture o conteúdo da tela como um arquivo de imagem.
-   **Envio de dados de diagnóstico** – Permite que o dispositivo envie informações de diagnóstico à Microsoft.
-   **Sincronizar contas de email personalizadas** – Permite que o dispositivo se conecte a contas de email não Microsoft.

## <a name="password"></a>Senha
-   **Aplicar todas as configurações somente ao Windows Phone 8.1** – Essa é uma configuração de pode ser definida no Portal Clássico do Intune. Não é possível alterar essa configuração no Portal do Azure. Se definido como **Configurado**, as configurações serão aplicadas somente aos dispositivos com Windows Phone 8.1. Se definido como **Não Configurado**, essas configurações também serão aplicadas aos dispositivos Windows 10 Mobile.
-   **Senha obrigatória** – Exigir que o usuário final insira uma senha para acessar o dispositivo.
    -   **Tipo de senha exigida** – Especifica o tipo de senha que será necessário, como apenas com caracteres numéricos ou alfanuméricos.
    -   **Tamanho mínimo da senha** – Especifica o número mínimo de caracteres necessários na senha.
    -   **Senhas simples** – Especifica que senhas simples, como “0000” e “1234”, podem ser usadas.
    -   **Número de falhas de entrada antes de apagar o dispositivo** – Especifica o número de vezes que uma senha incorreta pode ser inserida antes que o dispositivo seja apagado.
    -   **Máximo de minutos de inatividade para o bloqueio de tela** – Especifica o período que um dispositivo deve permanecer ocioso antes da tela ser bloqueada automaticamente.
    -   **Expiração da senha (dias)** – Especifica o número de dias antes que a senha do dispositivo precise ser alterada.
    -   **Impedir a reutilização de senhas anteriores** – Especifica quantas senhas usadas anteriormente são lembradas.
-   **Criptografia** – Exige que os dados em dispositivos móveis com suporte sejam criptografados.

## <a name="app-store"></a>Loja de aplicativos
-   **Aplicar todas as configurações somente ao Windows Phone 8.1** – Essa é uma configuração de pode ser definida no Portal Clássico do Intune. Não é possível alterar essa configuração no Portal do Azure. Se definido como **Configurado**, as configurações serão aplicadas somente aos dispositivos com Windows Phone 8.1. Se definido como **Não Configurado**, essas configurações também serão aplicadas aos dispositivos Windows 10 Mobile.
-   **Loja de aplicativos** – Permite que os usuários se conectem à loja de aplicativos do dispositivo.

## <a name="restricted-apps"></a>Aplicativos restritos

-   **Aplicar todas as configurações somente ao Windows Phone 8.1** – Essa é uma configuração de pode ser definida no Portal Clássico do Intune. Não é possível alterar essa configuração no Portal do Azure. Se definido como **Configurado**, as configurações serão aplicadas somente aos dispositivos com Windows Phone 8.1. Se definido como **Não Configurado**, essas configurações também serão aplicadas aos dispositivos Windows 10 Mobile.

Na lista de aplicativos restritos, você pode configurar uma das seguintes listas:

Uma lista de **Aplicativos bloqueados** – Lista os aplicativos (não gerenciados pelo Intune) que os usuários não têm permissão para instalar e executar.
Uma lista de **Aplicativos permitidos** – Lista os aplicativos que os usuários têm permissão para instalar. Aplicativos que são gerenciados pelo Intune são permitidos automaticamente.

Para configurar a lista, clique em **Adicionar**, especifique um nome de sua preferência, o editor do aplicativo (opcional) e a URL para o aplicativo na loja de aplicativos.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Como especificar a URL de um aplicativo na loja

Para especificar uma URL de aplicativo na lista de aplicativos permitidos e bloqueados, use o seguinte formato:

Na página da [Windows Phone Store](https://www.microsoft.com/store/apps/windows-phone), pesquise o aplicativo que você deseja usar.

Abra a página do aplicativo e copie a URL para a área de transferência. Agora você pode usar isso como a URL em uma lista de aplicativos permitidos ou bloqueados.

Exemplo: pesquisar o aplicativo Skype na loja. A URL usada será **http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51**.



### <a name="additional-options"></a>Opções adicionais

Você também pode clicar em **Importar** para popular a lista de um arquivo csv no formato <*url do aplicativo*>, <*nome do aplicativo*>, <*editor do aplicativo*>, ou clique em **Exportar** para criar um arquivo csv que inclui o conteúdo da lista de aplicativos restritos no mesmo formato.


## <a name="browser"></a>Navegador
-   **Aplicar todas as configurações somente ao Windows Phone 8.1** – Essa é uma configuração de pode ser definida no Portal Clássico do Intune. Não é possível alterar essa configuração no Portal do Azure. Se definido como **Configurado**, as configurações serão aplicadas somente aos dispositivos com Windows Phone 8.1. Se definido como **Não Configurado**, essas configurações também serão aplicadas aos dispositivos Windows 10 Mobile.
-   **Navegador da Web** – Habilita ou bloqueia o navegador da Web interno em dispositivos.

## <a name="cellular-and-connectivity"></a>Rede Celular e Conectividade
-   **Aplicar todas as configurações somente ao Windows Phone 8.1** – Essa é uma configuração de pode ser definida no Portal Clássico do Intune. Não é possível alterar essa configuração no Portal do Azure. Se definido como **Configurado**, as configurações serão aplicadas somente aos dispositivos com Windows Phone 8.1. Se definido como **Não Configurado**, essas configurações também serão aplicadas aos dispositivos Windows 10 Mobile.
-   **Wi-Fi** – Habilita ou desabilita a funcionalidade Wi-Fi do dispositivo.
-   **Compartilhamento da Internet por Wi-Fi** – Habilita o uso de compartilhamento de Internet por Wi-Fi no dispositivo.
-   **Conectar automaticamente a hotspots Wi-Fi** – Permite que o dispositivo se conecte automaticamente a hotspots Wi-Fi gratuitos e aceite automaticamente os termos de uso.
-   **Relatórios de hotspot Wi-Fi** – Envia informações sobre conexões Wi-Fi para ajudar o usuário a descobrir conexões próximas.
-   **NFC** – Habilita ou desabilita as operações que usam comunicação a curta distância em dispositivos que dão suporte a ela.
-   **Bluetooth** – Habilita ou desabilita a funcionalidade Bluetooth do dispositivo.
