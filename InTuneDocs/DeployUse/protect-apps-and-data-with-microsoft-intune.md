---
title: Proteger aplicativos e dados | Microsoft Intune
description: 
keywords: "Este tópico descreve os vários recursos e funcionalidades do Intune que estão disponíveis para ajudar a proteger os dados e aplicativos da sua empresa."
author: karthikaraman
manager: jeffgilb
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5c46e188-87eb-4ce2-b184-24809e8bf783
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c72c8e1a764af73ba4d421ca6637ee91ab7bca0a
ms.openlocfilehash: c4ee5b25bd737c357e58db6420e69beabf66a74d


---

# Proteger aplicativos e dados com o Microsoft Intune


O Intune protege os dados da empresa por meio de várias camadas de tecnologia.  Na camada de identidade, o acesso condicional protege o acesso aos serviços, permitindo o acesso somente de dispositivos gerenciados e compatíveis.  Na camada de aplicativo do cliente, o MAM (Gerenciamento de aplicativos Móveis) protege contra a perda de dados impedindo que os dados sejam movidos para aplicativos ou locais de armazenamento não protegidos e apagando os dados quando um dispositivo é perdido ou roubado.  Essas duas camadas de proteção devem ser usadas juntas para proteger os dados, mantendo sua força de trabalho móvel produtiva.

A primeira etapa importante para a proteção de dados da empresa é implementar o acesso condicional, certificando-se de que os dispositivos usados para acessar os dados usem proteções de segurança como senhas, criptografia e não sejam desbloqueados. O Microsoft Intune oferece a capacidade de definir as condições que os dispositivos precisam cumprir para poderem acessar o email e os dados da empresa.

O [acesso condicional](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) é determinado por dois tipos de políticas que podem ser definidas no Intune:
- As [políticas de conformidade](introduction-to-device-compliance-policies-in-microsoft-intune.md) determinam a conformidade de um dispositivo. Elas avaliam as configurações e as condições, como:
  - PINs e senhas: você pode criar regras para exigir senhas para desbloquear um dispositivo, seus requisitos de complexidade e outras definições de senha.
  - Criptografia: você pode restringir o acesso a dispositivos criptografados.
  - O dispositivo não está desbloqueado ou enraizado: o Intune pode detectar se um dispositivo registrado está desbloqueado e você pode definir a política para bloquear o acesso a tais dispositivos.
- [Políticas de acesso condicional](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) são configuradas para um serviço específico como o Exchange Online ou no SharePoint Online. Para cada serviço, você pode definir a quais grupos de usuários essas políticas devem ser aplicadas. Por exemplo, você pode garantir que todos no departamento financeiro possam acessar apenas email de dispositivos registrados e compatíveis.

Proteger o acesso aos recursos da empresa é apenas o primeiro passo para proteger os dados da empresa. Você ainda precisa ser capaz de proteger os dados depois que eles tiverem sido acessados no dispositivo. O conteúdo agora pode ser copiado, movido, salvo em um local diferente ou compartilhado. O Intune resolve esse problema fornecendo a capacidade de restringir a movimentação dos dados, criando um conjunto de regras como:
- Bloqueie a ação de copiar e colar ou impeça a transferência de dados fora do contexto de trabalho.
- Impeça backups para armazenamento em nuvem particular, impedindo a ação Salvar como.
- Proteja o acesso a aplicativos exigindo PIN/senha ou credenciais corporativas.
- Faça todos os links da Web serem abertos no Navegador Gerenciado do Intune.

Esse conjunto de regras é denominado [políticas de MAM (Gerenciamento de Aplicativo Móvel)](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).  Políticas de MAM podem ser aplicadas a aplicativos em execução em dispositivos que podem ou não ser gerenciados por você.  

Você pode proteger os dados da empresa usando políticas de MAM para dispositivos **registrados no Intune**, dispositivos **registrados e gerenciados por MDM de terceiros** ou um dispositivo **não registrado em nenhuma solução de MDM**, como dispositivos de funcionários.

Para associar um aplicativo a uma política de MAM, o aplicativo deve incorporar o SDK (Kit de Desenvolvimento de Software) do Microsoft Intune ou usar a Ferramenta de encapsulamento de aplicativos.

Aplicativos como aqueles do Microsoft Office têm o SDK interno do aplicativo. A lista completa de aplicativos com suporte pode ser encontrada na [galeria de aplicativos móveis do Microsoft Intune](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) na página de parceiros de aplicativos do Microsoft Intune. Escolha aplicativo para ver os cenários e plataformas com suporte e se o aplicativo dá suporte a várias identidades ou não.

Você também pode [habilitar seus aplicativos de linha de negócios personalizados](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md) para uso com políticas de MAM.

Além de restringir a movimentação dos dados, se um dispositivo for perdido ou roubado ou se o usuário não trabalhar mais para sua empresa, você poderá [apagar seletivamente os dados corporativos](wipe-managed-company-app-data-with-microsoft-intune.md), deixando apenas os dados pessoais.



<!--HONumber=Jul16_HO3-->


