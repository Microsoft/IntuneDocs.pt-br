---
title: Registrar dispositivos Android no Intune
titlesuffix: Microsoft Intune
description: Saiba como registrar dispositivos Android no Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3b7652c8c4f471a0a0c32da23d8ac1859e84eb13
ms.sourcegitcommit: e8aaa0955d13fa6c9d5f35a730ad06509ce88d0b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39400344"
---
# <a name="enroll-android-devices"></a>Registrar dispositivos Android

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Como administrador do Intune, você pode gerenciar os seguintes dispositivos Android:
- Dispositivos Android, incluindo dispositivos Samsung KNOX Standard.
- Dispositivos Android Enterprise, incluindo [dispositivos de perfil de trabalho Android](#enable-enrollment-of-android-for-work-devices) e dispositivos de quiosque Android.

Dispositivos que executam o Samsung Knox Standard são compatíveis para o gerenciamento de vários usuários pelo Intune. Isso significa que os usuários finais podem entrar ou sair de um dispositivo com as credenciais do Azure AD. O dispositivo é gerenciado centralizadamente, independentemente de estar ou não em uso. Quando os usuários entram, eles têm acesso a aplicativos e, além disso, obtêm todas as políticas aplicadas a eles. Quando os usuários saem, todos os dados do aplicativo são removidos.

## <a name="prerequisite"></a>Pré-requisito

Para se preparar para gerenciar dispositivos móveis, é necessário definir a autoridade MDM (gerenciamento de dispositivo móvel) como **Microsoft Intune**. Consulte [Definir a autoridade MDM](mdm-authority-set.md) para obter instruções. Você define esse item apenas uma vez, na primeira vez que configurar o Intune para gerenciamento de dispositivo móvel.

## <a name="set-up-android-enrollment"></a>Configurar registro do Android

Por padrão, o Intune é configurado para permitir o registro de dispositivos Android e Samsung Knox Standard. Depois de cumprir o pré-requisito, os administradores simplesmente precisam [informar aos usuários como eles devem registrar os dispositivos](/intune-user-help/enroll-your-device-in-intune-android).

Depois que os usuários registrarem os dispositivos, você poderá começar a gerenciar esses dispositivos no Intune, por exemplo, [atribuindo políticas de conformidade](compliance-policy-create-android.md), [gerenciando aplicativos](app-management.md) e muito mais.

Para obter informações sobre outras tarefas, consulte estes artigos:

- [Recursos sobre a experiência do usuário final com o Microsoft Intune](end-user-educate.md)
- [Usando seu dispositivo Android com o Intune](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

Para bloquear o registro de dispositivos Android ou para bloquear o registro somente de dispositivos Android de propriedade pessoal, consulte [Definir restrições de tipo de dispositivo](enrollment-restrictions-set.md).

## <a name="set-up-android-enterprise-enrollment"></a>Configurar o registro do Android Enterprise

O Android Enterprise é um conjunto de recursos e serviços do dispositivo Android que separam aplicativos e dados pessoais de um perfil de trabalho que contém dados e aplicativos de trabalho. Os dispositivos Android Enterprise incluem dispositivos de perfil de trabalho e dispositivos de quiosque. 

Para configurar o registro de dispositivos Android Enterprise, primeiro você precisa [conectar o Android Enterprise ao Intune](connect-intune-android-enterprise.md). Depois de concluir essa etapa, você poderá:

[Configurar registros de perfil de trabalho Android](android-work-profile-enroll.md)
[Configurar registros de quiosque do Android](android-kiosk-enroll.md)

## <a name="end-user-experience-when-enrolling-a-samsung-knox-device"></a>Experiência do usuário final ao registrar um dispositivo Samsung Knox
Há várias considerações ao registrar dispositivos Samsung Knox:
-   Mesmo se nenhuma política exigir um PIN, o dispositivo precisará ter pelo menos um PIN de um a quatro dígitos para o registro. Se o dispositivo não tiver um PIN, o usuário será solicitado a criar um.
-   Não há interação do usuário para os WPJ (Certificados Workplace Join).
-   O usuário é solicitado a dar informações de Registro do Serviço e sobre o que o aplicativo pode fazer.
-   O usuário é solicitado a dar informações de Registro do Knox e sobre o que o Knox pode fazer.
-   Se uma Política de Criptografia for imposta, os usuários precisarão definir uma senha complexa de seis caracteres como a senha do dispositivo.
-   Não há prompts adicionais do usuário para instalar certificados enviados por push por um serviço para Acesso a Recursos da Empresa.
- Alguns dispositivos Knox mais antigos solicitarão que o usuário forneça certificados adicionais usados para Acesso a Recursos da Empresa.
- Se um dispositivo Samsung Mini falhar em instalar o WPJ com os erros **Certificado Não Encontrado** ou **Não é Possível Registrar o Dispositivo**, instale as Atualizações de Firmware Samsung mais recentes.
