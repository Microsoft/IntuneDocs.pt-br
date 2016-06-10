---
# required metadata

title: Configurar o gerenciamento do Windows 10 Mobile e do Windows Phone com o Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f5615051-2dd1-453b-9872-d3fdcefb2cb8

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Configurar o gerenciamento do Windows 10 Mobile e do Windows Phone com o Microsoft Intune
Antes que você possa gerenciar dispositivos Windows 10 Mobile ou Windows Phone com o Microsoft Intune, os dispositivos devem ser capazes de se comunicar com o Intune. Para simplificar isso, você pode criar um registro DNS para que os usuários não precisem inserir o endereço do servidor. As etapas a seguir descrevem como simplificar o registro dos usuários.  

Para a maioria dos cenários, os usuários podem instalar o aplicativo do Portal da Empresa da Windows Store. Se gerenciar dispositivos Windows Phone 8.0 ou precisar implantar o Portal da Empresa em dispositivos Windows Phone, você também precisará baixar e assinar o aplicativo do Portal da Empresa. Consulte [Set up Windows Phone 8.0 management](set-up-windows-phone-8.0-management-with-microsoft-intune.md) (Configurar o gerenciamento do Windows Phone 8.0).

1.  **Configurar Intune** Se você ainda não o fez, prepare-se para o gerenciamento de dispositivo móvel ao [Configurar a autoridade de gerenciamento do dispositivo móvel](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority) como **Microsoft Intune** e configurando o MDM.

2.  **Definir um alias DNS para o endereço do servidor de registro** (opcional)

    Criar um alias DNS (tipo de registro CNAME) facilita para os usuários registrarem seus dispositivos. Se você não criar um alias DNS, os usuários deverão

  1.  Criar registros de recurso DNS **CNAME** para o domínio da sua empresa. Por exemplo, se o site de sua empresa for contoso.com, você precisará criar um CNAME no DNS que redirecione EnterpriseEnrollment.contoso.com para manage.microsoft.com. Se houver mais de um domínio verificado, crie um registro CNAME para cada domínio. Os registros de recurso CNAME devem conter as seguintes informações:

      |TYPE|Nome do host|Aponta para|TTL|
      |--------|-------------|-------------|-------|
      |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 hora|
      |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 hora|

      Alterações de registro DNS podem levar até 72 horas para serem propagadas. Você não pode verificar a alteração do DNS no Intune até que o registro DNS seja propagado.

      **EnterpriseEnrollment-s.manage.microsoft.com** – dá suporte ao redirecionamento para o serviço Intune com reconhecimento de domínio por meio do nome de domínio do email

      **EnterpriseRegistration.windows.net** – dá suporte a dispositivos Windows 8.1 e Windows 10 Mobile que serão registrado no Azure Active Directory usando sua conta corporativa ou de estudante

    2.  No [console do administrador do Intune](http://manage.microsoft.com), clique em **Administração** &gt; **Gerenciamento de dispositivo móvel** &gt; **Windows Phone**.

      ![Caixa de diálogo Configurar o gerenciamento de dispositivo móvel para Windows](../media/windows-device-enrollment.png)

    3.  Digite a URL do domínio verificado do site na empresa na caixa **Especificar um Nome de Domínio Verificado** e clique em **Testar Detecção Automática**.



Nenhum trabalho adicional é necessário, a menos que você vá implantar o Portal da Empresa em dispositivos.  As etapas 2 e 3 no console do administrador podem ser ignoradas com segurança.


<!--HONumber=May16_HO2-->


