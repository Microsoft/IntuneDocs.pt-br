---
title: "Proteger dados de aplicativo usando políticas MAM | Microsoft Intune"
description: "Este tópico explica como as políticas de gerenciamento de aplicativo móvel pode ajudar a proteger os dados de sua empresa, evitar perda de dados e manter as informações pessoais e de trabalho separadas."
keywords: 
author: karthikaraman
manager: arob98
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ab6cd622-b738-4a63-9c91-56044aaafa6d
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2038ed6219a94dc4285891d71ce00fd51310f3e3
ms.openlocfilehash: b4cc44885683be0f6ef414b630571f3216248876


---

# Proteger dados de aplicativo usando políticas de gerenciamento de aplicativos móveis com o Microsoft Intune

## Como proteger os dados do aplicativo
Os funcionários usam dispositivos móveis para tarefas de pessoais e corporativas.  Embora seja necessário certificar-se que seus funcionários sejam produtivos, você também deseja evitar a perda de dados, intencional ou acidental.  Além disso, é útil ter a capacidade de proteger os dados corporativos acessados usando dispositivos mesmo caso eles não sejam gerenciados por você.

Você pode usar as políticas de MAM (Gerenciamento de Aplicativo Móvel) do Intune para ajudar a proteger os dados da sua empresa. Como as políticas de MAM do Intune podem ser usadas **independentemente de qualquer solução de MDM (Gerenciamento de Dispositivo Móvel)**, você pode usá-las para proteger os dados da sua empresa registrando ou não os dispositivos em uma solução de gerenciamento de dispositivo. Implementando as **políticas de nível de aplicativo**, você pode restringir o acesso aos recursos da empresa e manter os dados dentro do alcance do seu departamento de TI.

As políticas de MAM podem ser configuradas para aplicativos em execução em dispositivos que são:

- **Registrados com o Microsoft Intune:** os dispositivos nessa categoria normalmente são dispositivos corporativos.

-   **Registrados em uma solução de MDM (gerenciamento de dispositivo móvel) de terceiros:** os dispositivos nessa categoria normalmente são dispositivos corporativos.

  > [!NOTE]
  > Políticas de gerenciamento de aplicativo móvel não devem ser usadas com o gerenciamento de aplicativos móveis de terceiros ou com soluções seguras de contêiner.

-   **Não registrados em nenhuma solução de gerenciamento de dispositivo móvel:** os dispositivos nessa categoria normalmente são dispositivos de funcionários que não são gerenciados ou registrados no Intune ou outras soluções de MDM.

> [!IMPORTANT]
> Você pode criar políticas de gerenciamento para aplicativos móveis do Office que se conectam aos serviços do Office 365. As políticas de MAM não têm suporte em aplicativos que se conectam aos serviços do Exchange, Skype for Business ou SharePoint local.

**Os principais benefícios do uso de políticas de MAM são**

-   Proteger os dados da empresa no nível do aplicativo.  Como o gerenciamento de aplicativos móveis não requer gerenciamento de dispositivos, você pode proteger os dados da empresa em dispositivos gerenciados e não gerenciados. O gerenciamento concentra-se na identidade do usuário, o que elimina a necessidade de gerenciar dispositivos.

-   A produtividade do usuário final não é afetada e as políticas não são aplicadas ao usar o aplicativo em um contexto pessoal.  As políticas são aplicadas somente em um contexto corporativo, proporcionando assim a capacidade de proteger dados da empresa sem tocar em dados pessoais.

Há benefícios adicionais em usar MDM com políticas MAM, e as empresas podem usar ambos (MAM com e sem MDM) ao mesmo tempo. Por exemplo, um funcionário pode usar um telefone da empresa e um tablet particular.  Nesse caso, o telefone da empresa é registrado no MDM e protegido pelas políticas de MAM e o dispositivo pessoal é protegido somente pelas políticas de MAM.

- **O MDM garante que o dispositivo estará protegido**.  Por exemplo, você pode exigir um PIN acessar o dispositivo ou pode implantar aplicativos gerenciados para o dispositivo. Você também pode implantar aplicativos em dispositivos por meio da solução MDM, para conferir mais controle sobre o gerenciamento de aplicativo.

- **Políticas de MAM garantem que as proteções de camada de aplicativo estejam em vigor**. Por exemplo, você pode exigir um PIN abrir um aplicativo em um contexto corporativo, se os dados puderem ser compartilhados entre aplicativos ou impedindo que os dados de aplicativo da empresa sejam salvos em um local de armazenamento pessoal.


