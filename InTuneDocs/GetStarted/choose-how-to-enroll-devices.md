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

## Os funcionários trazem seus próprios dispositivos ou recebem dispositivos fornecidos pela sua organização?

  **Dispositivos de usuários** – registro "BYOD" (Traga seu próprio dispositivo): os usuários podem instalar o aplicativo de Portal da Empresa do Intune em seu dispositivo e registrá-lo, obtendo acesso a recursos da empresa como email, aplicativos da empresa, dados da empresa e suporte.  
  > [!div class="button"]   [Registro BYOD >](..deploy-use/get-ready-to-enroll-devices-in-microsoft-intune)

  **Dispositivos da empresa**: COD (dispositivos da empresa) podem ser registrados de diversas maneiras, dependendo das necessidades da organização e dos tipos de dispositivos gerenciados. Próxima pergunta...

## Seus dispositivos da empresa são compartilhados ou têm usuários individuais?

**Dispositivos da empresa compartilhados**: esses dispositivos não tem um único usuário e geralmente não estão configurados para acessar email. Os exemplos incluem dispositivos de quiosque ou dispositivos orientados a tarefas que os usuários extraem de um pool, conforme necessário e depois retornam. Os métodos de registro recomendados dependem da plataforma dos dispositivos.

  - **Dispositivos com Android e Windows**: um *gerenciador de registro de dispositivo* é uma conta do Intune que pode ser usada para registrar vários dispositivos compartilhados usando o aplicativo de Portal da Empresa.
  > [!div class="button"]   [Gerenciador de registro de dispositivo >](../deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - **Dispositivos iOS**: dispositivos iOS compartilhados podem ser gerenciados de três maneiras.  **Como você registrará seus dispositivos iOS compartilhados?**

    - **DEP (Programa de Registro do Dispositivo) da Apple**: dispositivos iOS podem ser comprados ou gerenciados com o DEP com um perfil de registro. Quando os usuários ligam seus dispositivos pela primeira vez, o dispositivo baixa o perfil de DEP e registra-se com ele
    > [!div class="button"]     [Registro DEP >](../deploy-use/ios-device-enrollment-program-in-microsoft-intune)

    - **Apple Configurator em um Mac**: o Apple Configurator é um aplicativo da Apple que é executado em um computador Mac. Você pode conectar dispositivos iOS ao Mac com um cabo USB para instalar um perfil de registro no dispositivo. Se você puder redefinir os dispositivos para os padrões de fábrica, use o Assistente de Configuração. Se você não quiser redefinir os dispositivos para os padrões de fábrica, use o Registro direto.

    > [!div class="button"]     [Registro do assistente de configuração >](../deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) ou [Registro direto >](../deploy-use/ios-direct-enrollment-in-microsoft-intune)

    - **Nenhum deles**: se você não puder ou não quiser usar os métodos de DEP ou Apple Configurator, use o gerenciador de registro de dispositivo do Intune.
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


<!--HONumber=Jun16_HO1-->


