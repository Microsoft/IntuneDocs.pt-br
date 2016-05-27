---
# required metadata

title: Restringir o acesso a email e serviços do O365 | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: c564d292-b83b-440d-bf08-3f5b299b7a5e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Restringir o acesso a email e serviços do O365 com o Microsoft Intune
Você pode restringir o acesso a seus emails corporativos e serviços de O365 com acesso condicional do Intune. Essa funcionalidade de acesso condicional do Intune permite que você certifique-se de que o acesso ao seu email da empresa e serviços O365 seja restrito aos dispositivos que são compatíveis com as regras que você definir.
## Como funciona o acesso condicional?
Configurações de política de conformidade são usadas para avaliar a conformidade do dispositivo. A política de acesso condicional usa a avaliação para restringir ou permitir o acesso a um serviço específico. Quando uma política de acesso condicional é usada em combinação com uma política de conformidade, apenas os dispositivos compatíveis poderão acessar o serviço.

Tenha em mente que o usuário que está usando o dispositivo também deve ter uma política de conformidade implantada para que o dispositivo seja avaliado para fins de conformidade.
Se nenhuma política de conformidade for implantada para o usuário, o dispositivo será tratado como compatível e nenhuma restrição de acesso será aplicada.

Quando dispositivos não atendem às condições definidas na política, o usuário final é guiado pelo processo de registro do dispositivo e correção do problema que está impedindo o dispositivo de ser compatível.

Um fluxo típico do acesso condicional:

![O diagrama mostra os pontos de decisão usados para determinar se um dispositivo tem acesso permitido ou bloqueado acesso a um serviço](./media/ConditionalAccess4.png)

## Como configurar o acesso condicional?
Use o acesso condicional para gerenciar o acesso ao Microsoft **Exchange Local**, **Exchange Online**, **Exchange Online Dedicado**, **SharePoint Online** e **Skype for Business Online**.

Para configurar o acesso condicional, configure uma política de conformidade do dispositivo e uma política de acesso condicional.

A política de conformidade inclui configurações como senha, criptografia e se um dispositivo tem ou não jailbreak. O dispositivo deve atender a essas regras para ser considerado compatível.

Você pode definir uma política de acesso condicional para restringir o acesso com base em:
- Status de conformidade do dispositivo.
- Plataforma em execução no dispositivo.
- Tipos de aplicativos usados para acessar os serviços.

Ao contrário de outras políticas do Intune, você não implanta políticas de acesso condicional. Em vez disso, depois de configurar a política e selecionar os usuários que devem ter a política, a política é aplicada a todos os usuários de destino. Quando um usuário é afetado por uma política, cada dispositivo que ele usa deve ser compatível para que possa acessar os recursos.


## Próximas etapas
1. [Saiba mais sobre a política de conformidade do dispositivo e como ela funciona ](introduction-to-device-compliance-policies-in-microsoft-intune.md)

2. [Criar uma política de conformidade](create-a-device-compliance-policy-in-microsoft-intune.md)

2.  Criar uma política de acesso condicional para um dos seguintes:
> [!div class="op_single_selector"]
  - [Criar uma política de acesso condicional para o Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [Criar uma política de acesso condicional para o Exchange Local](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [Criar uma política de acesso condicional para o novo Exchange Online Dedicado](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [Criar uma política de acesso condicional para o Exchange Online Dedicado herdado](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [Criar política de acesso condicional para o SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  - [Criar política de acesso condicional para o Skype for Business Online](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)


<!--HONumber=May16_HO1-->

