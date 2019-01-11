---
title: O que são políticas de proteção do aplicativo
titleSuffix: Microsoft Intune
description: Saiba como as políticas de proteção de aplicativo do Microsoft Intune ajudam a proteger os dados da sua empresa e evitar a perda de dados.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/11/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1c086943-84a0-4d99-8295-490a2bc5be4b
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.openlocfilehash: 49ecdebc2777112ce8c8c97af1f98b3c12b200e1
ms.sourcegitcommit: 0dc977795ff80abb6a3b989ca633cba410f06c64
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/04/2019
ms.locfileid: "54006277"
---
# <a name="what-are-app-protection-policies"></a>O que são políticas de proteção de aplicativo?


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

As políticas de proteção de aplicativo do Microsoft Intune ajudam a proteger os dados da empresa e evitar a perda de dados.

## <a name="how-you-can-protect-app-data"></a>Como proteger os dados do aplicativo
Os funcionários usam dispositivos móveis para tarefas de pessoais e corporativas. Embora seja necessário garantir que seus funcionários sejam produtivos, você deseja evitar a perda de dados, intencional ou acidental. Você também quer proteger dados da empresa acessados por dispositivos que não são gerenciados por você.

Você pode usar políticas de proteção de aplicativo do Intune **independentemente de qualquer solução de MDM (gerenciamento de dispositivo móvel)**. Essa independência ajuda a proteger os dados da sua empresa com ou sem registro de dispositivos em uma solução de gerenciamento de dispositivo. Implementando as **políticas de nível de aplicativo**, você pode restringir o acesso aos recursos da empresa e manter os dados dentro do alcance do seu departamento de TI.

As políticas de proteção de aplicativo podem ser configuradas para aplicativos em execução em dispositivos que são:

- **Registrados no Microsoft Intune:** Esses dispositivos normalmente são corporativos.

- **Registrados em uma solução de MDM (Gerenciamento de dispositivo móvel) de terceiros:** Esses dispositivos normalmente são corporativos.

  > [!NOTE]
  > Políticas de gerenciamento de aplicativo móvel não devem ser usadas com o gerenciamento de aplicativos móveis de terceiros ou com soluções seguras de contêiner.

- **Não registrados em nenhuma solução de gerenciamento de dispositivo móvel:** Os dispositivos dessa categoria normalmente são dispositivos de funcionários que não são gerenciados nem registrados no Intune nem em outras soluções de MDM.

