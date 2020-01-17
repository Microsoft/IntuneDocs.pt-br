---
title: Definir configurações de VPN em dispositivos Windows 8.1 no Microsoft Intune – Azure | Microsoft Docs
description: Adicione ou crie um perfil de configuração de VPN usando as definições de configuração de VPN (rede virtual privada), incluindo os detalhes da conexão e as configurações de proxy para incluir o endereço IP ou FQDN e a porta TCP em Microsoft Intune em dispositivos que executam o Windows 8.1.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/19/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9f9a1399d5474d79ac8fd48a8aa3a844f20eb640
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "75207036"
---
# <a name="add-vpn-settings-on-windows-81-devices-in-microsoft-intune"></a>Adicionar configurações de VPN em dispositivos Windows 8.1 no Microsoft Intune



Este artigo mostra as configurações do Intune que você pode usar para configurar conexões VPN em dispositivos que executam Windows 8.1.

Dependendo das configurações que você escolher, nem todos os valores na lista a seguir serão configuráveis.

## <a name="base-vpn-settings"></a>Configurações de VPN de base

- **Aplicar todas as configurações somente a Windows 8.1**: defina essa configuração no portal clássico do Intune. No centro de administração do Microsoft Endpoint Manager, essa configuração não pode ser alterada. Se definido como **Configurado**, as configurações serão aplicadas somente aos dispositivos com Windows 8.1. Se definido como **Não Configurado**, essas configurações também serão aplicadas aos dispositivos com Windows 10.
- **Nome da conexão**: Insira um nome para essa conexão. Os usuários verão esse nome quando navegarem na lista de conexões VPN disponíveis no dispositivo.
- **Servidores**: Adicione um ou mais servidores VPN aos quais os dispositivos se conectarão.
  - **Adicionar**: abre a página **Adicionar Linha**, na qual é possível especificar as seguintes informações:
    - **Descrição**: especifique um nome descritivo para o servidor como **Servidor VPN Contoso**.
    - **Endereço IP ou FQDN**: forneça o endereço IP ou o nome de domínio totalmente qualificado do servidor VPN ao qual os dispositivos se conectam. Exemplos: **192.168.1.1**, **vpn.contoso.com**.
    - **Servidor padrão**: Habilita esse servidor como o servidor padrão que os dispositivos usam para estabelecer a conexão. Verifique se você definiu apenas um servidor como padrão.
  - **Importar**: procure um arquivo separado por vírgula que inclua a lista de servidores na descrição de formato, endereço IP ou FQDN, servidor padrão. Escolha **OK** para importar esses servidores para a lista **Servidores**.
  - **Exportar**: exporta a lista de servidores para um arquivo de valores separados por vírgula (csv).

- **Tipo de conexão**: Selecione o tipo de conexão VPN na lista de fornecedores a seguir:
  - **Check Point Capsule VPN**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Pulse Secure**

<!--- **Fingerprint** (Check Point Capsule VPN only): Specify a string (for example, "Contoso Fingerprint Code") that will be used to verify that the VPN server can be trusted. A fingerprint can be sent to the client so it knows to trust any server that presents the same fingerprint when connecting. If the device doesn’t already have the fingerprint, it will prompt the user to trust the VPN server that they are connecting to while showing the fingerprint. (The user manually verifies the fingerprint and chooses **trust** to connect.) --->

- **Grupo de logon ou domínio** (somente SonicWall Mobile Connect): Especifique o nome do grupo de logon ou domínio ao qual você deseja se conectar.

- **Função** (somente Pulse Secure): Especifique o nome da função do usuário que tem acesso a essa conexão. Uma função de usuário define configurações e opções pessoais e habilita ou desabilita determinados recursos de acesso.

- **Território** (somente Pulse Secure): Especifique o nome do território de autenticação que você deseja usar. Um realm de autenticação é um agrupamento de recursos de autenticação usado pelo tipo de conexão Pulse Secure.

- **XML personalizado**: especifique comandos XML personalizados que configuram a conexão VPN.

  **Exemplo de Pulse Secure**:

  ```xml
  <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
  ```

  **Exemplo de VPN Móvel de Ponto de Verificação**:

  ```xml
  <CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
  ```

  **Exemplo do SonicWall Mobile Connect**:

  ```xml
  <MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
  ```

  **Exemplo de F5 Edge Client**:

  ```xml
  <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
  ```

  Para obter mais informações sobre como escrever comandos XML personalizados, consulte a documentação de VPN do fabricante.

## <a name="proxy-settings"></a>Configurações de proxy

- **Detectar automaticamente as configurações de proxy**: Se o servidor VPN exigir um servidor proxy para a conexão, especifique se deseja que os dispositivos detectem automaticamente as configurações de conexão.
- **Script de configuração automática**: Use um arquivo para configurar o servidor proxy. Insira a **URL do servidor Proxy** que contém o arquivo de configuração. Por exemplo, insira `http://proxy.contoso.com`.
- **Usar servidor proxy**: habilite essa opção se você quiser inserir manualmente as configurações do servidor proxy.
  - **Endereço**: insira o endereço do servidor proxy (como um endereço IP).
  - **Número da porta**: insira o número da porta associada ao servidor proxy.
- **Ignorar proxy para endereços locais**: se o servidor VPN exigir um servidor proxy para a conexão e você não quiser usar o servidor proxy para endereços locais que você inserir, selecione esta opção.

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada ainda. Em seguida, [atribua o perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).

Defina as configurações de VPN em dispositivos [Android](vpn-settings-android.md), [Android Enterprise](vpn-settings-android-enterprise.md), [MacOS](vpn-settings-macos.md)e [Windows 10](vpn-settings-windows-10.md) .
