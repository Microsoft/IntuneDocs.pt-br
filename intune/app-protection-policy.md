---
title: "O que são políticas de proteção do aplicativo"
titleSuffix: Azure portal
description: "Use este tópico para saber como proteger os dados da empresa com as políticas de Proteção de Aplicativo do Microsoft Intune."
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 01/19/2018
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1c086943-84a0-4d99-8295-490a2bc5be4b
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0ee95990afa08aa55e0f9101329b31bd8b3041f4
ms.sourcegitcommit: 6d69403266dbcb31c879432719798935c94917fa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2018
---
# <a name="what-are-app-protection-policies"></a>O que são políticas de proteção de aplicativo?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

As políticas de proteção de aplicativo do Microsoft Intune ajudam a proteger os dados da empresa e evitar a perda de dados.

## <a name="how-you-can-protect-app-data"></a>Como proteger os dados do aplicativo
Os funcionários usam dispositivos móveis para tarefas de pessoais e corporativas.  Embora seja necessário certificar-se que seus funcionários sejam produtivos, você também deseja evitar a perda de dados, intencional ou acidental.  Além disso, é útil ter a capacidade de proteger os dados corporativos acessados usando dispositivos mesmo caso eles não sejam gerenciados por você.

Você pode usar as políticas de proteção de aplicativo do Intune para ajudar a proteger os dados da sua empresa. Como as políticas de proteção de aplicativo do Intune podem ser usadas **independentemente de qualquer solução de MDM (gerenciamento de dispositivo móvel)**, você pode usá-las para proteger os dados da sua empresa registrando ou não os dispositivos em uma solução de gerenciamento de dispositivo. Implementando as **políticas de nível de aplicativo**, você pode restringir o acesso aos recursos da empresa e manter os dados dentro do alcance do seu departamento de TI.

As políticas de proteção de aplicativo podem ser configuradas para aplicativos em execução em dispositivos que são:

- **Registrados com o Microsoft Intune:** os dispositivos nessa categoria normalmente são dispositivos corporativos.

-   **Registrados em uma solução de MDM (gerenciamento de dispositivo móvel) de terceiros:** os dispositivos nessa categoria normalmente são dispositivos corporativos.

  > [!NOTE]
  > Políticas de gerenciamento de aplicativo móvel não devem ser usadas com o gerenciamento de aplicativos móveis de terceiros ou com soluções seguras de contêiner.

-   **Não registrados em nenhuma solução de gerenciamento de dispositivo móvel:** os dispositivos nessa categoria normalmente são dispositivos de funcionários que não são gerenciados ou registrados no Intune ou outras soluções de MDM.

> [!IMPORTANT]
> Você pode criar políticas de gerenciamento para aplicativos móveis do Office que se conectam aos serviços do Office 365. As políticas de proteção de aplicativo não são compatíveis com aplicativos que se conectam aos serviços locais do Exchange ou do SharePoint.

**Os principais benefícios do uso de políticas de proteção de aplicativo são**

-   Proteger os dados da empresa no nível do aplicativo.  Como o gerenciamento de aplicativos móveis não requer gerenciamento de dispositivos, você pode proteger os dados da empresa em dispositivos gerenciados e não gerenciados. O gerenciamento concentra-se na identidade do usuário, o que elimina a necessidade de gerenciar dispositivos.

-   A produtividade do usuário final não é afetada e as políticas não são aplicadas ao usar o aplicativo em um contexto pessoal.  As políticas são aplicadas somente em um contexto corporativo, proporcionando assim a capacidade de proteger dados da empresa sem tocar em dados pessoais.

Há benefícios adicionais em usar MDM com políticas de proteção de aplicativo, e as empresas podem usar ambos (políticas de proteção de aplicativo com e sem MDM) ao mesmo tempo. Por exemplo, um funcionário pode usar um telefone da empresa e um tablet particular.  Nesse caso, o telefone da empresa é registrado no MDM e protegido pelas políticas de proteção de aplicativo e o dispositivo pessoal é protegido somente pelas políticas de proteção de aplicativo.

- **O MDM garante que o dispositivo estará protegido**.  Por exemplo, você pode exigir um PIN acessar o dispositivo ou pode implantar aplicativos gerenciados para o dispositivo. Você também pode implantar aplicativos em dispositivos por meio da solução MDM, para conferir mais controle sobre o gerenciamento de aplicativo.

- **Políticas de proteção de aplicativo garantem que as proteções de camada de aplicativo estejam em vigor**. Por exemplo, você pode exigir um PIN abrir um aplicativo em um contexto corporativo, se os dados puderem ser compartilhados entre aplicativos ou impedindo que os dados de aplicativo da empresa sejam salvos em um local de armazenamento pessoal.


