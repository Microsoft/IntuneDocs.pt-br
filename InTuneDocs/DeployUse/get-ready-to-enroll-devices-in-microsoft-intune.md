---
# required metadata

title: Preparar-se para registrar dispositivos no Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 44fd4af0-f9b0-493a-b590-7825139d9d40

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Prepare-se registrar dispositivos no Microsoft Intune
Para permitir que os funcionários registrem dispositivos móveis (incluindo Android, iOS, Windows Phone e computadores Windows) com o Intune, você deve habilitar o registro de dispositivo. Para permitir o registro você deve definir uma autoridade de gerenciamento de dispositivo móvel, configurar o Portal da Empresa do Intune, atribuir licenças e habilitar o registro para a plataforma do dispositivo.

## <a name="BKMK_Set_MDM_Authority"></a>Defina a autoridade de gerenciamento de dispositivos móveis
A autoridade MDM define o serviço de gerenciamento com permissão para gerenciar um conjunto de dispositivos. As opções para a autoridade MDM incluem o Intune e o Configuration Manager com Intune. Se você definir o Configuration Manager como a autoridade de gerenciamento, nenhum outro serviço poderá ser usado para gerenciamento de dispositivo móvel.

>[!IMPORTANT]
> Considere atentamente se você quer gerenciar dispositivos móveis usando apenas o Intune (serviço online) ou o System Center Configuration Manager com a integração com Intune (solução de software local com serviço online). Depois de configurada, a autoridade de gerenciamento de dispositivo móvel não poderá ser alterada.



1.  No [Console de administração do Microsoft Intune](http://manage.microsoft.com), clique em **Admin** &gt; **Gerenciamento de dispositivo móvel**.

2.  Na lista **Tarefas** , clique em **Configurar autoridade de gerenciamento de dispositivo móvel**. A caixa de diálogo **Definir autoridade MDM** é aberta.

    ![Definir a caixa de diálogo de autoridade de MDM](../media/intune-mdm-authority.png)

3.  O Intune solicita a confirmação de que você deseja o Intune como autoridade MDM. Marque a caixa de seleção e clique em **Sim** para usar o Microsoft Intune para gerenciar dispositivos móveis.

## Configurar o Portal da empresa do Intune e atribuir licenças
O Portal da empresa do Intune ajuda os usuários a acessarem recursos da empresa, como aplicativos, encontrar informações de suporte técnico e registrar e cancelar o registro de dispositivos. Antes de registrar dispositivos, você deve [Configurar o Portal da empresa](/intune/get-started/get-started-with-a-paid-subscription-to-microsoft-intune-step-7). Você também deve [atribuir licenças de usuário](/intune/get-started/get-started-with-a-paid-subscription-to-microsoft-intune-step-4) para permitir o acesso ao Intune.

## Configurar gerenciamento de dispositivo
Depois de configurar a autoridade MDM, você precisa configurar o gerenciamento de dispositivos para os sistemas operacionais aos quais sua organização quer dar suporte. As etapas necessárias para configurar o gerenciamento de dispositivos variam de acordo com o sistema operacional. Por exemplo, o SO do Android não requer nenhuma ação no console de administração do Intune. Por outro lado, o Windows e iOS exigem uma relação de confiança entre os dispositivos e o Intune para permitir o gerenciamento.

> [!div class="op_single_selector"]
- [Configurar o gerenciamento de Android com o Microsoft Intune](set-up-android-management-with-microsoft-intune.md)
- [Set up iOS and Mac management with Microsoft Intune](set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Configurar o gerenciamento do Windows Phone com o Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md)
- [Configurar o gerenciamento do dispositivo Windows com o Microsoft Intune](set-up-windows-device-management-with-microsoft-intune.md)

Você também pode:
 - Use a [conta de gerente de registro do dispositivo](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) para registrar vários dispositivos
 - [Especifique os dispositivos da empresa usando números IMEI](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) para ajudar a registrar dispositivos e a direcionar a política


<!--HONumber=May16_HO1-->


