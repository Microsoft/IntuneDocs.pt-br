---
title: Defina a autoridade de gerenciamento de dispositivo móvel
titlesuffix: Microsoft Intune
description: Defina a autoridade de gerenciamento de dispositivo móvel no Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f903e9dfe5fb30f45806aac5694171814492f2e
ms.sourcegitcommit: 0f1a5d6e577915d2d748d681840ca04a0a2604dd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2018
---
# <a name="set-the-mobile-device-management-authority"></a>Defina a autoridade de gerenciamento de dispositivo móvel

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A configuração de autoridade de gerenciamento de dispositivo móvel (MDM) determina como você gerenciar seus dispositivos. Como administrador de TI, você deverá definir uma autoridade MDM antes que os usuários possam registrar dispositivos para gerenciamento.

As configurações possíveis são:

- **Intune Autônomo** – Gerenciamento apenas na nuvem, que você pode definir usando o Portal do Azure. Inclui o conjunto completo de recursos que o Intune oferece. [Definir a autoridade MDM no console do Intune](#set-mdm-authority-to-intune).

- **Intune Híbrido** – Integração da solução de nuvem Intune com o System Center Configuration Manager. Você configura o Intune usando o console do Configuration Manager. [Definir a autoridade do MDM no Configuration Manager](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).

- **Gerenciamento de dispositivo móvel para o Office 365** – Integração do Office 365 com a solução de nuvem do Intune. Configure o Intune do seu Centro de Administração do Office 365. Inclui um subconjunto dos recursos que estão disponíveis com o Intune Autônomo. Defina a autoridade MDM no Centro de administração do Office 365.

> [!IMPORTANT]
> No Configuration Manager versão 1610 ou posterior e no Microsoft Intune versão 1705, você altera a autoridade de MDM sem precisar contatar o Suporte da Microsoft e sem cancelar o registro e registrar novamente os dispositivos gerenciados existentes. Para obter detalhes, consulte [O que fazer se você escolher a configuração incorreta de autoridade de MDM](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting).

## <a name="set-mdm-authority-to-intune"></a>Definir a autoridade de MDM como o Intune

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Selecione a faixa laranja para abrir a configuração **Autoridade de Gerenciamento de Dispositivo Móvel**.
4. Em **Autoridade de Gerenciamento de Dispositivo Móvel**, escolha sua autoridade de MDM entre as seguintes opções:
   - **Autoridade de MDM do Intune**
   - **Autoridade de MDM do Configuration Manager**
   - **Nenhum**

   ![Captura da tela da definição de autoridade de gerenciamento de dispositivo móvel do Intune](media/set-mdm-auth.png)

   Uma mensagem indica que você configurou com êxito sua autoridade MDM Intune.

## <a name="enable-device-enrollment"></a>Habilitar registro de dispositivo

Com o Intune definido como sua autoridade de MDM, os usuários podem registrar dispositivos pessoais e obter acesso a recursos como email das seguintes maneiras: instalando o Portal da Empresa (iOS, macOS e Android), adicionando as credenciais de trabalho (Windows) ou acessando o site do Portal da Empresa (iOS, Android, macOS).

As diferentes plataformas a seguir têm os seguintes requisitos para habilitar ou simplificar o registro:
- **iOS** – (obrigatório) [obter um Apple MDM Push Certificate](apple-mdm-push-certificate-get.md) e, em seguida [habilitar o registro para dispositivos iOS da empresa](ios-enroll.md) (opcional).
- **Android** – (opcional) [habilitar perfis de trabalho do Android](android-enroll.md)
- **Windows** – (opcional) habilitar o [Registro automático](windows-enroll.md) ou o [Registro em massa](windows-bulk-enroll.md)
- **macOS** – (obrigatório) [Obter um Certificado Push de MDM da Apple](apple-mdm-push-certificate-get.md).

### <a name="workflow-of-intune-administration-ui"></a>Fluxo de trabalho da interface do usuário da administração do Intune
Quando o gerenciamento de dispositivo Android ou Apple está habilitado, o Intune envia informações do dispositivo e do usuário para integração com esses serviços de terceiros, possibilitando que eles gerenciem os respectivos dispositivos.

Os cenários que adicionam um consentimento para compartilhar dados estão inclusos quando:
- Você habilita o Android for Work.
- Você habilita e carrega Apple MDM Push Certificates.
- Você habilita qualquer um dos serviços da Apple, como o Programa de registro de dispositivos, o School Manager ou o Volume Purchase Program.

Em cada caso, a autorização é estritamente relacionada à execução de um serviço de gerenciamento de dispositivo móvel, como a confirmação de que um administrador de TI autorizou dispositivos Google ou Apple a se registrarem. A documentação que trata das informações que serão compartilhadas quando os novos fluxos de trabalho forem ativados está disponível nos seguintes locais:
- [Dados enviados pelo Intune ao Google](https://aka.ms/Data-intune-sends-to-google)
- [Dados enviados pelo Intune à Apple](https://aka.ms/data-intune-sends-to-apple)

Para obter mais informações sobre a conformidade de GDPR da Microsoft, veja [Central de Confiabilidade – Avaliar sua conformidade com GDPR](https://aka.ms/trust_center_info).

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Limpeza de dispositivo móvel após a expiração do certificado MDM

O certificado do MDM é renovado automaticamente quando os dispositivos móveis estão se comunicando com o serviço Intune. Se os dispositivos móveis forem apagados ou se eles não conseguirem se comunicar com o serviço Intune por um certo período, o certificado do MDM não será renovado. O dispositivo é removido do Portal do Azure 180 dias após a expiração do certificado do MDM.