### <a name="supported-platforms-for-app-protection-polices"></a>Plataformas com suporte para as políticas de proteção de aplicativo
O suporte da plataforma de políticas de Proteção de Aplicativo do Intune está alinhado ao suporte da plataforma de aplicativo do Office. Para obter detalhes, consulte [Requisitos do sistema para o Office](https://products.office.com/en-US/office-system-requirements).

Não há suporte para dispositivos Windows. No entanto, quando registra dispositivos Windows 10 no Intune, você pode usar a Proteção de Informações do Windows, que oferece funcionalidades semelhantes. Para obter detalhes, consulte [Proteger seus dados empresariais usando a WIP (Proteção de Informações do Windows)](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).
##  <a name="how-app-protection-policies-protect-app-data"></a>Como as políticas de proteção de aplicativo protegem dados do aplicativo

####  <a name="apps-without-app-protection-policies"></a>Aplicativos sem políticas de proteção de aplicativo

![Imagem que mostra que os dados pode ser movidos livremente entre aplicativos quando não há nenhuma política de proteção de aplicativo em vigor](./media/apps-without-protection-policies.png)

Quando os aplicativos são usados sem restrições, os dados corporativos e pessoais podem se misturar.  Os dados corporativos poderiam acabar em locais como um armazenamento pessoal ou transferidos para aplicativos fora do seu alcance, resultando na perda de dados. As setas no diagrama mostram a movimentação de dados irrestrita entre aplicativos (corporativos e pessoais) e locais de armazenamento.


### <a name="data-protection-with-app-protection-policies"></a>Proteção de dados com as políticas de proteção de aplicativo

![A imagem que mostra como os dados da empresa são protegidos quando as políticas de proteção de aplicativo são aplicadas ](./media/apps-with-protection-policies.png)


Você pode usar as políticas de proteção de aplicativo para impedir que os dados da empresa sejam salvos no armazenamento local do dispositivo, bem como restringir a movimentação de dados para outros aplicativos que não estão protegidos pelas políticas de proteção de aplicativo. As configurações de política de proteção de aplicativo incluem:
- Políticas de realocação de dados como **Evitar Salvar como**, **Restringir recortar, copiar e colar**.
- Configurações de política de acesso como **Exigir PIN simples para acesso**, **Bloquear a execução de aplicativos gerenciados em dispositivos com jailbreak ou raiz**.

### <a name="data-protection-with-app-protection-policies-on-devices-managed-by-a-mdm-solution"></a>Proteção de dados com políticas de proteção de aplicativo nos dispositivos gerenciados por uma solução de MDM

![A imagem que mostra como as políticas de proteção de aplicativo funcionam em dispositivos BYOD](./media/app-protection-policies-with-mdm.png)

**Para dispositivos registrados em uma solução de MDM**-

A ilustração acima mostra as camadas de proteção que as políticas de MDM e proteção de aplicativo oferecem juntas.

A solução MDM:

-   Registra o dispositivo

-   Implanta os aplicativos no dispositivo

-   Fornece gerenciamento e a conformidade contínuos no dispositivo

**Políticas de proteção de aplicativo agregam valor da seguinte forma:**

-   Ajudar a proteger os dados da empresa contra vazamento de serviços e aplicativos de consumidor

-   Aplicar restrições (salvar como, área de transferência, PIN, etc.) aos aplicativos móveis

-   Apagar os dados da empresa dos aplicativos sem remover esses aplicativos do dispositivo


### <a name="data-protection-with-app-protection-policies-for-devices-without-enrollment"></a>Proteção de dados com políticas de proteção de aplicativo para dispositivos sem registro

![A imagem que mostra como as políticas de proteção de aplicativo funcionam em dispositivos gerenciados](./media/app-protection-policies-without-mdm.png)

O diagrama acima ilustra como as políticas de proteção de dados funcionam no nível do aplicativo sem MDM.

Para dispositivos BYOD não registrados em nenhuma solução MDM, as políticas de proteção de aplicativo podem ajudar a proteger os dados da empresa no nível do aplicativo.
Contudo, existem algumas limitações a serem consideradas, como:

-   Você não pode implantar aplicativos no dispositivo.  O usuário final precisa obter os aplicativos na loja.

-   Não é possível provisionar perfis de certificado nesses dispositivos.

-   Não é possível provisionar as configurações de Wi-Fi e VPN da empresa nesses dispositivos.


## <a name="multi-identity"></a>Várias identidades

Aplicativos que dão suporte a várias identidades permitem usar contas diferentes (pessoal e corporativa) para acessar os mesmos aplicativos quando políticas de proteção de aplicativo são aplicadas somente quando os aplicativos são usados no contexto de trabalho.

Por exemplo, quando o usuário inicia o aplicativo OneDrive usando sua conta de trabalho, ele não pode mover os arquivos para um local de armazenamento pessoal. No entanto, quando ele usa o OneDrive com sua conta pessoal, ele pode copiar e mover dados do seu OneDrive pessoal sem restrições.

- Saiba mais sobre os aplicativos que oferecem suporte a [MAM e várias identidades](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) com o Intune.

##  <a name="next-steps"></a>Próximas etapas

[Como criar e implantar as políticas de proteção de aplicativo com o Microsoft Intune](app-protection-policies.md)

## <a name="see-also"></a>Consulte também
Os aplicativos de terceiros, como o aplicativo móvel Salesforce, funcionam com o Intune de maneiras específicas para proteger dados corporativos. Para saber mais sobre como o aplicativo Salesforce em particular funciona com o Intune (incluindo as definições das configurações do aplicativo MDM), confira [Aplicativo Salesforce e Microsoft Intune](https://gallery.technet.microsoft.com/Salesforce-App-and-Intune-c47d44ee/file/188000/1/Salesforce%20App%20and%20Intune%20for%20external.pdf).
