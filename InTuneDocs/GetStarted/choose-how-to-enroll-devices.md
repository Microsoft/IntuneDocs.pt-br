---
# required metadata

title: Escolher como registrar dispositivos móveis | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 06/06/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: cac62b64-3f8b-47ae-aa66-970c7ba15466

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: damionw
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Escolher como registrar dispositivos móveis

Registro de dispositivo móvel é o processo que traz smartphones, tablets e computadores para gerenciamento pelo Microsoft Intune. Como administrador, você precisa determinar a melhor maneira de registrar dispositivos com base no seguinte:

 -  Propriedade (pessoal versus propriedade da empresa)
 -  Uso (compartilhado versus pessoal)
 -  Plataforma (iOS, Android, Windows Phone, computador Windows ou computador Mac)

As respostas para as perguntas a seguir ajudam a determinar o melhor método de registro para os dispositivos gerenciados.

## **Os funcionários trazem seus próprios dispositivos ou recebem dispositivos fornecidos pela sua organização?**

  **Dispositivos de usuários**, também conhecidos como registro BYOD ("Traga seu próprio dispositivo"), permitem que os usuários registrem seus dispositivos para obter acesso aos recursos da empresa, como email, aplicativos da empresa, os dados da empresa e suporte. **COD (Dispositivos da empresa)** são fornecidos pela organização para os funcionários atenderem uma necessidade de negócios.
  > [!div class="button"]   [Registro BYOD >](#byod-device-enrollment)   [Registro de COD>](cod-device-enrollment)

### Registro de dispositivo BYOD

O registro de BYOD requer que os usuários instalem o aplicativo de Portal da Empresa do Intune em seus dispositivos. Em seguida, eles podem iniciar o aplicativo e registrá-lo fornecendo suas credenciais corporativas ou de estudante. O Intune fornecido localiza uma licença para essas credenciais, o dispositivo é adicionado ao console de administração do Intune e recebe a política do Intune, concedendo acesso aos recursos da empresa.

**Selecionar o tipo de dispositivo:**

> [!div class="op_single_selector"]
- [Configurar o gerenciamento de Android com o Microsoft Intune](..deploy-use/set-up-android-management-with-microsoft-intune.md)
- [Set up iOS and Mac management with Microsoft Intune](..deploy-use/set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Configurar o gerenciamento do Windows Phone com o Microsoft Intune](..deploy-use/set-up-windows-phone-management-with-microsoft-intune.md)
- [Configurar o gerenciamento do dispositivo Windows com o Microsoft Intune](..deploy-use/set-up-windows-device-management-with-microsoft-intune.md)


### Registro de dispositivo COD

Dispositivos da empresa podem ser registrados para dar suporte a um usuário dedicado ou compartilhado.  **Dispositivos compartilhados** não tem um único usuário e geralmente não estão configurados para acessar email. Os exemplos incluem dispositivos de quiosque ou dispositivos orientados a tarefas que os usuários emprestam de um pool conforme necessário e depois retornam. Os métodos de registro recomendados dependem da plataforma dos dispositivos. Os **usuários individuais** que são emitidos a usuários individuais precisam ser controlados como ativos da empresa ao mesmo tempo que permitem aos usuários acessar email e dados como dispositivos personalizados. Os métodos de registro recomendados dependem da plataforma dos dispositivos.

## **Seus dispositivos da empresa são compartilhados ou têm usuários dedicados?**

> [!div class="button"] [Compartilhado >](#Shared-company-owned-devices)   [Dedicado >](..deploy-use/get-ready-to-enroll-devices-in-microsoft-intune)


### Dispositivos da empresa compartilhados

Esses dispositivos não tem um único usuário e geralmente não estão configurados para acessar email. Os exemplos incluem dispositivos de quiosque ou dispositivos orientados a tarefas que os usuários emprestam de um pool conforme necessário e depois retornam. Os métodos de registro recomendados dependem da plataforma dos dispositivos.

  - **Dispositivos com Android e Windows**: um *gerenciador de registro de dispositivo* é uma conta do Intune que pode ser usada para registrar vários dispositivos compartilhados usando o aplicativo de Portal da Empresa.
  > [!div class="button"]   [Windows >](../deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [Android >](../deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [iOS >](#shared-ios-device-enrollment)

### Registro de dispositivo iOS compartilhado

O método preferido de registro para dispositivos iOS da empresa compartilhados depende de como você comprar e gerenciar esses dispositivos:

  - **DEP (Programa de Registro do Dispositivo) da Apple**: dispositivos iOS podem ser comprados ou gerenciados com o DEP com um perfil de registro. Quando os usuários ligam seus dispositivos pela primeira vez, o dispositivo baixa o perfil de DEP e registra-se com ele
  - **Apple Configurator em um Mac (Mac)**: o Apple Configurator é um aplicativo da Apple que é executado em um computador Mac. Você pode conectar dispositivos iOS ao Mac com um cabo USB para instalar um perfil de registro no dispositivo. Se você puder redefinir os dispositivos para os padrões de fábrica, use o Assistente de Configuração. Se você não quiser redefinir os dispositivos para os padrões de fábrica, use o Registro direto.
  - **Nenhum deles**: se você não puder ou não quiser usar os métodos de DEP ou Apple Configurator, use o gerenciador de registro de dispositivo do Intune.

  **Escolha:**
    > [!div class="button"]      [Registro DEP >](../deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Mac >](../deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Registro direto >](../deploy-use/ios-direct-enrollment-in-microsoft-intune)  

  > [!div class="button"]     [Registro DEM >](../deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

**Usuários individuais**: -dispositivos da empresa que são concedidos a usuários individuais precisam ser controlados como ativos da empresa, permitindo ainda aos usuários acessar email e dados como dispositivos pessoais. Os métodos de registro recomendados dependem da plataforma dos dispositivos.

  - **Dispositivos com Android e Windows**: importando os números do IMEI (identidade internacional de equipamentos móveis) dos dispositivos da empresa, você poderá marcá-los como dispositivos da empresa no Intune. Os usuários podem registrar seus dispositivos como um dispositivos pessoal instalando o Portal da Empresa para acessar os recursos da empresa como email, aplicativos e dados.
  > [!div class="button"]   [Marcar com o IMEI >](../deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  - **Dispositivos iOS**: dispositivos iOS compartilhados podem ser gerenciados de três maneiras.  **Como você registrará seus dispositivos iOS compartilhados?**

    - **DEP (Programa de Registro do Dispositivo) da Apple**: dispositivos iOS podem ser comprados ou gerenciados com o DEP com um perfil de registro. Quando os usuários ligam seus dispositivos pela primeira vez, ele baixa o perfil de DEP e registra-se de acordo com ele.
    > [!div class="button"]     [Registro DEP](../deploy-use/ios-device-enrollment-program-in-microsoft-intune).

    - **Apple Configurator em um Mac**: o Apple Configurator é um aplicativo da Apple que é executado em um computador Mac. Você pode conectar dispositivos iOS ao Mac com um cabo USB para instalar um perfil de registro no dispositivo. Se você puder redefinir os dispositivos para os padrões de fábrica, use o Assistente de Configuração.

    Se você não quiser redefinir os dispositivos para os padrões de fábrica, use o Registro direto.
    Se você puder redefinir os dispositivos para os padrões de fábrica, use o Assistente de Configuração.
    > [!div class="button"][Registro do Assistente de Configuração de iOS](../deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [!div class="button"][Registro direto do iOS](../deploy-use/ios-direct-enrollment-in-microsoft-intune).

    - **Nenhum deles**: se você não puder ou não quiser usar os métodos de registro do DEP ou o Apple Configurator, importando o IMEI (identidade internacional de equipamentos móveis) de dispositivos da empresa, você poderá marcá-los como dispositivos da empresa no Intune. Os usuários podem registrar seus dispositivos como um dispositivos pessoal instalando o Portal da Empresa para acessar os recursos da empresa como email, aplicativos e dados. > [!div class="button"][Marcar dispositivos com números do IMEI](../deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)


<!--HONumber=Jun16_HO2-->