> [!IMPORTANT]
> Você pode criar políticas de gerenciamento para aplicativos móveis do Office que se conectam aos serviços do Office 365. Você também pode proteger o acesso às caixas de correio locais do Exchange criando políticas de proteção de aplicativos do Intune para o Outlook para iOS e Android habilitado com Autenticação Moderna híbrida. Antes de usar esse recurso, verifique se você atende aos [requisitos do Outlook para iOS e Android](https://technet.microsoft.com/library/mt846639(v=exchg.160).aspx). As políticas de proteção de aplicativos não são compatíveis com outros aplicativos que se conectam a serviços locais do Exchange ou do SharePoint.

**Os principais benefícios do uso de políticas de proteção de aplicativo são**

-   Proteger os dados da empresa no nível do aplicativo. Como o gerenciamento de aplicativo móvel não requer gerenciamento de dispositivos, é possível proteger os dados da empresa em dispositivos gerenciados e não gerenciados. O gerenciamento concentra-se na identidade do usuário, o que elimina a necessidade de gerenciar dispositivos.

-   A produtividade do usuário final não é afetada, e as políticas não são aplicadas ao usar o aplicativo em um contexto pessoal. As políticas são aplicadas somente em um contexto corporativo, que proporciona a capacidade de proteger dados da empresa sem tocar em dados pessoais.

Há benefícios adicionais ao usar MDM com políticas de proteção de aplicativo, e as empresas podem usar as políticas de proteção de aplicativo com e sem MDM ao mesmo tempo. Por exemplo, considere um funcionário que usa um telefone da empresa e um tablet pessoal. O telefone da empresa é registrado no MDM e protegido pelas políticas de proteção de aplicativo, e o dispositivo pessoal é protegido somente pelas políticas de proteção de aplicativo.

- **O MDM garante que o dispositivo estará protegido**. Por exemplo, você pode exigir um PIN acessar o dispositivo ou pode implantar aplicativos gerenciados para o dispositivo. Você também pode implantar aplicativos em dispositivos por meio da solução MDM, para conferir mais controle sobre o gerenciamento de aplicativo.

- **Políticas de proteção de aplicativo garantem que as proteções de camada de aplicativo estejam em vigor**. Por exemplo, você pode:
  - Exigir um PIN para abrir um aplicativo em um contexto de trabalho 
  - Controlar o compartilhamento de dados entre aplicativos 
  - Impedir a gravação de dados de aplicativos da empresa em um local de armazenamento pessoal


### <a name="supported-platforms-for-app-protection-policies"></a>Plataformas com suporte para as políticas de proteção de aplicativo
O suporte da plataforma de políticas de proteção de aplicativo do Intune está alinhado ao suporte da plataforma de aplicativo móvel do Office para dispositivos com Android e iOS. Para obter detalhes, confira a seção **Aplicativos móveis** dos [Requisitos de sistema do Office](https://products.office.com/office-system-requirements#coreui-contentrichblock-9r05pwg).

Não há suporte para dispositivos Windows. No entanto, você pode usar a Proteção de Informações do Windows, que oferece recursos semelhantes. Para obter detalhes, consulte [Proteger seus dados empresariais usando a WIP (Proteção de Informações do Windows)](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).


## <a name="how-app-protection-policies-protect-app-data"></a>Como as políticas de proteção de aplicativo protegem dados do aplicativo

#### <a name="apps-without-app-protection-policies"></a>Aplicativos sem políticas de proteção de aplicativo

![Imagem conceitual para movimentação de dados entre aplicativos sem nenhuma política em vigor](./media/apps-without-protection-policies.png)

Quando os aplicativos são usados sem restrições, os dados corporativos e pessoais podem se misturar. Os dados corporativos podem acabar em locais como um armazenamento pessoal ou podem ser transferidos para aplicativos fora do seu alcance, resultando na perda de dados. As setas no diagrama anterior mostram a movimentação de dados irrestrita entre aplicativos corporativos e pessoais, além de locais de armazenamento.


### <a name="data-protection-with-app-protection-policies"></a>Proteção de dados com as políticas de proteção de aplicativo

![Imagem conceitual que mostra os dados da empresa sendo protegidos por políticas](./media/apps-with-protection-policies.png)


Você pode usar as políticas de proteção de aplicativo para impedir que os dados da empresa sejam salvos no armazenamento local do dispositivo. Você também pode restringir a movimentação de dados para outros aplicativos que não estão protegidos pelas políticas de proteção do aplicativo. As configurações de política de proteção de aplicativo incluem:
- Políticas de realocação de dados como **Evitar Salvar Como** e **Restringir recortar, copiar e colar**.
- As configurações de política de acesso como **Exigir PIN simples para acesso** e **Bloquear a execução de aplicativos gerenciados em dispositivos com jailbreak ou raiz**.

### <a name="data-protection-with-app-protection-policies-on-devices-managed-by-a-mobile-device-management-solution"></a>Proteção de dados com políticas de proteção de aplicativo nos dispositivos gerenciados por uma solução de Gerenciamento de Dispositivo Móvel

![A imagem que mostra como as políticas de proteção de aplicativo funcionam em dispositivos BYOD](./media/app-protection-policies-with-mdm.png)

**Para dispositivos registrados em uma solução de MDM**-

A ilustração anterior mostra as camadas de proteção que as políticas de MDM e proteção de aplicativo oferecem juntas.

A solução MDM:

-   Registra o dispositivo

-   Implanta os aplicativos no dispositivo

-   Fornece gerenciamento e a conformidade contínuos no dispositivo

**Políticas de proteção de aplicativo agregam valor da seguinte forma:**

-   Ajudar a proteger os dados da empresa contra vazamento de serviços e aplicativos de consumidor

-   Aplicar restrições, como *salvar como*, *área de transferência* ou *PIN*, aos aplicativos cliente

-   Apagar os dados da empresa dos aplicativos sem remover esses aplicativos do dispositivo


### <a name="data-protection-with-app-protection-policies-for-devices-without-enrollment"></a>Proteção de dados com políticas de proteção de aplicativo para dispositivos sem registro

![A imagem que mostra como as políticas de proteção de aplicativo funcionam em dispositivos gerenciados](./media/app-protection-policies-without-mdm.png)

O diagrama anterior ilustra como as políticas de proteção de dados funcionam no nível do aplicativo sem MDM.

Para dispositivos BYOD não registrados em nenhuma solução MDM, as políticas de proteção de aplicativo podem ajudar a proteger os dados da empresa no nível do aplicativo.
Contudo, existem algumas limitações a serem consideradas, como:

-   Não é possível implantar aplicativos no dispositivo. O usuário final precisa obter os aplicativos na loja.

-   Não é possível provisionar perfis de certificado nesses dispositivos.

-   Não é possível provisionar as configurações de Wi-Fi e VPN da empresa nesses dispositivos.

## <a name="app-protection-global-policy"></a>Política Global de proteção de aplicativo

Se um administrador do OneDrive navegar até **admin.office.com** e selecionar o acesso a **Dispositivo**, ele poderá definir os controles de **Gerenciamento de aplicativo móvel** para os aplicativos de cliente do OneDrive e do SharePoint. 

As configurações, disponibilizadas para o console de administração do OneDrive, configuram uma política de proteção especial de aplicativo do Intune chamada de política **Global**. Essa política global é aplicável a todos os usuários em seu locatário e não tem como controlar o direcionamento de política. 

Uma vez habilitada, os aplicativos OneDrive e SharePoint para iOS e Android são protegidos com as configurações selecionadas por padrão. Um profissional de TI pode editar essa política no console do Intune para adicionar mais aplicativos direcionados e modificar qualquer configuração de política. 

Por padrão, só pode haver uma política **Global** por locatário. No entanto, você pode usar as [APIs do Graph do Intune](intune-graph-apis.md) para criar políticas extras globais por locatário, mas isso não é recomendado. Criar políticas extras globais não é recomendado porque a solução de problemas da implementação dessa política pode se tornar complicada.

Embora a política **Global** se aplique a todos os usuários em seu locatário, qualquer política de Proteção de Aplicativo do Intune padrão substituirá essas configurações.


## <a name="multi-identity"></a>Várias identidades

Aplicativos que dão suporte a várias identidades permitem usar contas diferentes (pessoal e corporativa) para acessar os mesmos aplicativos. Por outro lado, políticas de proteção de aplicativo são aplicadas somente quando os aplicativos são usados no contexto de trabalho.

Para obter um exemplo de um contexto pessoal, considere um usuário que inicia um novo documento no Word, isso é considerado um contexto pessoal, portanto, as políticas de Proteção de Aplicativo do Intune não são aplicadas. Assim que o documento for salvo na conta corporativa do OneDrive, ele será considerado um contexto corporativo e as políticas de Proteção de Aplicativo do Intune serão aplicadas.

Como exemplo de contexto de trabalho, considere um usuário que inicia o aplicativo OneDrive usando sua conta corporativa. No contexto de trabalho, ele não pode mover arquivos para um local de armazenamento pessoal. Mais tarde, quando ele usa o OneDrive com sua conta pessoal, pode copiar e mover dados do seu OneDrive pessoal sem restrições.

- Saiba mais sobre os aplicativos que oferecem suporte a [MAM e várias identidades](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) com o Intune.

## <a name="next-steps"></a>Próximas etapas

[Como criar e implantar as políticas de proteção de aplicativo com o Microsoft Intune](app-protection-policies.md)

## <a name="see-also"></a>Consulte também
Os aplicativos de terceiros, como o aplicativo móvel Salesforce, funcionam com o Intune de maneiras específicas para proteger dados corporativos. Para saber mais sobre como o aplicativo Salesforce em particular funciona com o Intune (incluindo as definições das configurações do aplicativo MDM), confira [Aplicativo Salesforce e Microsoft Intune](https://gallery.technet.microsoft.com/Salesforce-App-and-Intune-c47d44ee/file/188000/1/Salesforce%20App%20and%20Intune%20for%20external.pdf).
