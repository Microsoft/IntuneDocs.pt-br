---
title: Visão geral das políticas de proteção de aplicativos
titleSuffix: Microsoft Intune
description: Saiba como as políticas de proteção de aplicativo do Microsoft Intune ajudam a proteger os dados da sua empresa e evitar a perda de dados.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/06/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1c086943-84a0-4d99-8295-490a2bc5be4b
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, get-started, seoapril2019
ms.collection: M365-identity-device-management
ms.openlocfilehash: d2d8d50f7ac5d79d4d0081e7eee2169e9ff45d49
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77512068"
---
# <a name="app-protection-policies-overview"></a>Visão geral das políticas de proteção de aplicativos

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

As políticas de proteção do aplicativo são regras que garantem que os dados de uma organização permaneçam seguros ou armazenados em um aplicativo gerenciado. Uma política pode ser uma regra imposta quando o usuário tenta acessar ou mover dados “corporativos” ou um conjunto de ações proibidas ou monitoradas quando o usuário está no aplicativo. Um aplicativo gerenciado é um aplicativo que tem políticas de proteção de aplicativo aplicadas e que pode ser gerenciado pelo Intune.

As políticas de proteção do aplicativo para MAM (gerenciamento de aplicativo móvel) permitem gerenciar e proteger os dados da organização em um aplicativo. Com o **MAM sem registro**, um aplicativo relacionado ao trabalho ou à escola, que contém dados confidenciais, pode ser gerenciado em quase todos os [dispositivos](app-management.md#app-management-capabilities-by-platform), inclusive dispositivos pessoais, em cenários de **BYOD** (Traga seu próprio dispositivo). Vários aplicativos de produtividade, como os aplicativos do Microsoft Office, podem ser gerenciados pelo Intune MAM. Confira a lista oficial de [aplicativos protegidos do Microsoft Intune](apps-supported-intune-apps.md) disponíveis para uso público.

## <a name="how-you-can-protect-app-data"></a>Como proteger os dados do aplicativo
Os funcionários usam dispositivos móveis para tarefas de pessoais e corporativas. Embora seja necessário garantir que seus funcionários sejam produtivos, você deseja evitar a perda de dados, intencional ou acidental. Você também quer proteger dados da empresa acessados por dispositivos que não são gerenciados por você.

Você pode usar políticas de proteção de aplicativo do Intune **independentemente de qualquer solução de MDM (gerenciamento de dispositivo móvel)** . Essa independência ajuda a proteger os dados da sua empresa com ou sem registro de dispositivos em uma solução de gerenciamento de dispositivo. Implementando as **políticas de nível de aplicativo**, você pode restringir o acesso aos recursos da empresa e manter os dados dentro do alcance do seu departamento de TI.

### <a name="app-protection-policies-on-devices"></a>Políticas de proteção do aplicativo em dispositivos

As políticas de proteção de aplicativo podem ser configuradas para aplicativos em execução em dispositivos que são:

- **Registrados no Microsoft Intune:** Esses dispositivos normalmente são corporativos.

- **Registrados em uma solução de MDM (Gerenciamento de dispositivo móvel) de terceiros:** Esses dispositivos normalmente são corporativos.

  > [!NOTE]
  > Políticas de gerenciamento de aplicativo móvel não devem ser usadas com o gerenciamento de aplicativos móveis de terceiros ou com soluções seguras de contêiner.

- **Não registrados em nenhuma solução de gerenciamento de dispositivo móvel:** Esses dispositivos normalmente são dispositivos de funcionários, que não são gerenciados nem registrados no Microsoft Intune nem em outras soluções de MDM.

> [!IMPORTANT]
> Você pode criar políticas de gerenciamento para aplicativos móveis do Office que se conectam aos serviços do Office 365. Você também pode proteger o acesso às caixas de correio locais do Exchange criando políticas de proteção de aplicativo do Intune para o Outlook para iOS/iPadOS e Android habilitado com Autenticação Moderna híbrida. Antes de usar esse recurso, verifique se você atende aos [requisitos do Outlook para iOS/iPadOS e Android](https://technet.microsoft.com/library/mt846639(v=exchg.160).aspx). As políticas de proteção de aplicativos não são compatíveis com outros aplicativos que se conectam a serviços locais do Exchange ou do SharePoint.

## <a name="benefits-of-using-app-protection-policies"></a>Vantagens do uso de políticas de proteção do aplicativo

As principais vantagens de usar as políticas de proteção do aplicativo são as seguintes:

- **Proteger os dados da empresa no nível do aplicativo**. Como o gerenciamento de aplicativo móvel não requer gerenciamento de dispositivos, é possível proteger os dados da empresa em dispositivos gerenciados e não gerenciados. O gerenciamento concentra-se na identidade do usuário, o que elimina a necessidade de gerenciar dispositivos.

- **A produtividade do usuário final não é afetada e as políticas não são aplicadas ao usar o aplicativo em um contexto pessoal**. As políticas são aplicadas somente em um contexto corporativo, que proporciona a capacidade de proteger dados da empresa sem tocar em dados pessoais.

- **As políticas de proteção do aplicativo garantem a aplicação de proteções por camada do aplicativo**. Por exemplo, você pode:
  - Exigir um PIN para abrir um aplicativo em um contexto de trabalho 
  - Controlar o compartilhamento de dados entre aplicativos 
  - Impedir a gravação de dados de aplicativos da empresa em um local de armazenamento pessoal

- **O MDM juntamente com o MAM verificam se o aplicativo está protegido**. Por exemplo, você pode exigir um PIN acessar o dispositivo ou pode implantar aplicativos gerenciados para o dispositivo. Você também pode implantar aplicativos em dispositivos por meio da solução MDM, para conferir mais controle sobre o gerenciamento de aplicativo.

Há benefícios adicionais ao usar MDM com políticas de proteção de aplicativo, e as empresas podem usar as políticas de proteção de aplicativo com e sem MDM ao mesmo tempo. Por exemplo, considere um funcionário que usa um telefone da empresa e um tablet pessoal. O telefone da empresa é registrado no MDM e protegido pelas políticas de proteção de aplicativo, e o dispositivo pessoal é protegido somente pelas políticas de proteção de aplicativo.

Se você aplicar uma política de MAM ao usuário sem definir o estado do dispositivo, o usuário receberá a política de MAM em seu próprio dispositivo e no dispositivo gerenciado pelo Intune. Você também pode aplicar uma política de MAM com base no estado gerenciado. Portanto, ao criar uma política de proteção do aplicativo, ao lado de **Destino para todos os tipos de aplicativo**, selecione **Não**. Depois, siga um destes procedimentos:
- Aplique uma política de MAM menos rígida a dispositivos gerenciados pelo Intune e uma política de MAM mais restritiva a dispositivos não registrados no MDM.
- Aplique uma política de MAM apenas a dispositivos não registrados.

## <a name="supported-platforms-for-app-protection-policies"></a>Plataformas com suporte para as políticas de proteção de aplicativo

O Intune oferece uma variedade de recursos para ajudar a obter os aplicativos que você precisa, nos dispositivos em que você deseja executá-los. Para saber mais, confira [Recursos de gerenciamento de aplicativo por plataforma](app-management.md#app-management-capabilities-by-platform).

O suporte da plataforma de políticas de proteção de aplicativo do Intune está alinhado ao suporte da plataforma de aplicativo móvel do Office para dispositivos com Android e iOS/iPadOS. Para obter detalhes, confira a seção **Aplicativos móveis** dos [Requisitos de sistema do Office](https://products.office.com/office-system-requirements#coreui-contentrichblock-9r05pwg).

> [!IMPORTANT]
> O dispositivo exige o Portal da Empresa do Intune para receber Políticas de proteção de aplicativos no Android. Saiba mais em [Requisitos de acesso dos aplicativos para o Portal da Empresa do Intune](../fundamentals/end-user-mam-apps-android.md#access-apps).

## <a name="how-app-protection-policies-protect-app-data"></a>Como as políticas de proteção de aplicativo protegem dados do aplicativo

### <a name="apps-without-app-protection-policies"></a>Aplicativos sem políticas de proteção de aplicativo

Quando os aplicativos são usados sem restrições, os dados corporativos e pessoais podem se misturar. Os dados corporativos podem acabar em locais como um armazenamento pessoal ou podem ser transferidos para aplicativos fora do seu alcance, resultando na perda de dados. As setas no diagrama a seguir mostram a movimentação de dados irrestrita entre aplicativos corporativos e pessoais, além de locais de armazenamento.

![Imagem conceitual para movimentação de dados entre aplicativos sem nenhuma política em vigor](./media/app-protection-policy/apps-without-protection-policies.png)

### <a name="data-protection-with-app-protection-policies-app"></a>Proteção de dados com políticas de proteção do aplicativo

Você pode usar as políticas de proteção do aplicativo para impedir que os dados da empresa sejam salvos no armazenamento local do dispositivo (veja a imagem abaixo). Você também pode restringir a movimentação de dados para outros aplicativos que não estão protegidos pelas políticas de proteção do aplicativo. As configurações de política de proteção de aplicativo incluem:
- Políticas de realocação de dados, como **Salvar cópias de dados da organização** e **Restringir recortar, copiar e colar**.
- As configurações de política de acesso como **Exigir PIN simples para acesso** e **Bloquear a execução de aplicativos gerenciados em dispositivos com jailbreak ou raiz**.

![Imagem conceitual que mostra os dados da empresa sendo protegidos por políticas](./media/app-protection-policy/apps-with-protection-policies.png)

### <a name="data-protection-with-app-on-devices-managed-by-an-mdm-solution"></a>Proteção de dados com políticas de proteção do aplicativo em dispositivos gerenciados por uma solução de MDM

A ilustração abaixo mostra as camadas de proteção que o MDM e as políticas de proteção do aplicativo oferecem em conjunto.

![A imagem que mostra como as políticas de proteção de aplicativo funcionam em dispositivos BYOD](./media/app-protection-policy/app-protection-policies-with-mdm.png)

A solução de MDM agrega valor fornecendo o seguinte:

- Registra o dispositivo
- Implanta os aplicativos no dispositivo
- Fornece gerenciamento e a conformidade contínuos no dispositivo

As políticas de proteção do aplicativo agregam valor fornecendo o seguinte:

- Ajudam a proteger os dados da empresa contra vazamento de serviços e aplicativos de consumidor
- Aplicam restrições, como *salvar como*, *área de transferência* ou *PIN*, aos aplicativos cliente
- Apagam os dados da empresa dos aplicativos, quando necessário, sem remover esses aplicativos do dispositivo

### <a name="data-protection-with-app-for-devices-without-enrollment"></a>Proteção de dados com políticas de proteção do aplicativo para dispositivos sem registro

O diagrama a seguir ilustra como as políticas de proteção de dados funcionam no nível do aplicativo sem MDM.

![Imagem que mostra como as políticas de proteção do aplicativo funcionam em dispositivos sem registro (dispositivos não gerenciados).](./media/app-protection-policy/app-protection-policies-without-mdm.png)

Para dispositivos BYOD não registrados em nenhuma solução MDM, as políticas de proteção de aplicativo podem ajudar a proteger os dados da empresa no nível do aplicativo.
No entanto, existem algumas limitações a serem consideradas, como:

- Não é possível implantar aplicativos no dispositivo. O usuário final precisa obter os aplicativos na loja.
- Não é possível provisionar perfis de certificado nesses dispositivos.
- Não é possível provisionar as configurações de Wi-Fi e VPN da empresa nesses dispositivos.

## <a name="apps-you-can-manage-with-app-protection-policies"></a>Aplicativos que podem ser gerenciados com políticas de proteção do aplicativo

Qualquer aplicativo que tenha sido integrado ao [SDK do Intune](../developer/app-sdk.md) ou encapsulado pela [Intune App Wrapping Tool](../developer/apps-prepare-mobile-application-management.md) pode ser gerenciado por políticas de proteção de aplicativo do Intune. Confira a lista oficial de [aplicativos protegidos pelo Microsoft Intune](apps-supported-intune-apps.md) que foram criados com essas ferramentas e estão disponíveis para uso público.

A equipe de desenvolvimento do SDK do Intune testa ativamente e mantém o suporte para aplicativos criados com as plataformas nativas do Android, iOS/iPadOS (Obj-C, Swift), Xamarin, Xamarin.Forms e Cordova. Embora alguns clientes tiveram sucesso na integração do SDK do Intune com outras plataformas, como React Native e NativeScript, não fornecemos orientação explícita ou plug-ins para desenvolvedores de aplicativos que usem algo diferente de nossas plataformas que têm suporte.

O [SDK do Intune](../developer/app-sdk.md) usa algumas funcionalidades avançadas de autenticação moderna da [ADAL (Biblioteca de Autenticação do Azure Active Directory)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) para as versões internas e de terceiros do SDK. Desse modo, a [MSAL (Biblioteca de Autenticação da Microsoft)](https://docs.microsoft.com/azure/active-directory/develop/reference-v2-libraries) não funciona da maneira ideal com muitos de nossos principais cenários, como a inicialização condicional e a autenticação no serviço da Proteção de Aplicativo do Intune. Considerando que a diretriz geral da equipe de identidade da Microsoft é a alternância para o MSAL em todos os aplicativos do Microsoft Office, em algum momento, o [SDK do Intune](../developer/app-sdk.md) precisará dar suporte a ele, mas atualmente não há planos para esse recurso.

## <a name="end-user-requirements-to-use-app-protection-policies"></a>Requisitos do usuário final para usar políticas de proteção do aplicativo

A lista a seguir fornece os requisitos do usuário final para usar políticas de proteção do aplicativo em um aplicativo gerenciado pelo Intune:

- O usuário final deve ter uma conta do AAD (Azure Active Directory). Consulte [Adicionar usuários e conceder permissão administrativa para o Intune](../fundamentals/users-add.md) para saber como criar usuários do Intune no Azure Active Directory.

- O usuário final deve ter uma licença do Microsoft Intune atribuída à sua conta do Azure Active Directory. Confira [Gerenciar licenças do Intune](../fundamentals/licenses-assign.md) para saber como atribuir licenças do Intune aos usuários finais.

- O usuário final deve pertencer a um grupo de segurança destinado a uma política de proteção do aplicativo. A mesma política de proteção do aplicativo deve ter como destino o aplicativo específico utilizado. Políticas de proteção do aplicativo podem ser criadas e implantadas no console do Intune no [portal do Azure](https://portal.azure.com). No momento, grupos de segurança podem ser criados no [centro de administração do Microsoft 365](https://admin.microsoft.com).

- O usuário final deve se conectar ao aplicativo usando sua conta do AAD.

## <a name="app-protection-policies-for-microsoft-office-apps"></a>Políticas de proteção do aplicativo para aplicativos do Microsoft Office

Há alguns requisitos adicionais que você deve conhecer ao usar as políticas de proteção do aplicativo com os aplicativos do Microsoft Office.

### <a name="outlook-mobile-app"></a>Aplicativo Outlook Mobile
Os requisitos adicionais para usar o [aplicativo Outlook Mobile](https://products.office.com/outlook) incluem o seguinte:

- O usuário final deve ter o aplicativo móvel do Outlook instalado em seu dispositivo.
- O usuário final deve ter uma caixa de correio do [Office 365 Exchange Online](https://products.office.com/exchange/exchange-online) e uma licença vinculada à sua conta do Azure Active Directory.

  >[!NOTE]
  > O aplicativo móvel do Outlook atualmente é compatível apenas para a Proteção de Aplicativo do Intune para o Microsoft Exchange Online e [Exchange Server com autenticação moderna híbrida](https://technet.microsoft.com/library/mt846639(v=exchg.160).aspx), e não dá suporte ao Exchange no Office 365 Dedicado.

### <a name="word-excel-and-powerpoint"></a>Word, Excel e PowerPoint
Os requisitos adicionais para usar os aplicativos [Word, Excel e PowerPoint](https://products.office.com/business/office) incluem o seguinte:

- O usuário final deve ter uma licença do [Office 365 Business ou Enterprise](https://products.office.com/business/compare-more-office-365-for-business-plans) vinculada à sua conta do Azure Active Directory. A assinatura deve incluir os aplicativos do Office em dispositivos móveis e pode incluir uma conta de armazenamento em nuvem com o [OneDrive for Business](https://onedrive.live.com/about/business/). As licenças do Office 365 podem ser atribuídas na [centro de administração do Microsoft 365](https://admin.microsoft.com) seguindo estas [instruções](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).

- O usuário final deve configurar um local gerenciado usando o salvamento granular como funcionalidade na configuração "Salvar cópias de dados da organização" da política de proteção do aplicativo. Por exemplo, se o local gerenciado for o OneDrive, será necessário configurar o aplicativo [OneDrive](https://onedrive.live.com/about/) no aplicativo Word, Excel ou PowerPoint do usuário final.

- Se o local gerenciado for o OneDrive, será necessário direcionar o aplicativo de acordo com a política de proteção do aplicativo implantada para o usuário final.

  >[!NOTE]
  > No momento, os aplicativos móveis do Office dão suporte apenas ao SharePoint Online e não ao SharePoint local.

### <a name="managed-location-needed-for-office"></a>Local gerenciado necessário para o Office
Uma localização gerenciada (ou seja, o OneDrive) é necessária para o Office. O Microsoft Intune marca todos os dados no aplicativo como "corporativos" ou "pessoais". Os dados são considerados “corporativos” quando tem como origem um local da empresa. Para os aplicativos do Office, o Intune considera o seguinte como locais da empresa: email (Exchange) ou armazenamento em nuvem (aplicativo OneDrive com uma conta do OneDrive para Empresas).

### <a name="skype-for-business"></a>Skype for Business
Existem requisitos adicionais para usar o Skype for Business. Consulte os requisitos de licença do [Skype for Business](https://products.office.com/skype-for-business/it-pros). Para configurações híbridas e locais do SfB (Skype for Business), confira [A autenticação moderna híbrida para SfB e Exchange torna-se GA](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Hybrid-Modern-Auth-for-SfB-and-Exchange-goes-GA/ba-p/134756) e [Autenticação moderna para SfB local com o AAD](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Modern-Auth-for-SfB-OnPrem-with-AAD/ba-p/180910), respectivamente.

## <a name="app-protection-global-policy"></a>Política Global de proteção de aplicativo

Se um administrador do OneDrive navegar até **admin.onedrive.com** e escolher **Acesso a dispositivo**, ele poderá definir os controles de **Gerenciamento de aplicativo móvel** para os aplicativos de cliente do OneDrive e do SharePoint. 

As configurações, disponibilizadas para o console de administração do OneDrive, configuram uma política de proteção especial de aplicativo do Intune chamada de política **Global**. Essa política global é aplicável a todos os usuários em seu locatário e não tem como controlar o direcionamento de política. 

Uma vez habilitada, os aplicativos OneDrive e SharePoint para iOS/iPadOS e Android são protegidos com as configurações selecionadas por padrão. Um profissional de TI pode editar essa política no console do Intune para adicionar mais aplicativos direcionados e modificar qualquer configuração de política. 

Por padrão, só pode haver uma política **Global** por locatário. No entanto, você pode usar as [APIs do Graph do Intune](../developer/intune-graph-apis.md) para criar políticas extras globais por locatário, mas isso não é recomendado. Criar políticas extras globais não é recomendado porque a solução de problemas da implementação dessa política pode se tornar complicada.

Embora a política **Global** se aplique a todos os usuários em seu locatário, qualquer política de Proteção de Aplicativo do Intune padrão substituirá essas configurações.

## <a name="app-protection-features"></a>Recursos de proteção do aplicativo

### <a name="multi-identity"></a>Várias identidades

O suporte para várias identidades permite que um aplicativo forneça suporte a vários públicos. Esses públicos são formados por usuários "corporativos" e "pessoais". As contas corporativas e de estudante são usadas por públicos "corporativos", enquanto as contas pessoais são usadas pelo público consumidor, como usuários do Microsoft Office. Um aplicativo com suporte para várias identidades pode ser lançado publicamente, caso em que as políticas de proteção do aplicativo se aplicam somente quando o aplicativo é usado no contexto profissional e escolar ("corporativo"). O suporte a várias identidades usa o [SDK do Intune](../developer/app-sdk.md) para aplicar políticas de proteção de aplicativo somente à conta corporativa ou de estudante conectada ao aplicativo. Se uma conta pessoal estiver conectada ao aplicativo, os dados permanecerão inalterados.

Para obter um exemplo de contexto "pessoal", considere um usuário que inicia um novo documento no Word. Isso é considerado um contexto pessoal, portanto, não se aplicam as políticas da Proteção de Aplicativo do Intune. Quando o documento é salvo na conta "corporativa" do OneDrive, ele é considerado um contexto "corporativo", e as políticas de proteção do aplicativo do Intune são aplicadas.

Como exemplo de contexto de trabalho ou "corporativo", considere um usuário que inicia o aplicativo OneDrive usando uma conta corporativa. No contexto de trabalho, ele não pode mover arquivos para um local de armazenamento pessoal. Mais tarde, quando ele usa o OneDrive com sua conta pessoal, pode copiar e mover dados do seu OneDrive pessoal sem restrições.

O Outlook tem uma exibição de email combinada para emails "pessoais" e "corporativos". Nessa situação, o aplicativo do Outlook solicita o PIN do Intune na inicialização.

Para saber mais sobre várias identidades no Microsoft Intune, confira o tópico [MAM e várias identidades](apps-supported-intune-apps.md).

### <a name="intune-app-pin"></a>PIN do aplicativo do Intune

O PIN (Número de Identificação Pessoal) é uma senha usada para verificar se o usuário correto está acessando os dados da organização em um aplicativo.

**Solicitação de PIN**<br>
O Intune solicitará o PIN do aplicativo do usuário quando o usuário estiver prestes a acessar dados "corporativos". Em aplicativos de várias identidades, como o Word, Excel ou PowerPoint, o usuário é solicitado a inserir o respectivo PIN ao tentar abrir um arquivo ou documento "corporativo". Em aplicativos de identidade única, como aplicativos de linha de negócios gerenciados com a [Intune App Wrapping Tool](../developer/apps-prepare-mobile-application-management.md), o PIN é solicitado na inicialização, pois o [SDK do Intune](../developer/app-sdk.md) sabe que a experiência do usuário no aplicativo é sempre "corporativa".

**Solicitação de PIN, solicitação de credenciais corporativas, frequência**<br>
O administrador de TI pode definir a política de proteção do aplicativo do Intune com o recurso **Verificar novamente os requisitos de acesso após (minutos)** , no console de administrador do Intune. Essa configuração especifica o tempo necessário para a verificação dos requisitos de acesso no dispositivo e até a tela do PIN do aplicativo ou as solicitação de credenciais corporativas ser exibida novamente. No entanto, detalhes importantes sobre o PIN que afetam a frequência com que o usuário será consultado são:

- **O PIN é compartilhado entre aplicativos do mesmo editor para melhorar a usabilidade:**<br> No iOS/iPadOS, um PIN de aplicativo é compartilhado entre todos os aplicativos **do mesmo editor de aplicativo**. Por exemplo, todos os aplicativos da Microsoft compartilham o PIN. No Android, o PIN de um aplicativo é compartilhado com todos os aplicativos.
- **O comportamento do recurso *Verificar novamente os requisitos de acesso após (minutos)* , após uma reinicialização do dispositivo:**<br> Um temporizador rastreia o número de minutos de inatividade que determinam quando mostrar o PIN do aplicativo do Intune ou a solicitação de credenciais corporativas em seguida. No iOS/iPadOS, o temporizador não é afetado pela reinicialização do dispositivo. Portanto, a reinicialização do dispositivo não tem nenhum efeito sobre o número de minutos que o usuário esteve inativo em um aplicativo iOS/iPadOS com a política de PIN do Intune (ou de credenciais corporativas) de destino. No Android, o temporizador é redefinido na reinicialização do dispositivo. Portanto, os aplicativos Android com a política de PIN do Intune (ou de credenciais corporativas) provavelmente solicitarão um PIN do aplicativo ou as credenciais corporativas, seja qual for o valor da configuração 'Verificar novamente os requisitos de acesso após (minutos)' **depois de uma reinicialização do dispositivo**.  
- **A natureza em constante movimento do temporizador associada ao PIN:**<br> Depois que um PIN é inserido para acessar um aplicativo (aplicativo A) e o aplicativo deixa o primeiro plano (foco de entrada principal) no dispositivo, o temporizador é redefinido para esse PIN. Qualquer aplicativo (aplicativo B) que compartilhe esse PIN não solicitará ao usuário para inserir o PIN porque o temporizador foi redefinido. A solicitação será exibida novamente quando o valor "Verificar novamente os requisitos de acesso após (minutos)" for atendido novamente.

Para dispositivos iOS/iPadOS, mesmo se o PIN for compartilhado entre aplicativos de diferentes fornecedores, a solicitação será exibida novamente quando o valor **Verificar novamente os requisitos de acesso após (minutos)** for atendido novamente para o aplicativo que não é o foco principal de entrada. Por exemplo, um usuário tem o aplicativo _A_ do fornecedor _X_ e o aplicativo _B_ do fornecedor _Y_, e esses dois aplicativos compartilham o mesmo PIN. O usuário está concentrado no aplicativo _A_ (primeiro plano), e o aplicativo _B_ está minimizado. Depois que o valor **Verificar novamente os requisitos de acesso após (minutos)** for atendido e o usuário alternar para o aplicativo _B_, o PIN será necessário.

  >[!NOTE]
  > Para verificar os requisitos de acesso do usuário com mais frequência (ou seja, solicitação do PIN), especialmente para um aplicativo usado com frequência, é recomendável reduzir o valor da configuração "Verificar novamente os requisitos de acesso após (minutos)".

**PINs de aplicativos internos para Outlook e OneDrive**<br>
O PIN do Intune funciona de acordo com um temporizador baseado em inatividade (o valor de **Verificar novamente os requisitos de acesso após (minutos)** ). Portanto, os prompts do PIN do Intune são mostrados independentemente dos prompts do PIN do aplicativo interno do Outlook e do OneDrive, que geralmente são vinculados à inicialização do aplicativo por padrão. Se o usuário recebe ambos os prompts de PIN ao mesmo tempo, o comportamento esperado é que o PIN do Intune tenha precedência.

**Segurança de PIN do Intune**<br>
O PIN serve para permitir que somente o usuário correto acesse os dados de sua organização no aplicativo. Portanto, um usuário final deve entrar com sua conta corporativa ou de estudante antes de definir ou redefinir o PIN do aplicativo do Intune. Essa autenticação é feita pelo Azure Active Directory por meio da troca de tokens seguros e não é transparente para o [SDK do Intune](../developer/app-sdk.md). Sob a perspectiva de segurança, a melhor maneira de proteger dados corporativos ou de estudante é criptografá-los. A criptografia não está relacionada ao PIN do aplicativo, mas à sua própria política de proteção de aplicativo.

**Proteção contra ataques de força bruta e o PIN do Intune**<br>
Como parte da política de PIN do aplicativo, o administrador de TI pode definir o número máximo de vezes que um usuário pode tentar autenticar seu PIN antes do bloqueio do aplicativo. Depois que o número de tentativas for atingido, o [SDK do Intune](../developer/app-sdk.md) poderá apagar os dados "corporativos" do aplicativo.

**PIN do Intune e um apagamento seletivo**<br>
No iOS/iPadOS, as informações de PIN no nível de aplicativo são armazenadas no conjunto de chaves que é compartilhado entre aplicativos com o mesmo editor, como todos os aplicativos internos da Microsoft. Essas informações de PIN também estão vinculadas a uma conta de usuário final. Um apagamento seletivo de um aplicativo não deve afetar outro aplicativo. 

Por exemplo, um PIN definido no Outlook para o usuário conectado é armazenado em um conjunto de chaves compartilhado. Quando o usuário entra no OneDrive (também publicado pela Microsoft), ele vê o mesmo PIN que o Outlook, pois ele usa o mesmo conjunto de chaves compartilhado. Ao sair do Outlook ou apagar os dados do usuário no Outlook, o SDK do Intune não limpa esse conjunto de chaves, porque o OneDrive ainda pode estar usando esse PIN. Por isso, os apagamentos seletivos não limpam esse conjunto de chaves compartilhado, incluindo o PIN. Esse comportamento permanece inalterado, mesmo se há apenas um aplicativo de um editor no dispositivo. 

Como o PIN é compartilhado entre aplicativos com o mesmo editor, se o apagamento se destina a um só aplicativo, o SDK do Intune não sabe se há outros aplicativos no dispositivo com o mesmo editor. Portanto, o SDK do Intune não limpa o PIN, pois ele ainda pode ser usado para outros aplicativos. A expectativa é que o PIN do aplicativo seja apagado no momento da remoção do último aplicativo desse editor como parte de uma limpeza do sistema operacional.
 
Caso você observe que o PIN está sendo apagado em alguns dispositivos, provavelmente está ocorrendo o seguinte: Como o PIN está vinculado a uma identidade, caso o usuário se conecte com uma conta diferente após um apagamento, ele deve inserir um novo PIN. No entanto, caso ele se conecte com uma conta anteriormente existente, um PIN armazenado no conjunto de chaves já pode ser usado para a conexão.

**Definir um PIN duas vezes em aplicativos do mesmo editor?**<br>
Atualmente, o MAM (no iOS/iPadOS) permite o PIN no nível de aplicativo com caracteres alfanuméricos e especiais (chamados de 'senha'), o que exige a participação de aplicativos (ou seja, WXP, Outlook, Managed Browser e Yammer), a fim de integrar o [SDK do Intune para iOS](../developer/app-sdk-ios.md). Sem isso, as configurações de senha não são aplicadas corretamente nos aplicativos de destino. Esse era um recurso lançado no SDK do Intune para iOS v. 7.1.12.

Para dar suporte a esse recurso e garantir a compatibilidade com versões anteriores do SDK do Intune para iOS/iPadOS, todos os PINs (numéricos ou de senha) na versão 7.1.12+ são tratados separadamente do PIN numérico das versões anteriores do SDK. Portanto, se um dispositivo tiver aplicativos com o SDK do Intune para versões do iOS anteriores a 7.1.12 E posteriores a 7.1.12 do mesmo editor, será necessário configurar dois PINs. Os dois PINs (para cada aplicativo) não estão relacionados de forma alguma (ou seja, devem aderir à política de proteção do aplicativo aplicada ao aplicativo). Sendo assim, o usuário poderá configurar o mesmo PIN duas vezes *somente* se os aplicativos A e B tiverem as mesmas políticas aplicadas com relação ao PIN. 

Esse comportamento é específico ao PIN em aplicativos do iOS/iPadOS habilitados com o Gerenciamento de Aplicativo Móvel do Intune. Ao longo do tempo, à medida que os aplicativos adotam versões posteriores do SDK do Intune para iOS/iPadOS, a necessidade de definir um PIN duas vezes em aplicativos do mesmo editor se torna um problema menos significativo. Consulte a observação abaixo para obter um exemplo.

  >[!NOTE]
  > Por exemplo, se o aplicativo A for compilado com uma versão anterior à 7.1.12, e o aplicativo B for compilado com uma versão superior ou igual à 7.1.12 do mesmo editor, o usuário final precisará configurar PINs separadamente para A e B, se ambos forem instalados em um dispositivo iOS/iPadOS.
  > Se um aplicativo C que tem o SDK versão 7.1.9 estiver instalado no dispositivo, ele compartilhará o mesmo PIN que o aplicativo A. Um aplicativo D criado com a versão 7.1.14 compartilhará o mesmo PIN que o aplicativo B.  
  > Se apenas os aplicativos A e C estiverem instalados em um dispositivo, será necessário definir um PIN. O mesmo se aplica se apenas os aplicativos B e D estiverem instalados em um dispositivo.

### <a name="app-data-encryption"></a>Criptografia de dados do aplicativo
Os administradores de TI podem implantar uma política de proteção do aplicativo que exige a criptografia dos dados do aplicativo. Como parte da política, o administrador de TI também pode especificar quando o conteúdo é criptografado.

**Como funciona o processo de criptografia de dados do Microsoft Intune**<br> Consulte [Android app protection policy settings (Configurações da política de proteção do aplicativo Android)](app-protection-policy-settings-android.md) e [iOS/iPadOS app protection policy settings (Configurações da política de proteção do aplicativo iOS)](app-protection-policy-settings-ios.md) para obter informações detalhadas sobre a configuração da política de proteção do aplicativo para criptografia.

**Dados criptografados**<br>
Somente os dados marcados como “corporativos” são criptografados, de acordo com a política de proteção do aplicativo do administrador de TI. Os dados são considerados “corporativos” quando tem como origem um local da empresa. Para os aplicativos do Office, o Intune considera o seguinte como locais de negócios:

- Email (Exchange) 
- Armazenamento em nuvem (aplicativo OneDrive com uma conta do OneDrive for Business)

Para aplicativos de linha de negócios gerenciados pela [Ferramenta de Encapsulamento de Aplicativo do Intune](../developer/apps-prepare-mobile-application-management.md), todos os dados do aplicativo são considerados "corporativos".

### <a name="selective-wipe"></a>Limpeza seletiva

**Apagar dados remotamente**<br>
O Microsoft Intune pode apagar dados de aplicativos de três maneiras diferentes: 
- Apagamento completo do dispositivo
- Apagamento seletivo para MDM 
- Apagamento seletivo de MAM

Para obter mais informações sobre o apagamento remoto para MDM, consulte [Remover dispositivos usando o apagamento ou a desativação](../remote-actions/devices-wipe.md). Para obter mais informações sobre o apagamento seletivo usando MAM, confira [A ação Desativar](../remote-actions/devices-wipe.md#retire) e [Como apagar apenas dados corporativos dos aplicativos](apps-selective-wipe.md).

O [apagamento completo do dispositivo](../remote-actions/devices-wipe.md) remove do **dispositivo** todos os dados e todas as configurações do usuário, restaurando o dispositivo para as configurações padrão de fábrica. O dispositivo é removido do Intune.

  >[!NOTE]
  > O apagamento completo e o apagamento seletivo do dispositivo para MDM só podem ser feitos em dispositivos registrados no MDM (gerenciamento de dispositivo móvel) do Intune.

**Apagamento seletivo para MDM**<br>
Confira [Remover dispositivos – desativar](../remote-actions/devices-wipe.md#retire) para saber mais sobre a remoção de dados da empresa.

**Apagamento seletivo para MAM**<br>
O apagamento seletivo para MAM simplesmente remove dados de aplicativo da empresa de um aplicativo. A solicitação é iniciada usando o portal do Azure no Intune. Para saber como iniciar uma solicitação de apagamento, confira [Como remover apenas dados corporativos dos aplicativos](apps-selective-wipe.md).

Se o usuário estiver usando o aplicativo quando o apagamento seletivo for iniciado, o [SDK do Intune](../developer/app-sdk.md) verificará, a cada 30 minutos, se há uma solicitação de apagamento seletivo do serviço MAM do Intune. Ele também verifica o apagamento seletivo quando o usuário inicia o aplicativo pela primeira vez e se conecta com sua conta corporativa ou de estudante.

**Quando os serviços locais não funcionam com os aplicativos protegidos do Intune**<br>
A proteção de aplicativo do Intune depende da consistência da identidade do usuário entre o aplicativo e o [SDK do Intune](../developer/app-sdk.md). A única maneira de assegurar isso é por meio da autenticação moderna. Existem cenários nos quais os aplicativos podem funcionar com uma configuração local, mas eles não são consistentes nem têm garantia.

**Maneira segura de abrir links da Web em aplicativos gerenciados**<br>
O administrador de TI pode implantar e definir uma política de proteção do aplicativo para o [aplicativo Intune Managed Browser](app-configuration-managed-browser.md), um navegador da Web desenvolvido pelo Microsoft Intune que pode ser gerenciado facilmente com o Intune. O administrador de TI pode exigir que todos os links da Web em aplicativos gerenciados pelo Intune sejam abertos usando o aplicativo Managed Browser.

## <a name="app-protection-experience-for-ios-devices"></a>Experiência de proteção de aplicativo para dispositivos iOS

### <a name="device-fingerprint-or-face-ids"></a>Face ID ou impressão digital no dispositivo 
As políticas de Proteção de Aplicativo do Intune permitem controlar o acesso do aplicativo somente para o usuário licenciado do Intune. Uma das maneiras de controlar o acesso ao aplicativo é exigir uma Touch ID ou a Face ID da Apple em dispositivos com suporte. O Intune implementa um comportamento no qual, se houver qualquer alteração ao banco de dados biométrico do dispositivo, solicitará ao usuário um PIN quando o próximo valor de tempo limite de inatividade for atendido. As alterações aos dados biométricos incluem a adição ou a remoção de uma impressão digital ou detecção facial. Se o usuário do Intune não tiver um PIN definido, ele será conduzido a configurar um PIN do Intune.
 
A intenção desse processo é continuar a manter os dados da organização dentro do aplicativo, seguros e protegidos no nível do aplicativo. Esse recurso só está disponível para o iOS/iPadOS e exige a participação de aplicativos que integram o SDK do Intune para iOS/iPadOS, versão 9.0.1 ou posterior. A integração do SDK é necessária para que o comportamento possa ser aplicado aos aplicativos de destino. Essa integração ocorre sem interrupção, e depende de equipes do aplicativo específico. Alguns aplicativos que participam incluem WXP, Outlook, Managed Browser e Yammer.
  
### <a name="ios-share-extension"></a>Extensão de compartilhamento do iOS
Você pode usar a extensão de compartilhamento do iOS/iPadOS para abrir dados corporativos ou de estudante em aplicativos não gerenciados, mesmo com a política de transferência de dados definida como **Somente aplicativos gerenciados** ou **Nenhum aplicativo**. A política de proteção de aplicativo do Intune não pode controlar a extensão de compartilhamento do iOS/iPadOS sem gerenciar o dispositivo. Portanto, o _**Intune criptografa os dados “corporativos” antes que eles sejam compartilhados fora do aplicativo**_ . É possível validar esse comportamento de criptografia ao tentar abrir o arquivo "corporativo" fora do aplicativo gerenciado. O arquivo deve ser criptografado e não pode ser aberto fora do aplicativo gerenciado.

### <a name="multiple-intune-app-protection-access-settings-for-same-set-of-apps-and-users"></a>Várias configurações de acesso de proteção de aplicativo do Microsoft Intune para o mesmo conjunto de aplicativos e usuários
As políticas de proteção do aplicativo do Intune para acesso serão aplicadas em uma ordem específica nos dispositivos de usuários finais à medida que eles tentarem acessar um aplicativo de destino nas respectivas contas corporativas. Em geral, um apagamento teria precedência, seguido por um bloqueio e então um aviso ignorável. Por exemplo, se aplicável ao usuário/aplicativo em questão, uma configuração de sistema operacional mínima do iOS/iPadOS que avisa o usuário para atualizar a versão de iOS/iPadOS, que será aplicada após a configuração de sistema operacional mínima do iOS/iPadOS que bloqueia o acesso do usuário. Portanto, no cenário em que o administrador de TI configura a versão de sistema operacional iOS mínima para 11.0.0.0 e do sistema operacional iOS mínima para 11.1.0.0, enquanto o dispositivo que tenta acessar o aplicativo estava em uma versão de iOS 10, o usuário final seria bloqueado com base a configuração mais restritiva para a versão de sistema operacional iOS mínima que resulta em acesso bloqueado.

Ao lidar com diferentes tipos de configurações, um requisito de versão do SDK do Intune tem precedência, em seguida, um requisito de versão do aplicativo, seguido pelo requisito de versão do sistema operacional iOS/iPadOS. Em seguida, os avisos para todos os tipos de configurações na mesma ordem são verificados. Recomendamos que o requisito de versão do SDK do Intune seja configurado somente após as diretrizes da equipe de produto do Intune para cenários de bloqueio essenciais.

## <a name="app-protection-experience-for-android-devices"></a>Experiência de proteção de aplicativo para dispositivos Android

### <a name="company-portal-app-and-intune-app-protection"></a>Aplicativo Portal da Empresa e Proteção de Aplicativo do Intune
Grande parte da funcionalidade de proteção do aplicativo é interna ao aplicativo Portal da Empresa. O registro de dispositivo _não é necessário_, embora o aplicativo Portal da Empresa seja sempre obrigatório. Para o MAM (gerenciamento de aplicativos móvel) sem registro, o usuário final precisa apenas ter o aplicativo Portal da Empresa instalado no dispositivo.

### <a name="multiple-intune-app-protection-access-settings-for-same-set-of-apps-and-users"></a>Várias configurações de acesso de proteção de aplicativo do Microsoft Intune para o mesmo conjunto de aplicativos e usuários
As políticas de proteção do aplicativo do Intune para acesso serão aplicadas em uma ordem específica nos dispositivos de usuários finais à medida que eles tentarem acessar um aplicativo de destino nas respectivas contas corporativas. Em geral, um bloqueio teria precedência e, em seguida, um aviso ignorável. Por exemplo, se aplicável ao usuário/aplicativo em questão, uma configuração de versão de patch mínima do Android que avisa o usuário para fazer uma atualização de patch, que será aplicada após a configuração da versão de patch mínima do Android que bloqueia o acesso do usuário. Portanto, o cenário em que o administrador de TI configura a versão de patch de Android mínima 2018-03-01 e a versão de patch de Android mínima (somente Aviso) 2018-02-01, enquanto o dispositivo tentar acessar o aplicativo estava em uma versão de patch 2018-01-01, o usuário final seria bloqueado com base a configuração mais restritiva para a versão de patch de Android mínima que resulta em acesso bloqueado. 

Ao lidar com diferentes tipos de configurações, um requisito de versão do aplicativo teria precedência, seguido por um requisito de versão do sistema operacional de versão de patch do Android. Em seguida, os avisos para todos os tipos de configurações na mesma ordem são verificados.

### <a name="intune-app-protection-policies-and-googles-safetynet-attestation-for-android-devices"></a>Políticas da Proteção de Aplicativo do Intune e Certificação do SafetyNet do Google para dispositivos Android 
As políticas da Proteção de Aplicativo do Intune fornecem a funcionalidade para que os administradores exijam que os dispositivos de usuário final que os dispositivos de usuário final sejam aprovados pela Certificação de dispositivo do SafetyNet para dispositivos Android. Uma nova determinação de serviço do Google Play será relatada ao administrador de TI em um intervalo determinado pelo serviço do Intune. A frequência com que a chamada de serviço é feita é limitada devido à carga; portanto, esse valor é mantido internamente e não é configurável. Qualquer ação configurada pelo administrador de TI para a configuração do Atestado SafetyNet do Google será usada com base no último resultado relatado ao serviço do Intune no momento da inicialização condicional. Se não houver dados, o acesso será permitido sem depender de nenhuma outra falha nas verificações de inicialização condicional e a “viagem de ida e volta” do Serviço do Google Play para determinar os resultados do atestado começará no back-end e avisará o usuário de maneira assíncrona se o dispositivo tiver falhado. Se houver dados obsoletos, o acesso será bloqueado ou permitido dependendo do último resultado relatado e, de maneira semelhante, a “viagem de ida e volta” do Serviço do Google Play para determinar os resultados do atestado começará e avisará o usuário de maneira assíncrona se o dispositivo tiver falhado.

### <a name="intune-app-protection-policies-and-googles-verify-apps-api-for-android-devices"></a>Políticas da Proteção de Aplicativo do Intune e API de verificação de aplicativos do Google para dispositivos Android
As políticas da Proteção de Aplicativo do Intune fornecem a funcionalidade para que os administradores exijam que os dispositivos de usuário final enviem sinais por meio da API de verificação de aplicativos do Google para dispositivos Android. As instruções sobre como fazer isso variam um pouco por dispositivo. O processo geral envolve acessar a Google Play Store, clicar em **Meus aplicativos e jogos** e clicar no resultado do último exame de aplicativo que o levará até o menu do Play Protect. Verifique se **Examinar no dispositivo se há ameaças à segurança** está ativado.

### <a name="googles-safetynet-attestation-api"></a>API do certificado de SafetyNet do Google 
O Intune usa as APIs SafetyNet do Google Play Protect a serem adicionadas às nossas verificações de detecção raiz para dispositivos não registrados. O Google desenvolveu e manteve esse conjunto de APIs para os aplicativos Android adotarem se eles não desejarem que os aplicativos sejam executados em dispositivos desbloqueados por rooting. O aplicativo Android Pay incorporou isso, por exemplo. Embora o Google não compartilhe publicamente todas as verificações de detecção raiz que ocorrem, esperamos que essas APIs detectem usuários que bloquearam seus dispositivos por rooting. Esses usuários podem ter o acesso bloqueado ou suas contas corporativas podem ser apagadas dos aplicativos habilitados por política. **Verificar integridade básica** informa sobre a integridade geral do dispositivo. Dispositivos desbloqueados por rooting, emuladores, dispositivos virtuais e dispositivos com sinais de falsificação apresentam falha na integridade básica. **Verificar integridade básica e dispositivos com certificação** informa sobre a compatibilidade do dispositivo com os serviços do Google. Somente dispositivos não modificados que foram certificados pelo Google podem ser aprovados nessa verificação. Dispositivos que falharão incluem o seguinte:

- dispositivos que apresentam falha na integridade básica
- dispositivos com um carregador de inicialização desbloqueado
- dispositivos com uma imagem/ROM do sistema personalizada
- dispositivos que o fabricante não inscreveu na certificação do Google ou que não foram aprovados por ela
- dispositivos com uma imagem do sistema criada diretamente de arquivos de origem do Programa de Software Livre do Android
- dispositivos com uma imagem do sistema de versão prévia beta/do desenvolvedor

Confira a [documentação do Google sobre o Atestado SafetyNet](https://developer.android.com/training/safetynet/attestation) para obter detalhes técnicos.

### <a name="safetynet-device-attestation-setting-and-the-jailbrokenrooted-devices-setting"></a>Configuração da Certificação de dispositivo do SafetyNet e a configuração "Dispositivos desbloqueados por jailbreak/rooting"
As verificações da API SafetyNet do Google Play Protect exigem que o usuário final esteja online, pelo menos durante o período de execução da “viagem de ida e volta” para determinar os resultados do atestado. Se o usuário final estiver offline, o administrador de TI ainda poderá esperar que um resultado seja imposto da configuração **Dispositivos desbloqueados por jailbreak/rooting**. Tendo isso em conta, se o usuário final ficar offline por muito tempo, o valor **Período de carência offline** entrará em vigor, e todo o acesso a dados corporativos ou de estudante será bloqueado quando esse valor de timer for atingido, até que o acesso à rede esteja disponível. A ativação das duas configurações permite que uma abordagem em camadas mantenha os dispositivos de usuário final íntegros, o que é importante quando os usuários finais acessam dados corporativos ou de estudante em dispositivos móveis.

### <a name="google-play-protect-apis-and-google-play-services"></a>APIS do Google Play Protect e Google Play Services
As configurações da política de proteção do aplicativo que usam as APIs do Google Play Protect exigem que o Google Play Services esteja em funcionamento. As configurações **Certificação de dispositivo do SafetyNet** e **Verificação de ameaças em aplicativos** exigem que a versão determinada do Google Play Services funcione corretamente. Como essas configurações se enquadram na área de segurança, o usuário final será bloqueado se for direcionado com essas configurações e não atender à versão adequada do Google Play Services ou não tiver acesso ao Google Play Services.

## <a name="next-steps"></a>Próximas etapas

[Como criar e implantar as políticas de proteção de aplicativo com o Microsoft Intune](app-protection-policies.md)

[Configurações disponíveis da política de proteção de aplicativo do Android no Microsoft Intune](app-protection-policy-settings-android.md)

[Configurações disponíveis da política de proteção de aplicativo do iOS/iPadOS no Microsoft Intune](app-protection-policy-settings-ios.md)

## <a name="see-also"></a>Consulte também
Os aplicativos de terceiros, como o aplicativo móvel Salesforce, funcionam com o Intune de maneiras específicas para proteger dados corporativos. Para saber mais sobre como o aplicativo Salesforce em particular funciona com o Intune (incluindo as definições das configurações do aplicativo MDM), confira [Aplicativo Salesforce e Microsoft Intune](https://gallery.technet.microsoft.com/Salesforce-App-and-Intune-c47d44ee/file/188000/1/Salesforce%20App%20and%20Intune%20for%20external.pdf).
