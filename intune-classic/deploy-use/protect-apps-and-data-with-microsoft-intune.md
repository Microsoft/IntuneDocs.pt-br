---
title: Proteger os aplicativos e os dados
description: "Este tópico descreve os vários recursos e funcionalidades do Intune que estão disponíveis para ajudar a proteger os dados e aplicativos da sua empresa."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5c46e188-87eb-4ce2-b184-24809e8bf783
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 59168615548d3c7da8dc284476227ed0f01ceffe
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2017
---
# <a name="protect-apps-and-data-with-microsoft-intune"></a>Proteger aplicativos e dados com o Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

O Intune protege os dados da empresa por meio de várias camadas de tecnologia. Na camada de identidade, o acesso condicional protege o acesso aos serviços, permitindo o acesso somente de dispositivos gerenciados e compatíveis. Na camada de aplicativo do cliente, o MAM (Gerenciamento de aplicativos Móveis) protege contra a perda de dados impedindo que os dados sejam movidos para aplicativos ou locais de armazenamento não protegidos e apagando os dados quando um dispositivo é perdido ou roubado. Recomendamos usar essas duas camadas de proteção juntas para ajudar a proteger os dados, mantendo sua força de trabalho móvel produtiva.

A primeira etapa importante para a proteção de dados da empresa é implementar o acesso condicional. Para fazer isso, verifique se os dispositivos usados para acessar os dados estão usando proteções de segurança, como senhas fortes e criptografia e não estão desbloqueados. O Intune permite definir as condições que os dispositivos precisam cumprir para poderem acessar o email e os dados da empresa.

O [acesso condicional](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) é determinado por dois tipos de políticas que podem ser definidas no Intune:
- Você usa [políticas de conformidade](introduction-to-device-compliance-policies-in-microsoft-intune.md) para determinar a conformidade de um dispositivo. Elas avaliam as configurações e as condições, como:
  - PINs e senhas: é possível criar regras para exigir senhas para desbloquear um dispositivo, seus requisitos de complexidade e outras definições de senha.
  - Criptografia: você pode restringir o acesso a dispositivos criptografados.
  - Quando um dispositivo não está desbloqueado ou enraizado: o Intune pode detectar se um dispositivo registrado está desbloqueado. É possível definir a política para bloquear o acesso a tais dispositivos.
- Configure [políticas de acesso condicional](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) para um serviço específico como o Exchange Online ou no SharePoint Online. Para cada serviço, você pode definir a quais grupos de usuários essas políticas devem ser aplicadas. Por exemplo, você pode garantir que todos no departamento financeiro possam acessar apenas email de dispositivos registrados e compatíveis.

Proteger o acesso aos recursos da empresa é apenas o primeiro passo para proteger os dados da empresa. Você ainda precisa ser capaz de proteger os dados depois que eles tiverem sido acessados no dispositivo. O conteúdo agora pode ser copiado, movido, salvo em um local diferente ou compartilhado. O Intune resolve esse problema fornecendo a capacidade de restringir a movimentação dos dados, criando um conjunto de regras como:
- Bloquear a ação de copiar e colar ou impedir a transferência de dados fora do contexto de trabalho.
- Impedir backup para armazenamento em nuvem particular e impedir "Salvar como".
- Proteger o acesso a aplicativos exigindo PIN/senha ou credenciais corporativas.
- Fazer todos os links da Web serem abertos no Intune Managed Browser.

Esse conjunto de regras é denominado [políticas de MAM (Gerenciamento de Aplicativo Móvel)](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md). É possível aplicar políticas de MAM para aplicativos executados em dispositivos que podem ou não ser gerenciados por você.  

É possível proteger os dados da empresa usando políticas de MAM para dispositivos **registrados no Intune**, dispositivos **registrados e gerenciados por uma solução de gerenciamento de dispositivo móvel (MDM) de terceiros** ou um dispositivo **não registrado em nenhuma solução de MDM**, como dispositivos de funcionários.

Para associar um aplicativo a uma política de MAM, o aplicativo deve incorporar o SDK (Kit de Desenvolvimento de Software) do Microsoft Intune ou você pode usar a Ferramenta de Encapsulamento de Aplicativos.

Aplicativos como os do Microsoft Office têm o SDK interno do aplicativo do Intune. É possível ver a lista completa de aplicativos com suporte na [Galeria de aplicativos móveis do Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) na página de parceiros de aplicativos do Microsoft Intune. Escolha o aplicativo para ver os cenários e plataformas com suporte e se o aplicativo dá suporte a várias identidades.

Também é possível [habilitar seus aplicativos de linha de negócios personalizados](/intune/apps-prepare-mobile-application-management) para uso com políticas de MAM.

Além de restringir a movimentação dos dados, se um dispositivo for perdido ou roubado ou se o usuário não trabalhar mais para sua empresa, você poderá [apagar seletivamente os dados corporativos](wipe-managed-company-app-data-with-microsoft-intune.md), deixando apenas os dados pessoais.
