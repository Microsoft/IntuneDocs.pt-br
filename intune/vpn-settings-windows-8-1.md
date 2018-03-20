---
title: "Configurações de VPN do Microsoft Intune para dispositivos Windows 8.1"
titleSuffix: 
description: "Conheça as definições do Intune que você pode usar para configurar as conexões VPN em dispositivos que executam o Windows 8.1."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8ced3e03fa337034076af75c7984a30cd75105bb
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2018
---
# <a name="configure-vpn-settings-in-microsoft-intune-for-devices-running-windows-81"></a>Definir as configurações de VPN no Microsoft Intune para dispositivos que executam o Windows 8.1

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Este artigo mostra as configurações do Intune que você pode usar para configurar conexões VPN em dispositivos que executam Windows 8.1.

Dependendo das configurações que você escolher, nem todos os valores na lista a seguir serão configuráveis.

## <a name="base-vpn-settings"></a>Configurações de VPN de base


- **Aplicar todas as configurações somente ao Windows 8.1** – Essa é uma configuração que pode ser definida no Portal Clássico do Intune. Não é possível alterar essa configuração no Portal do Azure. Se definido como **Configurado**, as configurações serão aplicadas somente aos dispositivos com Windows 8.1. Se definido como **Não Configurado**, essas configurações também serão aplicadas aos dispositivos com Windows 10.
- **Nome da conexão** – Insira um nome para esta conexão. Os usuários verão esse nome quando navegarem na lista de conexões VPN disponíveis no dispositivo.
- **Servidores** – Adicionar um ou mais servidores VPN aos quais os dispositivos se conectam.
    - **Adicionar** – Abre a página **Adicionar Linha**, na qual é possível especificar as seguintes informações:
        - **Descrição** – Especifique um nome descritivo para o servidor como **Servidor VPN Contoso**.
        - **Endereço IP ou FQDN** – forneça o endereço IP ou o nome de domínio totalmente qualificado do servidor VPN ao qual os dispositivos se conectarão. Exemplos: **192.168.1.1**, **vpn.contoso.com**.
        - **Servidor padrão** – Habilita esse servidor como o servidor padrão que os dispositivos usam para estabelecer a conexão. Verifique se você definiu apenas um servidor como padrão.
    - **Importar** – Navegue até um arquivo que contém uma lista separada por vírgulas de servidores no formato descrição, endereço IP ou FQDN, servidor padrão. Escolha **OK** para importá-los para a lista **Servidores**.
    - **Exportar** – Exporta a lista de servidores para um arquivo de valores separados por vírgula (csv).

- **Tipo de Conexão** – Selecione o tipo de conexão VPN na lista de fornecedores a seguir:
- **Check Point Capsule VPN**
- **SonicWall Mobile Connect**
- **F5 Edge Client**
- **Pulse Secure**

<!--- **Fingerprint** (Check Point Capsule VPN only) - Specify a string (for example, "Contoso Fingerprint Code") that will be used to verify that the VPN server can be trusted. A fingerprint can be sent to the client so it knows to trust any server that presents the same fingerprint when connecting. If the device doesn’t already have the fingerprint, it will prompt the user to trust the VPN server that they are connecting to while showing the fingerprint. (The user manually verifies the fingerprint and chooses **trust** to connect.) --->

- **Grupo ou domínio de logon** (somente SonicWall Mobile Connect) – Especifique o nome do grupo ou domínio de logon ao qual você deseja se conectar.

- **Função** (somente Pulse Secure) – Especifique o nome da função do usuário que tem acesso a essa conexão. Uma função de usuário define configurações e opções pessoais e habilita ou desabilita determinados recursos de acesso.

- **Realm** (somente Pulse Secure) – Especifique o nome do realm de autenticação que você deseja usar. Um realm de autenticação é um agrupamento de recursos de autenticação usado pelo tipo de conexão Pulse Secure.


- **XML Personalizado** – Especifique os comandos XML personalizados para configurar a conexão VPN.

**Exemplo do Pulse Secure:**

```
    <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>

```

**Exemplo do CheckPoint Mobile VPN:**
```
    <CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />

```

**Exemplo do SonicWall Mobile Connect:**
```
    <MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>

```

**Exemplo do F5 Edge Client:**

```
    <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>

```

Para obter mais informações, consulte a documentação do VPN de cada fabricante sobre como gravar comandos XML personalizados.


## <a name="proxy-settings"></a>Configurações de proxy

- **Detectar automaticamente as configurações de proxy** – Se o servidor VPN exigir um servidor proxy para a conexão, especifique se deseja que os dispositivos detectem automaticamente as configurações de conexão. Para obter mais informações, consulte a documentação do Windows Server.
- **Automático** – Use um arquivo de configuração para definir o servidor proxy. Digite a **URL do servidor proxy** (por exemplo **http://proxy.contoso.com**) que contém o arquivo de configuração.
- **Usar servidor proxy** – Habilite essa opção se você quiser inserir manualmente as configurações do servidor proxy.
    - **Endereço** – Insira o endereço do servidor proxy (como um endereço IP).
    - **Número da porta** – Insira o número de porta associado ao servidor proxy.
- **Bypass de proxy para endereços locais** – Se o servidor VPN exigir um servidor proxy para a conexão, selecione essa opção se não quiser usar o servidor proxy para endereços locais que você especificar. Para obter mais informações, consulte a documentação do Windows Server.
