---
title: Adicionar aplicativos | Microsoft Intune
description: "Antes de iniciar a implantação de aplicativos com o Intune, reserve um tempo para se familiarizar com os conceitos apresentados neste tópico."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2b770f4f-6d36-41e4-b535-514b46e29aaa
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c880bd9dfb998355a18e78af898a96d4cee393f7
ms.openlocfilehash: c4b1e5d3bb8b949096f7d15ddbbf0d1540485d0d


---

# Adicionar aplicativos com o Microsoft Intune
Antes de iniciar a implantação de aplicativos com o Microsoft Intune, reserve um tempo para se familiarizar com os conceitos apresentados neste tópico. Esses conceitos ajudarão você a entender quais aplicativos você pode implantar em qual plataforma. Eles também o ajudarão a entender os pré-requisitos que devem estar em vigor antes da implantação dos aplicativos.

## Tipos de aplicativo que você pode implantar

### Instalador de Software

|Tipo de aplicativo|Detalhes|
|----------------|-------|
|**Windows Installer (&#42;.exe, &#42;.msi)**|Esse tipo de aplicativo deve dar suporte à instalação silenciosa sem nenhuma entrada do usuário. A documentação do seu aplicativo deve incluir as opções de linha de comando relevantes para instalar silenciosamente o aplicativo (por exemplo, **/q**). Você pode encontrar uma lista de opções de linha de comando comuns em [Opções de linha de comando para a ferramenta do Microsoft Windows Installer](https://support.microsoft.com/en-us/kb/227091).<br><br>Quaisquer arquivos e pastas adicionais exigidos pelo programa de instalação do aplicativo deverão estar disponíveis na localização que você especificou para os arquivos de instalação de aplicativo.<br><br>Na maioria dos casos, os arquivos do Windows Installer (.msi) e Windows Installer Patch (.msp) não precisam do Intune para instalar nenhum argumento de linha de comando. Verifique a documentação do seu aplicativo.<br><br>Se argumentos de linha de comando forem necessários, insira-os como pares Name=Value (como TRANSFORMS=custom_transform.mst).|
|**Pacote do aplicativo para Android (&#42;.apk)**|Para implantar aplicativos Android, você deve ter um pacote .apk válido.|
|**Pacote do aplicativo para iOS (&#42;.ipa)**|Para implantar aplicativos iOS, você deve ter um pacote .ipa válido.<br><br>Isso significa que o pacote .ipa foi assinado pela Apple e a data de vencimento no perfil de provisionamento ainda é válida. O Intune pode distribuir aplicativos iOS empresariais certificados.<br><br>Nem todos os aplicativos de certificado de desenvolvedor Apple têm suporte.<br><br>Sua empresa deve ser registrada no Programa da Empresa do Desenvolvedor iOS.<br><br>Certifique-se de que o firewall da organização permite acesso aos sites de provisionamento e de certificação iOS.<br><br>Você não precisa implantar um arquivo de manifesto (. plist) com o aplicativo.|
|**Pacote do aplicativo do Windows Phone (&#42;.xap, .appx, .appxbundle)**|Para implantar aplicativos, você precisará de um certificado de assinatura de código móvel corporativo. Para obter detalhes, consulte [Set up Windows Phone management with Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md) (Configurar o gerenciamento do Windows Phone com o Microsoft Intune).|
|**Pacote de aplicativos do Windows (. appx, .appxbundle)**|Para implantar aplicativos, você precisará de um certificado de assinatura de código móvel corporativo. Para obter detalhes, consulte [Set up Windows device management with Microsoft Intune](set-up-windows-device-management-with-microsoft-intune.md) (Configurar o gerenciamento de dispositivos Windows com o Microsoft Intune).|
|**Windows Installer por meio do MDM (&#42;.msi)**|Você usa este aplicativo para criar e implantar aplicativos baseados no Windows Installer para computadores registrados que executam Windows 10. Esses computadores são gerenciados por meio do MAM (gerenciamento de dispositivo móvel).<br /><br />Só é possível carregar um único arquivo com a extensão .msi.<br><br>O código do produto do arquivo e a versão do produto são usados para a detecção de aplicativo.<br><br>O comportamento de reinicialização padrão do aplicativo será usado. O Intune não controla isso.<br><br>Serão instalados pacotes do MSI por usuário para um único usuário.<br><br>Serão instalados pacotes do MSI por computador para todos os usuários no dispositivo.<br><br>Atualmente, os pacotes do MSI de modo duplo são instalados somente para todos os usuários no dispositivo.<br><br>Há suporte para atualizações de aplicativos quando o código do produto MSI de cada versão é o mesmo.<br>
Todos os tipos de aplicativo do instalador de software são atualizados para seu espaço de armazenamento de nuvem.

### **Link externo**
Use um link externo quando você tiver:
- Uma URL que permite aos usuários baixar um aplicativo da loja de aplicativos.
- Um Link para um aplicativo baseado na Web executado no navegador da Web.

Aplicativos com base em links externos não são armazenados em seu espaço de armazenamento em nuvem do Intune.
### **Aplicativo iOS gerenciados da loja de aplicativos**
Você pode usar aplicativos iOS gerenciados para gerenciar e implantar aplicativos iOS gratuitos da loja de aplicativos. Você também pode usar aplicativos iOS gerenciados para associar [políticas de gerenciamento de aplicativos móveis](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) a [aplicativos compatíveis](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) e examinar seu status no console do administrador.<br /><br />Aplicativos iOS gerenciados não são armazenados no seu espaço de armazenamento em nuvem do Intune.

> [!TIP]
> As opções para dispositivos móveis não estão disponíveis até que você [defina a autoridade de MDM](prerequisites-for-enrollment.md) para o Intune.

## Intune Software Publisher
O Microsoft Intune Software Publisher inicia quando você adiciona ou modifica aplicativos do console de administrador do Intune. No Publisher, você seleciona e configura um tipo de instalação de software que vai:

- Carregar aplicativos (programas para computadores ou aplicativos para dispositivos móveis) para serem armazenados no armazenamento em nuvem Intune.
- Vincular a uma loja online ou aplicativo Web.

Antes de começar a usar o Software Publisher, é preciso instalar a versão completa do [Microsoft .NET Framework 4.0](https://www.microsoft.com/download/details.aspx?id=17851). Após a instalação, pode ser necessário reiniciar seu computador para que o Software Publisher abra corretamente.

## Espaço de armazenamento em nuvem
Todos os aplicativos que você cria usando o tipo de instalação do instalador de software (por exemplo, uma linha de aplicativo de negócios) são empacotados e carregados no armazenamento em nuvem do Microsoft Intune. Uma assinatura de avaliação do Intune inclui 2 GB de armazenamento baseado em nuvem que é usado para armazenar aplicativos gerenciados e atualizações. Sua assinatura completa inclui 20 GB de espaço de armazenamento.

Você pode ver quanto espaço está usando no nó **Uso de Armazenamento** do espaço de trabalho **Admin**.

Os requisitos de espaço de armazenamento em nuvem são os seguintes:

-   Todos os arquivos de instalação do aplicativo devem estar na mesma pasta.
-   O tamanho máximo do arquivo para qualquer arquivo que você carregar é de 2 GB.


## Suporte para aplicativos da UWP (Plataforma Universal do Windows)
Computadores Windows 10 não exigem uma chave de sideload para instalar aplicativos de linha de negócios. No entanto, a chave do Registro **HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Appx\AllowAllTrustedApps** deve ter um valor de **1** para habilitar o sideload.

Se essa chave do Registro não estiver configurada, o Intune definirá automaticamente esse valor como **1** na primeira vez que um aplicativo for implantado no dispositivo. Se você definiu o valor como **0**, o Intune não poderá alterar o valor automaticamente, e a implantação de aplicativos de linha de negócios falhará.

Os aplicativos de linha de negócios da Plataforma Universal do Windows devem ser assinados com um certificado de assinatura de código confiável em cada dispositivo no qual o aplicativo será implantado. Você pode usar um certificado de uma PKI (infraestrutura de chave pública) interna ou um certificado de um certificado raiz público de terceiros instalado no dispositivo.

Em dispositivos Windows 10 Mobile, você pode usar um certificado de assinatura de código que não seja da Symantec para assinar aplicativos **.appx**. Para aplicativos **.xap**, bem como pacotes **.appx** criados para Windows Phone 8.1 que você deseja instalar em dispositivos Windows 10 Mobile, você deve usar um certificado de assinatura de código da Symantec.

## Próximas etapas

Você precisará adicionar aplicativos no console do Intune antes de implantá-los. Você pode adicionar aplicativos para [dispositivos registrados](add-apps-for-mobile-devices-in-microsoft-intune.md) ou para [computadores Windows gerenciados com o software cliente do Intune](add-apps-for-windows-pcs-in-microsoft-intune.md).



<!--HONumber=Sep16_HO4-->


