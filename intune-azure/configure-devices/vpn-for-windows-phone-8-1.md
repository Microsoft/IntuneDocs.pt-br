---
title: "Configurações de VPN do Intune para dispositivos Windows Phone 8.1 | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: saiba mais sobre as configurações do Intune que você pode usar para configurar conexões VPN em dispositivos Windows Phone 8.1."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c1a9053f-02a7-4735-bc0d-fe4573b31ed4
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 674a806b16d1f88413c1d1bbda1fb1d4f3363771
ms.lasthandoff: 02/16/2017


---

# <a name="vpn-settings-for-windows-phone-81-devices-in-microsoft-intune"></a>Configurações de VPN para dispositivos Windows Phone 8.1 no Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Dependendo das configurações escolhidas, nem todos os valores na lista abaixo serão configuráveis.

## <a name="base-vpn-settings"></a>Configurações de VPN de base

- **Aplicar todas as configurações somente ao Windows Phone 8.1** – Essa é uma configuração de pode ser definida no Portal Clássico do Intune. Não é possível alterar essa configuração no Portal do Azure. Se definido como **Configurado**, as configurações serão aplicadas somente aos dispositivos com Windows Phone 8.1. Se definido como **Não Configurado**, essas configurações também serão aplicadas aos dispositivos Windows 10 Mobile.
- **Nome da conexão** – Insira um nome para esta conexão. Usuários finais verão esse nome quando navegarem pela lista de conexões VPN disponíveis em seus dispositivos.
- **Método de autenticação** – Escolha como os dispositivos se autenticarão do servidor VPN:
    - **Certificados** – Em **Certificado de autenticação**, escolha um perfil de certificado SCEP ou PKCS criado anteriormente para autenticar a conexão. Para obter mais detalhes sobre os perfis de certificado, consulte [Como configurar certificados](how-to-configure-certificates.md).
    - **Nome de usuário e senha** – Os usuários finais deverão fornecer um nome de usuário e senha para fazer logon no servidor VPN.
- **Servidores** – Adicionar um ou mais servidores VPN aos quais os dispositivos se conectarão.
    - **Adicionar** – Abre a folha **Adicionar linha**, na qual você pode especificar as seguintes informações:
        - **Descrição** – Especifique um nome descritivo para o servidor como **Servidor VPN Contoso**.
        - **Endereço IP ou FQDN** – Forneça o endereço IP ou o nome de domínio totalmente qualificado do servidor VPN ao qual os dispositivos se conectarão. Exemplos: **192.168.1.1**, **vpn.contoso.com**.
        - **Servidor padrão** – Habilita esse servidor como o servidor padrão que os dispositivos usarão para estabelecer a conexão. Verifique se você definiu apenas um servidor como padrão.
    - **Importar** – Navegue até um arquivo que contém uma lista separada por vírgulas de servidores no formato descrição, endereço IP ou FQDN, servidor padrão. Escolha **OK** para importá-los para a lista **Servidores**.
    - **Exportar** – Exporta a lista de servidores para um arquivo de valores separados por vírgula (csv).

- **Bypass de VPN na rede Wi-Fi corporativa** – Habilite esta opção para especificar que a conexão VPN não será usada quando o dispositivo estiver conectado à rede Wi-Fi da empresa.
- **Bypass de VPN na rede Wi-Fi doméstica** – Habilite esta opção para especificar que a conexão VPN não será usada quando o dispositivo estiver conectado a uma rede Wi-Fi doméstica.

- **Tipo de Conexão** – Selecione o tipo de conexão VPN na lista de fornecedores a seguir:
    - **Check Point Capsule VPN**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**

- **Grupo de logon ou domínio** (somente Dell SonicWALL Mobile Connect) – Especifique o nome do grupo de logon ou domínio ao qual você deseja se conectar.
- **Função** (somente Pulse Secure) – Especifique o nome da função do usuário que tem acesso a essa conexão. Uma função de usuário define configurações e opções pessoais e habilita ou desabilita determinados recursos de acesso.
- **Realm** (somente Pulse Secure) – Especifique o nome do realm de autenticação que você deseja usar. Um realm de autenticação é um agrupamento de recursos de autenticação usado pelo tipo de conexão Pulse Secure.

- **Lista de pesquisa de sufixos DNS** - **Adicionar** um ou mais sufixos de DNS. Cada sufixo DNS que você especificar será pesquisado durante a conexão com um site usando um nome curto. Por exemplo, especifique sufixos DNS **domain1.contoso.com** e **domain2.contoso.com**, visite a URL **http://mywebsite** e as URLs **http://mywebsite.domain1.contoso.com** e **http://mywebsite.domain2.contoso.com serão pesquisadas**.

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

- **Túnel dividido** - **Habilitar** ou **Desabilitar** essa opção que permite que os dispositivos decidam qual conexão usar dependendo do tráfego. Por exemplo, um usuário em um hotel usará a conexão VPN para acessar arquivos de trabalho, porém usará a rede padrão do hotel para navegação regular na Web.




## <a name="proxy-settings"></a>Configurações de proxy

- **Detectar automaticamente as configurações de proxy** – Se o servidor VPN exigir um servidor proxy para a conexão, especifique se deseja que os dispositivos detectem automaticamente as configurações de conexão. Para obter mais informações, consulte a documentação do Windows Server.
- **Automático** – Use um arquivo de configuração para definir o servidor proxy. Digite a **URL do servidor proxy** (por exemplo **http://proxy.contoso.com**) que contém o arquivo de configuração.
- **Usar servidor proxy** – Habilite essa opção se você quiser inserir manualmente as configurações do servidor proxy.
    - **Endereço** – Insira o endereço do servidor proxy (como um endereço IP).
    - **Número da porta** – Insira o número de porta associado ao servidor proxy.
- **Bypass de proxy para endereços locais** – Se o servidor VPN exigir um servidor proxy para a conexão, selecione essa opção se não quiser usar o servidor proxy para endereços locais que você especificar. Para obter mais informações, consulte a documentação do Windows Server.

