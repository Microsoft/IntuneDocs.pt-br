---
title: Registrar dispositivos Android no Intune
titleSuffix: Microsoft Intune
description: Saiba como registrar dispositivos Android no Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/31/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 363a7d0ef32aee0c21c6e5cecbd55cc3087f4613
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2019
ms.locfileid: "59568668"
---
# <a name="enroll-android-devices"></a>Registrar dispositivos Android

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Como administrador do Intune, você pode gerenciar os seguintes dispositivos Android:
- Dispositivos Android, incluindo dispositivos Samsung KNOX Standard.
- Dispositivos Android Enterprise, incluindo:
    - **Dispositivos Android Enterprise de perfil de trabalho**: Dispositivos pessoais cujo acesso a dados corporativos foi permitido. Administradores podem gerenciar contas de trabalho, aplicativos e dados. Dados pessoais no dispositivo são mantidos separados de dados de trabalho e os administradores não controlam as configurações ou dados pessoais. 
    - **Dispositivos Android Enterprise dedicados**: Dispositivos de propriedade corporativa para único uso, como a sinalização digital, tíquete de impressão ou gerenciamento de estoque. Os administradores bloqueiam o uso de um dispositivo a um conjunto limitado de aplicativos e links da Web. Isso também impede que os usuários adicionem outros aplicativos ou executem outras ações no dispositivo.
    - **Dispositivos Android Enterprise totalmente gerenciados**: Dispositivos de propriedade corporativa para único uso, usados exclusivamente para uso profissional e não pessoal. Os administradores podem gerenciar todo o dispositivo e impor controles de política não disponíveis para perfis de trabalho. 

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

O Android Enterprise oferece um conjunto de opções de registro que fornece aos usuários os recursos mais seguros e atualizados. As opções de registro do Android Enterprise incluem dispositivos de perfil de trabalho, dispositivos totalmente gerenciados e dispositivos dedicados.

- [Configurar registros de perfil de trabalho Android Enterprise](android-work-profile-enroll.md)
- [Configurar registros de dispositivo dedicados Android Enterprise](android-kiosk-enroll.md)
- [Configurar registro de dispositivos totalmente gerenciados Android Enterprise](android-fully-managed-enroll.md)

## <a name="end-user-experience-when-enrolling-a-samsung-knox-device"></a>Experiência do usuário final ao registrar um dispositivo Samsung Knox

Dispositivos Samsung Knox Standard são compatíveis para o gerenciamento de vários usuários pelo Intune. Isso significa que os usuários finais podem entrar ou sair de um dispositivo com as credenciais do Azure AD. O dispositivo é gerenciado centralizadamente, independentemente de estar ou não em uso. Quando os usuários entram, eles têm acesso a aplicativos e, além disso, obtêm todas as políticas aplicadas a eles. Quando os usuários saem, todos os dados do aplicativo são removidos.

Há várias considerações ao registrar dispositivos Samsung Knox:
-   Mesmo se nenhuma política exigir um PIN, o dispositivo precisará ter pelo menos um PIN de um a quatro dígitos para o registro. Se o dispositivo não tiver um PIN, o usuário será solicitado a criar um.
-   Não há interação do usuário para os WPJ (Certificados Workplace Join).
-   O usuário é solicitado a dar informações de Registro do Serviço e sobre o que o aplicativo pode fazer.
-   O usuário é solicitado a dar informações de Registro do Knox e sobre o que o Knox pode fazer.
-   Se uma Política de Criptografia for imposta, os usuários precisarão definir uma senha complexa de seis caracteres como a senha do dispositivo.
-   Não há prompts adicionais do usuário para instalar certificados enviados por push por um serviço para Acesso a Recursos da Empresa.
- Alguns dispositivos Knox mais antigos solicitarão que o usuário forneça certificados adicionais usados para Acesso a Recursos da Empresa.
- Se um dispositivo Samsung Mini falhar em instalar o WPJ com os erros **Certificado Não Encontrado** ou **Não é Possível Registrar o Dispositivo**, instale as Atualizações de Firmware Samsung mais recentes.

## <a name="next-steps"></a>Próximas etapas

- [Configurar registros de perfil de trabalho Android Enterprise](android-work-profile-enroll.md)
- [Configurar registros de dispositivo dedicados Android Enterprise](android-kiosk-enroll.md)
- [Configurar registro de dispositivos totalmente gerenciados Android Enterprise](android-fully-managed-enroll.md)
