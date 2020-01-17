---
title: Definir configurações de VPN em dispositivos Windows Phone 8.1 no Microsoft Intune – Azure | Microsoft Docs
description: Adicione ou crie um perfil de configuração de VPN usando as definições de configuração de VPN (rede virtual privada), incluindo os detalhes da conexão e as configurações de proxy para incluir o endereço IP ou FQDN e a porta TCP em Microsoft Intune em dispositivos que executam o Windows Phone 8,1.
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
ms.openlocfilehash: 70f33fe132eb6c3dbf91c5dc313369d75f4f3e24
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "75207019"
---
# <a name="add-vpn-settings-on-windows-phone-81-devices-in-microsoft-intune"></a>Adicionar configurações de VPN em dispositivos Windows Phone 8.1 no Microsoft Intune



Este artigo mostra as configurações do Intune que você pode usar para configurar conexões VPN em dispositivos que executam Windows Phone 8.1. 

Dependendo das configurações que você escolher, nem todos os valores na lista a seguir serão configuráveis.

>[!IMPORTANT]
>Windows Phone perfis de VPN 8,1 também são aplicados a dispositivos Windows 10.

## <a name="base-vpn-settings"></a>Configurações de VPN de base

- **Aplicar todas as configurações somente a Windows Phone 8,1**: defina essa configuração no portal clássico do Intune. No centro de administração do Microsoft Endpoint Manager, essa configuração não pode ser alterada. Se definido como **Configurado**, as configurações serão aplicadas somente aos dispositivos com Windows Phone 8.1. Se definido como **Não Configurado**, essas configurações também serão aplicadas aos dispositivos Windows 10 Mobile.
- **Nome da conexão**: Insira um nome para essa conexão. Os usuários verão esse nome quando navegarem na lista de conexões VPN disponíveis no dispositivo.
- **Método de autenticação**: Escolha, entre as seguintes opções, como os dispositivos se autenticam no servidor VPN:
  - **Certificados**: Em **Certificado de autenticação**, escolha um perfil de certificado SCEP ou PKCS criado anteriormente para autenticar a conexão. Para obter mais informações sobre os perfis de certificado, consulte [Como configurar certificados](../protect/certificates-configure.md).
  - **Nome de usuário e senha**: os usuários finais deverão fornecer um nome de usuário e senha para fazer logon no servidor VPN.
- **Servidores**: Adicione um ou mais servidores VPN aos quais os dispositivos se conectarão.
  - **Adicionar**: abre a folha **Adicionar linha**, na qual você pode especificar as seguintes informações:
    - **Descrição**: especifique um nome descritivo para o servidor como **Servidor VPN Contoso**.
    - **Endereço IP ou FQDN**: forneça o endereço IP ou o nome de domínio totalmente qualificado do servidor VPN ao qual os dispositivos se conectam. Exemplos: **192.168.1.1**, **vpn.contoso.com**.
    - **Servidor padrão**: Habilita esse servidor como o servidor padrão que os dispositivos usam para estabelecer a conexão. Verifique se você definiu apenas um servidor como padrão.
  - **Importar**: Procure um arquivo separado por vírgula que inclua uma lista de servidores na descrição de formato, endereço IP ou FQDN, servidor padrão. Escolha **OK** para importar esses servidores para a lista **Servidores**.
  - **Exportar**: Exporta a lista de servidores para um arquivo CSV (valores separados por vírgula).

- **Ignorar VPN na rede de empresa Wi-Fi**: habilite esta opção para especificar que a conexão VPN não será usada quando o dispositivo estiver conectado à rede Wi-Fi da empresa.
- **Ignorar VPN na rede doméstica Wi-Fi**: habilite esta opção para especificar que a conexão VPN não será usada quando o dispositivo estiver conectado a uma rede Wi-Fi doméstica.

- **Tipo de conexão**: Selecione o tipo de conexão VPN na lista de fornecedores a seguir:
  - **Check Point Capsule VPN**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Pulse Secure**

- **Grupo de logon ou domínio** (somente SonicWall Mobile Connect): Especifique o nome do grupo de logon ou domínio ao qual você deseja se conectar.
- **Função** (somente Pulse Secure): Especifique o nome da função do usuário que tem acesso a essa conexão. Uma função de usuário define configurações e opções pessoais e habilita ou desabilita determinados recursos de acesso.
- **Território** (somente Pulse Secure): Especifique o nome do território de autenticação que você deseja usar. Um realm de autenticação é um agrupamento de recursos de autenticação usado pelo tipo de conexão Pulse Secure.

- **Lista de pesquisa de sufixo DNS**: **adicione** um ou mais sufixos DNS. Cada sufixo DNS que você especificar é pesquisado durante a conexão com um site usando um nome curto. Por exemplo, especifique os sufixos DNS **domain1.contoso.com** e **domain2.contoso.com**, visite a URL `http://mywebsite` e as URLs `http://mywebsite.domain1.contoso.com` e `http://mywebsite.domain2.contoso.com` são pesquisadas.

- **XML personalizado**: Especifique comandos XML personalizados que configuram a conexão VPN.

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

- **Túnel dividido**: **habilite** ou **desabilite** essa opção, que permite que os dispositivos decidam qual conexão usar dependendo do tráfego. Por exemplo, um usuário em um hotel usará a conexão VPN para acessar arquivos de trabalho, mas usará a rede padrão do hotel para navegação regular na Web.

## <a name="proxy-settings"></a>Configurações de proxy

- **Detectar automaticamente as configurações de proxy**: Se o servidor VPN exigir um servidor proxy para a conexão, especifique se deseja que os dispositivos detectem automaticamente as configurações de conexão.
- **Script de configuração automática**: Use um arquivo para configurar o servidor proxy. Insira a **URL do servidor proxy** (por exemplo `http://proxy.contoso.com`) que contém o arquivo de configuração.
- **Usar servidor proxy**: habilite essa opção se você quiser inserir manualmente as configurações do servidor proxy.
  - **Endereço**: insira o endereço do servidor proxy (como um endereço IP).
  - **Número da porta**: insira o número da porta associada ao servidor proxy.
- **Ignorar proxy para endereços locais**: Se o servidor VPN exigir um servidor proxy para a conexão e você não quiser usar o servidor proxy para endereços locais que você inserir, selecione esta opção.

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada ainda. Em seguida, [atribua o perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).

Defina as configurações de VPN em dispositivos [Android](vpn-settings-android.md), [Android Enterprise](vpn-settings-android-enterprise.md), [MacOS](vpn-settings-macos.md)e [Windows 10](vpn-settings-windows-10.md) .