### Atualmente, há suporte para políticas de MAM em:
-   iOS 8.1 ou posterior

-   Android 4 ou posterior

Não há suporte para dispositivos Windows.
##  Como as políticas de MAM protegem os dados do aplicativo

####  Aplicativos sem políticas de MAM:

![Imagem que mostra que os dados pode ser movidos livremente entre aplicativos quando não há nenhuma política de MAM em vigor](../media/Apps_without_MAM_policies.png)

Quando os aplicativos são usados sem restrições, os dados corporativos e pessoais podem se misturar.  Os dados corporativos poderiam acabar em locais como um armazenamento pessoal ou transferidos para aplicativos fora do seu alcance, resultando na perda de dados. As setas no diagrama mostram a movimentação de dados irrestrita entre aplicativos (corporativos e pessoais) e locais de armazenamento.

### Proteção de dados com políticas de MAM:

![A imagem que mostra como os dados da empresa são protegidos quando as políticas de MAM são aplicadas ](../media/Apps_with_mobile_app_policies.png)

Você pode usar as políticas de MAM para impedir que os dados da empresa sejam salvos no armazenamento local do dispositivo, bem como restringir a movimentação de dados para outros aplicativos que não estão protegidos pelas políticas de MAM. As configurações de política de MAM incluem:
- Políticas de realocação de dados como **Evitar Salvar como**, **Restringir recortar, copiar e colar**.
- Configurações de política de acesso como **Exigir PIN simples para acesso**, **Bloquear a execução de aplicativos gerenciados em dispositivos com jailbreak ou raiz**.

### Proteção de dados com políticas de MAM nos dispositivos gerenciados por uma solução de MDM:

![A imagem que mostra como as políticas de MAM funcionam em dispositivos BYOD](../media/MAM_BYOD_November.png)

**Para dispositivos registrados em uma solução de MDM**-

A ilustração acima mostra as camadas de proteção que as políticas de MDM e MAM oferecem juntas.

A solução MDM:

-   Registra o dispositivo

-   Implanta os aplicativos no dispositivo

-   Fornece gerenciamento e a conformidade contínuos no dispositivo

**As políticas de MAM agregam valor ao:**

-   Ajudar a proteger os dados da empresa contra vazamento de serviços e aplicativos de consumidor

-   Aplicar restrições (salvar como, área de transferência, PIN, etc.) aos aplicativos móveis

-   Apagar os dados da empresa dos aplicativos sem remover esses aplicativos do dispositivo


### Proteção de dados com políticas de MAM para dispositivos sem registro

![Imagem que mostra como as políticas de MAM funcionam nos dispositivos gerenciados](../media/MAM_ManagedDevices_November.png)

O diagrama acima ilustra como as políticas de proteção de dados funcionam no nível do aplicativo sem MDM.

Para dispositivos BYOD não registrados em nenhuma solução MDM, as políticas de MAM podem ajudar a proteger os dados da empresa no nível do aplicativo.
Contudo, existem algumas limitações a serem consideradas, como:

-   Você não pode implantar aplicativos no dispositivo.  O usuário final precisa obter os aplicativos na loja.

-   Não é possível provisionar perfis de certificado nesses dispositivos.

-   Não é possível provisionar as configurações de Wi-Fi e VPN da empresa nesses dispositivos.


## Várias identidades

Aplicativos que dão suporte a várias identidades oferecem a capacidade de usar contas diferentes, pessoal e de trabalho, para acessar os mesmos aplicativos quando políticas de MAM são aplicadas ou quando os aplicativos são usados no contexto de trabalho.  

Por exemplo, quando o usuário final abre o aplicativo OneDrive usando sua conta de trabalho, ele não pode mover os arquivos para um local de armazenamento pessoal. No entanto, quando o usuário final usa o OneDrive com sua conta pessoal, ele pode copiar e mover dados do seu OneDrive pessoal sem restrições.  

Para ver uma explicação detalhada sobre a experiência de usar aplicativos associados a políticas de MAM e como aplicativos com várias identidades dão suporte à aplicação de políticas de MAM apenas no contexto de trabalho, leia [usando aplicativos com suporte a várias identidade](end-user-experience-for-mam-enabled-apps-with-microsoft-intune.md#using-apps-with-multi-identity-support)

Todos os aplicativos móveis do Office dão suporte a várias identidades.

##  Próximas etapas
[Preparar-se para configurar políticas de gerenciamento de aplicativos móveis](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)

[Criar e implantar políticas de gerenciamento de aplicativo móvel com o Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


