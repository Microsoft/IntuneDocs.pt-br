---
title: "Configurações de VPN do Intune para dispositivos Windows 8.1 | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: saiba mais sobre as configurações do Intune que você pode usar para configurar conexões de VPN em dispositivos Windows 8.1."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: aff935508551b45ee0a69f907506b0703290fddf
ms.openlocfilehash: 31a7779537062a63fac1fb512a7cf4b9033368f7


---

# <a name="vpn-settings-for-windows-81-devices-in-intune-azure-preview"></a>Configurações de VPN para dispositivos Windows 8.1 na versão prévia do Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Dependendo das configurações escolhidas, nem todos os valores na lista abaixo serão configuráveis.

## <a name="base-vpn-settings"></a>Configurações de VPN de base


- **Aplicar todas as configurações somente ao Windows 8.1** – Essa é uma configuração de pode ser definida no Portal Clássico do Intune. Não é possível alterar essa configuração no Portal do Azure. Se definido como **Configurado**, as configurações serão aplicadas somente aos dispositivos com Windows 8.1. Se definido como **Não Configurado**, essas configurações também serão aplicadas aos dispositivos com Windows 10.
- **Nome da conexão** – Insira um nome para esta conexão. Usuários finais verão esse nome quando navegarem pela lista de conexões VPN disponíveis em seus dispositivos.
- **Servidores** – Adicionar um ou mais servidores VPN aos quais os dispositivos se conectarão.
    - **Adicionar** – Abre a folha **Adicionar linha**, na qual você pode especificar as seguintes informações:
        - **Descrição** – Especifique um nome descritivo para o servidor como **Servidor VPN Contoso**.
        - **Endereço IP ou FQDN** – Forneça o endereço IP ou o nome de domínio totalmente qualificado do servidor VPN ao qual os dispositivos se conectarão. Exemplos: **192.168.1.1**, **vpn.contoso.com**.
        - **Servidor padrão** – Habilita esse servidor como o servidor padrão que os dispositivos usarão para estabelecer a conexão. Verifique se você definiu apenas um servidor como padrão.
    - **Importar** – Navegue até um arquivo que contém uma lista separada por vírgulas de servidores no formato descrição, endereço IP ou FQDN, servidor padrão. Escolha **OK** para importá-los para a lista **Servidores**.
    - **Exportar** – Exporta a lista de servidores para um arquivo de valores separados por vírgula (csv).

- **Tipo de Conexão** – Selecione o tipo de conexão VPN na lista de fornecedores a seguir:
- **Check Point Capsule VPN**
- **Dell SonicWALL Mobile Connect**
- **F5 Edge Client**
- **Pulse Secure**

<!--- **Fingerprint** (Check Point Capsule VPN only) - Specify a string (for example, "Contoso Fingerprint Code") that will be used to verify that the VPN server can be trusted. A fingerprint can be sent to the client so it knows to trust any server that presents the same fingerprint when connecting. If the device doesn’t already have the fingerprint, it will prompt the user to trust the VPN server that they are connecting to while showing the fingerprint. (The user manually verifies the fingerprint and chooses **trust** to connect.) --->

- **Grupo de logon ou domínio** (somente Dell SonicWALL Mobile Connect) – Especifique o nome do grupo de logon ou domínio ao qual você deseja se conectar.

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

**Exemplo do Dell SonicWALL Mobile Connect:**
```
    <MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>

```

**Exemplo do F5 Edge Client:**

```
    <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>

```

Consulte a documentação do VPN de cada fabricante para obter mais informações sobre como escrever comandos XML personalizados.


## <a name="proxy-settings"></a>Configurações de proxy

- **Detectar automaticamente as configurações de proxy** – Se o servidor VPN exigir um servidor proxy para a conexão, especifique se deseja que os dispositivos detectem automaticamente as configurações de conexão. Para obter mais informações, consulte a documentação do Windows Server.
- **Automático** – Use um arquivo de configuração para definir o servidor proxy. Digite a **URL do servidor proxy** (por exemplo **http://proxy.contoso.com**) que contém o arquivo de configuração.
- **Usar servidor proxy** – Habilite essa opção se você quiser inserir manualmente as configurações do servidor proxy.
    - **Endereço** – Insira o endereço do servidor proxy (como um endereço IP).
    - **Número da porta** – Insira o número de porta associado ao servidor proxy.
- **Bypass de proxy para endereços locais** – Se o servidor VPN exigir um servidor proxy para a conexão, selecione essa opção se não quiser usar o servidor proxy para endereços locais que você especificar. Para obter mais informações, consulte a documentação do Windows Server.



<!--HONumber=Feb17_HO1-->


