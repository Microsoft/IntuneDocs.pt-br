---
title: Registro de administrador de dispositivos Android no Microsoft Intune
titleSuffix: ''
description: Registre dispositivos Android no Intune usando o registro de administrador de dispositivos.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a72d3a16c5180b51fcc019d726a498e0d15ad1d3
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72503397"
---
# <a name="android-device-administrator-enrollment"></a>Registro de administrador de dispositivos Android

O administrador de dispositivos Android (às vezes chamado de gerenciamento Android "herdado" e lançado com o Android 2.2) é uma maneira de gerenciar dispositivos Android. No entanto, a funcionalidade de gerenciamento aprimorada já está disponível com o [Android Enterprise](https://www.android.com/enterprise/management/) (lançado com o Android 5.0). Em um esforço para migrar para um gerenciamento de dispositivo moderno, mais avançado e mais seguro, o Google tem reduzido o suporte do administrador de dispositivos em novos lançamentos do Android.

Portanto, para evitar essa funcionalidade reduzida, desaconselhamos o registro de novos dispositivos usando o processo do administrador de dispositivos descrito abaixo.

Pelas mesmas razões, também recomendamos que você migre dispositivos do gerenciamento de administrador de dispositivos se os dispositivos forem atualizados para o Android 10. 

Para obter mais informações sobre o suporte do Intune para o administrador de dispositivos Android, confira a [seção Avisos](../fundamentals/whats-new.md#decreasing-support-for-android-device-administrator).

Se você ainda quiser que os usuários registrem os dispositivos Android no gerenciamento de administrador de dispositivos, prossiga para a próxima seção.  


> [!Note]  
> O Android 10 e versões posteriores não terão suporte no gerenciamento de dispositivo móvel híbrido (MDM híbrido; gerenciado pelo Intune com o console do System Center Configuration Manager) porque o MDM híbrido será retirado de serviço em 1º de setembro de 2019. Se você ainda estiver usando o MDM híbrido, deverá migrar para o Intune autônomo o mais breve possível. Entre em contato com o suporte se precisar de ajuda na migração. Para obter mais informações, confira [Migrar do Gerenciamento de Dispositivo Móvel Híbrido para o Intune no Azure](https://aka.ms/hybrid_notification).

Para obter mais informações sobre os recursos do Android Enterprise do Google, confira estes artigos:
- [Diretrizes do Google para a migração do administrador de dispositivos para o Android Enterprise](http://static.googleusercontent.com/media/android.com/en/enterprise/static/2016/pdfs/enterprise/Android-Enterprise-Migration-Bluebook_2019.pdf)
- [Documentação do Google sobre o plano para substituir a API do administrador de dispositivos](https://developers.google.com/android/work/device-admin-deprecation)


## <a name="set-up-device-administrator-enrollment"></a>Configurar o registro do administrador de dispositivos

Por padrão, o Intune permite o registro de dispositivos Android com recursos de administrador de dispositivos.

1. Para se preparar para gerenciar dispositivos móveis, é necessário definir a autoridade MDM (gerenciamento de dispositivo móvel) como **Microsoft Intune**. Consulte [Definir a autoridade MDM](../fundamentals/mdm-authority-set.md) para obter instruções. Você define esse item apenas uma vez, na primeira vez que configurar o Intune para gerenciamento de dispositivo móvel.
2. Acesse **Intune** > **Registro de dispositivo** > **Registro do Android** > **Dispositivos pessoais e corporativos com privilégios de administração de dispositivos** > **Usar o administrador do dispositivo para gerenciar dispositivos**.
3. [Informe aos usuários como registrar seus dispositivos](/intune-user-help/enroll-your-device-in-intune-android).  

Depois que os usuários registrarem os dispositivos, você poderá começar a gerenciar esses dispositivos no Intune, por exemplo, [atribuindo políticas de conformidade](../protect/compliance-policy-create-android.md), [gerenciando aplicativos](../apps/app-management.md) e muito mais.

Para obter informações sobre outras tarefas, consulte estes artigos:
- [Recursos sobre a experiência do usuário final com o Microsoft Intune](../fundamentals/end-user-educate.md)
- [Usando seu dispositivo Android com o Intune](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)


## <a name="block-device-administrator-enrollment"></a>Bloquear o registro de administrador de dispositivos
Para bloquear dispositivos do administrador de dispositivos Android ou para bloquear apenas dispositivos do administrador de dispositivos Android de propriedade pessoal, confira [Definir restrições de tipo de dispositivo](enrollment-restrictions-set.md).



## <a name="next-steps"></a>Próximas etapas
- [Atribuir políticas de conformidade](../protect/compliance-policy-create-android.md)
- [Gerenciar aplicativos](../apps/app-management.md)