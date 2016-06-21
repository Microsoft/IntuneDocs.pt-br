---
# required metadata

title: Adicionar aplicativos | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2b770f4f-6d36-41e4-b535-514b46e29aaa

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Adicionar aplicativos com o Microsoft Intune
Antes de iniciar a implantação de aplicativos com o Microsoft Intune, reserve um tempo para se familiarizar com os conceitos apresentados neste tópico. Eles ajudarão a entender quais aplicativos você pode implantar em qual plataforma e entender os pré-requisitos que devem estar em vigor antes de fazer isso.

## Tipos de aplicativo que você pode implantar com o Intune
Você pode implantar aplicativos para todos os tipos de dispositivos que têm suporte pelo Intune. Dependendo do tipo de aplicativo que você deseja implantar, o processo e os dispositivos com suporte serão diferentes. Use a tabela a seguir para ajudá-lo a entender o que pode e o que não pode ser implantado:


### **Windows Installer (&#42;.exe, &#42;.msi)**
- Esse tipo de aplicativo deve dar suporte à instalação silenciosa sem nenhuma entrada do usuário. A documentação do seu aplicativo deve incluir as opções de linha de comando relevantes para instalar silenciosamente o aplicativo (por exemplo, **/q**). Uma lista de opções de linha de comando comuns pode ser encontrada [aqui](https://support.microsoft.com/en-us/kb/227091).
- Todos os arquivos e pastas adicionais exigidos pelo programa de instalação do aplicativo deverão estar disponíveis na localização que você especificou para os arquivos de instalação de aplicativo.
- Na maioria dos casos, os arquivos do Windows Installer (.msi) e Windows Installer Patch (.msp) não necessitam de argumentos de linha de comando para serem instalados pelo Intune. Verifique a documentação do seu aplicativo. Se argumentos de linha de comando forem necessários, insira-os como pares Name=Value (como TRANSFORMS=custom_transform.mst).

Este tipo de aplicativo é carregado em seu espaço de armazenamento de nuvem.
### **Pacote do aplicativo para Android (arquivo &#42;.apk)**
Este tipo de aplicativo é carregado em seu espaço de armazenamento de nuvem.
### **Pacote do aplicativo para iOS (arquivo &#42;.ipa)**
- Para implantar aplicativos iOS, você deve ter um pacote .ipa válido.
- Isso significa que o pacote .ipa foi assinado pela Apple e a data de expiração indicada no perfil de provisionamento ainda é válida. O Intune pode distribuir aplicativos iOS empresariais certificados. Nem todos os aplicativos de certificado de desenvolvedor Apple têm suporte.
- Sua empresa deve ser registrada no Programa da Empresa do Desenvolvedor iOS.
- Certifique-se de que o firewall da organização permite acesso aos sites da web de provisionamento e de certificação iOS.
- Um arquivo de manifesto (.plist) não precisa ser implantado com o aplicativo.

Este tipo de aplicativo é carregado em seu espaço de armazenamento de nuvem.

Atualmente, os usuários finais não conseguem instalar aplicativos corporativos do aplicativo diretamente do Portal da Empresa do Intune para iOS. Isso ocorre devido a restrições colocadas em aplicativos que são publicados no iOS App Store (consulte [diretrizes de revisão do aplicativo Store](https://developer.apple.com/app-store/review/guidelines/)). Os usuários podem acessar aplicativos corporativos (incluindo aplicativos gerenciados da Windows Store e pacotes de aplicativos de linha de negócios) ao iniciar o aplicativo Portal da Empresa em seus dispositivos e tocar no bloco Aplicativos da Empresa, que abrirá o navegador e redirecioná-los ao Portal da Web do Intune.

### **Pacote do aplicativo do Windows Phone (&#42;.xap, .appx, .appxbundle)**
- Para implantar aplicativos, você precisará de um certificado de assinatura de código móvel corporativo. Para obter detalhes, consulte [Set up Windows Phone management with Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md) (Configurar o gerenciamento do Windows Phone com o Microsoft Intune).

Este tipo de aplicativo é carregado em seu espaço de armazenamento de nuvem.

Consulte abaixo para obter informações sobre a instalação de aplicativos de linha de negócios da UWP (Plataforma Universal do Windows) com o Intune.

### **Pacote de aplicativos do Windows (. appx, .appxbundle)**
- Para implantar aplicativos, você precisará de um certificado de assinatura de código móvel corporativo. Para obter detalhes, consulte [Set up Windows device management with Microsoft Intune](set-up-windows-device-management-with-microsoft-intune.md) (Configurar o gerenciamento de dispositivos Windows com o Microsoft Intune).

Este tipo de aplicativo é carregado em seu espaço de armazenamento de nuvem.
### **Windows Installer por meio do MDM (&#42;.msi)**
Esse tipo de instalador permite criar e implantar aplicativos baseados no Windows Installer para PCs registrados que executam Windows 10.<br /><br />As seguintes considerações se aplicam quando você usa esse tipo de instalador:
- Só é possível carregar um único arquivo com a extensão .msi.
- O código do produto do arquivo e a versão do produto são usados para a detecção de aplicativo.
- O comportamento de reinicialização padrão do aplicativo será usado. O Intune não controla isso.
- Serão instalados pacotes do MSI por usuário para um único usuário.
- Serão instalados pacotes do MSI por computador para todos os usuários no dispositivo.
- Atualmente, os pacotes do MSI de modo duplo são instalados somente para todos os usuários no dispositivo.
- Há suporte para atualizações de aplicativos quando o código do produto MSI de cada versão é o mesmo.

Este tipo de aplicativo é carregado em seu espaço de armazenamento de nuvem.
### **Link externo**
Usado quando você tiver um(a):
- **URL** que permite aos usuários baixar um aplicativo da loja de aplicativos.
- **Link** para um aplicativo baseado na Web executado no navegador da Web.

Aplicativos com base em links externos não são armazenados em seu espaço de armazenamento em nuvem do Intune.
### **Aplicativo iOS gerenciados da loja de aplicativos**
Permite que você gerencie e implante aplicativos do iOS gratuitos da Windows Store. Também permite associar [políticas de gerenciamento de aplicativos móveis](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) a [aplicativos compatíveis](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) e examinar seu status no console do administrador.<br /><br />Aplicativos iOS gerenciados não são armazenados no seu espaço de armazenamento em nuvem do Intune.
> [!TIP] As opções para dispositivos móveis não estão disponíveis até que você [defina a Autoridade de Gerenciamento de Dispositivo Móvel](get-ready-to-enroll-devices-in-microsoft-intune.md) para o Intune.

## Suporte para aplicativos da UWP (Plataforma Universal do Windows)
Computadores Windows 10 não exigem uma chave de sideload para instalar aplicativos de linha de negócios. No entanto, a chave do Registro **HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Appx\AllowAllTrustedApps** deve ter um valor de **1** para habilitar o sideload.

Se essa chave do Registro não estiver configurada, o Intune definirá automaticamente esse valor como **1** na primeira vez que um aplicativo for implantado no dispositivo. Se você tiver definido o valor como **0**, o Intune não poderá alterar o valor automaticamente e a implantação de aplicativos de linha de negócios falhará.

Os aplicativos de linha de negócios da Plataforma Universal do Windows devem ser assinados com um certificado de assinatura de código confiável em cada dispositivo no qual o aplicativo será implantado. Você pode usar certificados de uma infra-estrutura de PKI interna ou um certificado de um certificado de raiz pública de terceiros instalado no dispositivo.

Em dispositivos Windows 10 Mobile, você pode usar um certificado de assinatura de código que não seja da Symantec para assinar aplicativos **.appx**. Para aplicativos **.xap**, bem como pacotes **.appx** criados para Windows Phone 8.1 que você deseja instalar em dispositivos Windows 10 Mobile, você deve usar um certificado de assinatura de código da Symantec.

## Próximas etapas 

Em seguida, você precisará adicionar aplicativos no console do Intune antes de implantá-los. Você pode adicionar aplicativos para [dispositivos registrados](add-apps-for-mobile-devices-in-microsoft-intune.md) ou para [computadores Windows gerenciados com o software cliente do Intune](add-apps-for-windows-pcs-in-microsoft-intune.md).

<!--HONumber=Jun16_HO2-->


