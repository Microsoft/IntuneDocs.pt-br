---
title: Proteger o email no Exchange Online
description: Proteja e controle o acesso ao email da empresa no Exchange Online com acesso condicional.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 09c82f5d-531c-474d-add6-784c83f96d93
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5b0bb2b518705c92089e1e9ed1d1cfece7f2572f
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2017
---
# <a name="protect-email-access-to-exchange-online-and-new-exchange-online-dedicated-with-intune"></a>Proteger o acesso ao email no Exchange Online e ao novo Exchange Online Dedicado com o Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Você pode configurar o acesso condicional para o Exchange Online ou Exchange Online Dedicado usando o Microsoft Intune. Para saber mais sobre como funciona o acesso condicional, leia o artigo [Proteger o acesso ao email, O365 e outros serviços](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).

> [!NOTE]
>Se você tiver um ambiente do Exchange Online Dedicado e precisar descobrir se ele está com a configuração nova ou herdada, contate seu gerente de conta.

## <a name="before-you-begin"></a>Antes de começar

Para configurar o acesso condicional, você deve:

-   Ter uma **assinatura do Office 365 que inclui o Exchange Online (como E3)**; além disso, os usuários devem ser licenciados para o Exchange Online.

- Ter uma **assinatura do Enterprise Mobility + Security** ou do **Azure Active Directory Premium** e ter os usuários licenciados para o EMS ou o Azure AD. Para obter mais detalhes, veja a [página de preços do Enterprise Mobility](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) ou a [página de preços do Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).

-  Considere a configuração do **conector serviço a serviço opcional do Intune**, que conecta o Intune ao Exchange Online e ajuda você a gerenciar as informações do dispositivo por meio do console do Intune. Você não precisa usar o conector para usar políticas de conformidade ou políticas de acesso condicional, mas ele é necessário para executar relatórios que ajudam a avaliar o impacto do acesso condicional.
    -  Saiba mais sobre o [Intune Service to Service Connector](intune-service-to-service-exchange-connector.md).

   > [!NOTE]
   > Não configure o Intune Service to Service Connector se você pretende usar o acesso condicional para o Exchange Online e o Exchange local.

### <a name="device-compliance-requirements"></a>Requisitos de conformidade do dispositivo

Ao configurar políticas de acesso condicional e direcioná-las a um usuário, antes que um usuário possa se conectar a seu email, o **dispositivo** usado deve ser/estar:

-   Um computador ingressado no domínio ou **registrado** no Intune.

-  **Registrado no Azure Active Directory**. Isso ocorre automaticamente quando o dispositivo é registrado com Intune. Além disso, a ID do Exchange ActiveSync do cliente deve estar registrada com o Azure Active Directory.

  O serviço Registro do Dispositivo do Azure Active Directory é ativado automaticamente para clientes do Intune e Office 365. Clientes que já tiverem implantado o Serviço de Registro de Dispositivos do ADFS não verão dispositivos registrados no seu Active Directory local.

-   **Em conformidade** com todas as políticas de conformidade do Intune implantadas nesse dispositivo ou ingressadas no domínio em um domínio local.

### <a name="when-the-device-is-not-compliant"></a>Quando o dispositivo não for compatível

Se uma política de acesso condicional não for atendida, o dispositivo será colocado imediatamente em quarentena e o usuário receberá um email com uma das seguintes notificações de quarentena ao entrar:

- Se o dispositivo não estiver registrado no Intune ou não estiver registrado no Azure Active Directory, será exibida uma mensagem com instruções sobre como instalar o aplicativo Portal da Empresa, registrar o dispositivo e ativar o email. Esse processo também associa a ID do Exchange ActiveSync do dispositivo com o registro no Azure Active Directory.

-   Se o dispositivo for avaliado como não estando em conformidade com as regras da política de conformidade, o usuário será direcionado para o site do Portal da Empresa do Intune ou para o aplicativo Portal da Empresa, em que poderá encontrar informações sobre o problema e como corrigi-lo.

### <a name="how-conditional-access-works-with-exchange-online"></a>Como o acesso condicional funciona com o Exchange Online

O diagrama a seguir ilustra o fluxo usado pelas políticas de acesso condicional para o Exchange Online.

![Diagrama que ilustra os pontos de decisões que determinam se um dispositivo tem permissão de acesso ou está bloqueado](../media/ConditionalAccess8-1.png)

## <a name="support-for-mobile-devices"></a>Suporte para dispositivos móveis
É possível proteger o acesso ao email do Exchange Online no **Outlook** e em outros **aplicativos que usam a autenticação moderna**. Há suporte para os recursos a seguir:

- Android 4.0 e posterior, Samsung Knox Standard 4.0 e posterior e Android for Work
- iOS 8.0 e posterior

A **autenticação moderna** leva a conexão baseada no ADAL (Biblioteca de Autenticação do Active Directory) para os clientes do Microsoft Office.

-   A autenticação baseada em ADAL permite que os clientes do Office participem da autenticação baseada em navegador (também conhecida como autenticação passiva). Para se autenticar, um usuário é direcionado para uma página da Web de conexão.
-   Esse novo método de conexão permite uma melhor segurança, como a **autenticação multifator** e a **autenticação baseada em certificado**. Para obter informações mais detalhadas, consulte [Como funciona a autenticação moderna](https://support.office.com/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517). É possível configurar regras de declaração do ADFS para bloquear protocolos de autenticação não moderna. Instruções detalhadas são fornecidas em [Cenário 3: bloquear todo o acesso ao O365, exceto para aplicativos baseados em navegador](https://technet.microsoft.com/library/dn592182.aspx).

É possível proteger o acesso ao **OWA (Outlook Web Access)** no Exchange Online quando um usuário o acessa em um navegador em dispositivos **iOS** e **Android**. O acesso será permitido somente de navegadores com suporte em dispositivos compatíveis:

* Safari (iOS)
* Chrome (Android)
* Intune Managed Browser (iOS, Android 5.0 e posterior)

   > [!IMPORTANT]
   > **Navegadores sem suporte serão bloqueados**.

**O aplicativo OWA para iOS e Android pode ser modificado para não usar a autenticação moderna e não há suporte para isso. O acesso do aplicativo OWA deve ser bloqueado por meio de regras de declaração do ADFS.**


Você pode proteger o acesso ao email no Exchange por meio do **cliente de email do Exchange ActiveSync** interno nas seguintes plataformas:

- Android 4.0 e posterior, Samsung Knox Standard 4.0 e posterior

- iOS 8.0 e posterior

- Windows Phone 8.1 e posterior

## <a name="support-for-pcs"></a>Suporte para computadores

É possível configurar o acesso condicional para computadores que executam aplicativos da área de trabalho do Office para acessar o **Exchange Online** e o **SharePoint Online** em computadores que atendem aos seguintes requisitos:

-   O computador deve executar o Windows 7.0, Windows 8.1 ou Windows 10.

  >[!NOTE]
  > Para usar o acesso condicional em PCs com Windows 10, você deve atualizar esses PCs com a Atualização de Aniversário do Windows 10.

  O computador deve estar ingressado no domínio ou deve ser compatível com as regras de políticas de conformidade.

  Para ser considerado em compatível, o computador deve ser registrado no Intune e estar em conformidade com as políticas.

  Para computadores ingressados no domínio, é necessário configurar o acesso condicional para [registrar o dispositivo automaticamente](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-automatic-device-registration/) no Azure Active Directory.

  >[!NOTE]
    >Não há suporte para o acesso condicional em computadores que executam o cliente de computador do Intune.

-   [A autenticação moderna do Office 365 deve estar habilitada](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) e ter todas as atualizações mais recentes do Office.

    A autenticação moderna leva a conexão baseada no ADAL (Biblioteca de Autenticação do Active Directory) para os clientes do Office 2013/Windows. Ela permite uma melhor segurança, como a **autenticação multifator** e a **autenticação baseada em certificado**.

-   As regras de declaração do ADFS são configuradas para bloquear protocolos de autenticação não modernos. Instruções detalhadas são fornecidas em [Cenário 3: bloquear todo o acesso ao O365, exceto para aplicativos baseados em navegador](https://technet.microsoft.com/library/dn592182.aspx).

## <a name="configure-conditional-access"></a>Configurar acesso condicional
### <a name="step-1-configure-and-deploy-a-compliance-policy"></a>Etapa 1: configurar e implantar uma política de conformidade
Lembre-se de [criar](create-a-device-compliance-policy-in-microsoft-intune.md) e [implantar](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md) uma política de conformidade para os grupos de usuários que também receberão a política de acesso condicional.


> [!IMPORTANT]
> Se você ainda não tiver implantado nenhuma política de conformidade, os dispositivos serão considerados em conformidade e terão acesso ao Exchange.

### <a name="step-2-evaluate-the-effect-of-the-conditional-access-policy"></a>Etapa 2: avaliar o efeito da política de acesso condicional
Você pode usar os **Relatórios de Inventário de Dispositivos Móveis** para identificar quais dispositivos em sua organização serão impedidos de acessar o Exchange quando você configura uma política de acesso condicional.

Para fazer isso, configure uma conexão entre o Intune e o Exchange usando o [Conector entre serviços do Microsoft Intune](intune-service-to-service-exchange-connector.md).
1.  Navegue até **Relatórios** > **Relatórios de Inventário de Dispositivo Móvel**.
![Captura de tela da página Relatórios de Inventário de Dispositivo Móvel](../media/IntuneSA2bMobileDeviceInventoryReport.png)

2.  Nos parâmetros do relatório, selecione o grupo do Intune que você deseja avaliar e, se necessário, as plataformas de dispositivo às quais a política será aplicada.
3.  Depois de selecionar os critérios que atendem às necessidades de sua organização, escolha **Exibir Relatório**.
Um Visualizador de Relatórios é aberto em uma nova janela.
![Captura de tela de um exemplo do relatório de inventário do dispositivo móvel](../media/IntuneSA2cViewReport.PNG)

Depois de executar o relatório, examine essas quatro colunas para determinar se um usuário será bloqueado:

-   **Canal de Gerenciamento**: indica se o dispositivo é gerenciado pelo Intune, pelo Exchange ActiveSync ou por ambos.

-   **Registrado no AAD**: indica se o dispositivo está registrado no Azure Active Directory (conhecido como Workplace Join).

-   **Em Conformidade**: indica se o dispositivo está em conformidade com as políticas de conformidade implantadas.

-   **ID do Exchange ActiveSync**: dispositivos iOS e Android precisam ter sua ID do Exchange ActiveSync associada ao registro do dispositivo no Azure Active Directory. Isso acontece quando um usuário escolhe o link **Ativar Email** no email de quarentena.

    > [!NOTE]
    > Dispositivos Windows Phone sempre exibem um valor nesta coluna.

Dispositivos que fazem parte de um grupo de destino são impedidos de acessar o Exchange, a menos que os valores da coluna correspondam aos valores listados na seguinte tabela:

--------------------------
|Canal de Gerenciamento|Registrado no AAD|Compatível|ID do Exchange ActiveSync|Ação resultante|
|----------------------|------------------|-------------|--------------------------|--------------------|
|**Gerenciado pelo Microsoft Intune e pelo Exchange ActiveSync**|Sim|Sim|Um valor é exibido|O acesso ao email é permitido|
|Qualquer outro valor|Não|Não|Nenhum valor é exibido|O acesso ao email é bloqueado|
----------------------
Você pode exportar o conteúdo do relatório e usar a coluna **Endereço de email** para informar os usuários de que eles serão bloqueados.

### <a name="step-3-configure-user-groups-for-the-conditional-access-policy"></a>Etapa 3: configurar grupos de usuários para a política de acesso condicional
Políticas de acesso condicional são destinadas a diferentes grupos de segurança do Azure Active Directory de usuários. Você também pode isentar alguns grupos de usuários de uma política de acesso condicional. Quando um usuário é afetado por uma política, todos os dispositivos usados por ele devem estar em conformidade para que ele possa acessar o email.

É possível configurar esses grupos no **Centro de administração do Office 365** ou no **Portal de conta do Intune**.

Você pode especificar dois tipos de grupo em cada política:

-   **Grupos de destino**: grupos de usuários aos quais a política é aplicada.

-   **Grupos isentos**: grupos de usuários isentos da política (opcional).

Se um usuário estiver nos dois grupos, ele ficará isento da política.

Somente os grupos que são afetados pela política de acesso condicional são avaliados.

### <a name="step-4-configure-the-conditional-access-policy"></a>Etapa 4: Configurar a política de acesso condicional

>[!NOTE]
> Também é possível criar uma política de acesso condicional no console de gerenciamento do Azure AD. O console de gerenciamento do Azure AD permite que você crie uma política de acesso condicional de dispositivo do Intune (conhecida como a **política de acesso condicional baseada em dispositivo** no Azure AD), além de outras políticas de acesso condicional, como a autenticação multifator.

>Também é possível definir políticas de acesso condicional para aplicativos empresariais de terceiros com suporte do Azure AD, como Salesforce e Box. Para obter mais detalhes, consulte [Como definir a política de acesso condicional com base no dispositivo do Azure Active Directory para controle de acesso dos aplicativos conectados no Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-policy-connected-applications/).


1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com), escolha **Política** > **Acesso Condicional** > **Política do Exchange Online**.

2.  Na página **Política do Exchange Online**, escolha **Habilitar política de acesso condicional para o Exchange Online**.

    > [!NOTE]
    > Se você ainda não tiver implantado nenhuma política de conformidade, os dispositivos serão tratados como em conformidade.
    >
    > Independentemente do estado de conformidade, todos os usuários que são afetados pela política precisam registrar seus dispositivos no Intune.

3.  Em **Acesso ao aplicativo**, para aplicativos que usam a autenticação moderna, há duas maneiras de escolher as plataformas às quais a política deve ser aplicada. Plataformas com suporte incluem iOS, Android, Windows e Windows Phone.

    -   **Todas as plataformas**

        Isso exige que os dispositivos usados para acessar o **Exchange Online** sejam registrados no Intune e estejam em conformidade com as políticas. Qualquer aplicativo cliente que use a **autenticação moderna** está sujeito à política de acesso condicional. Se, no momento, não houver suporte para a plataforma no Intune, o acesso ao **Exchange Online** será bloqueado.

        Selecionar a opção **Todas as plataformas** significa que o Azure Active Directory aplicará essa política a todas as solicitações de autenticação, independentemente da plataforma relatada pelo aplicativo cliente. Todas as plataformas devem ser registradas e estar em conformidade, exceto:
        *   Dispositivos Windows, que precisarão ser registrados e compatíveis, ingressados no domínio com o Active Directory local ou ambas as opções.
        * Plataformas sem suporte, como Mac OS. No entanto, os aplicativos que usam a autenticação moderna provenientes dessas plataformas ainda estarão bloqueados.

    -   **Plataformas específicas**

         A política de acesso condicional se aplica ao aplicativos cliente que usam a **autenticação moderna** nas plataformas de dispositivo especificadas.

4. Em **OWA (Outlook Web Access)**, você pode optar por permitir o acesso ao Exchange Online apenas por meio de navegadores com suporte: Safari (iOS) e Chrome (Android). O acesso de outros navegadores será bloqueado. As mesmas restrições de plataforma selecionadas para Acesso ao aplicativo para Outlook também se aplicam aqui.

  Em dispositivos **Android**, os usuários devem habilitar o acesso do navegador. Para fazer isso, o usuário deve habilitar a opção **Habilitar Acesso do Navegador** no dispositivo registrado da seguinte maneira:
  1.    Abra o **aplicativo Portal da Empresa**.
  2.    Acesse a página **Configurações** por meio das reticências (...) ou do botão de menu do hardware.
  3.    Pressione o botão **Habilitar Acesso do Navegador**.
  4.    No navegador Chrome, saia do Office 365 e reinicie o Chrome.

  Em plataformas **iOS** e **Android**, para identificar o dispositivo usado para acessar o serviço, o Azure Active Directory emite um certificado de protocolo TLS para o dispositivo. O dispositivo exibe o certificado com uma solicitação ao usuário final para selecionar o certificado, conforme mostrado nas capturas de tela a seguir. O usuário deve selecionar esse certificado antes que possa continuar usando o navegador.

  **iOS**

  ![Captura de tela da solicitação de certificado em um iPad](../media/mdm-browser-ca-ios-cert-prompt.png)

  **Android**

  ![captura de tela da solicitação de certificado em um dispositivo Android](../media/mdm-browser-ca-android-cert-prompt.png)

5.  Em **aplicativos do Exchange ActiveSync**, você pode optar por bloquear dispositivos incompatíveis de acessar o Exchange Online. Também é possível escolher se deseja permitir ou bloquear o acesso ao email quando o dispositivo não está executando uma plataforma com suporte. Plataformas com suporte incluem iOS, Android, Windows e Windows Phone.

 Aplicativos do Exchange Active Sync em dispositivos **Android para Trabalho**:
 -  Em dispositivos Android for Work, há suporte somente para os aplicativos **Gmail** e **Nine Work** no **perfil de trabalho**. Para que o acesso condicional funcione em dispositivos Android para Trabalho, é necessário implantar um perfil de email para os aplicativos Gmail ou Nine Work e também implantá-los como uma instalação **obrigatória**.

6.  Em **Grupos de Destino**, selecione os grupos de usuários de segurança do Active Directory aos quais a política se aplica. Você pode optar por direcionar todos os usuários ou uma lista selecionada de grupos de usuários.
![Captura de tela da página da política de acesso condicional do Exchange Online que mostra as opções de grupo de Destino e Isento](../media/IntuneSA5eTargetedExemptedGroups.PNG)
    > [!NOTE]
    > Para usuários que estão nos **Grupos de destino**, as políticas do Intune substituem as regras e políticas do Exchange.
    >
    > O Exchange apenas imporá as regras de permissão, bloqueio e quarentena, bem como as políticas do Exchange se:
    >
    > -   Um usuário não está licenciado para o Intune.
    > -   Um usuário está licenciado para o Intune, mas não pertence a nenhum grupo de segurança é afetado na política de acesso condicional.

6.  Em **Grupos isentos**, selecione os grupos de segurança de usuários do Active Directory que serão isentos desta política. Se um usuário estiver nos grupos de destino e isentos, ele será isento da política.

7.  Quando terminar, selecione **Salvar**.

-   Não é necessário implantar a política de acesso condicional, ela entra em vigor imediatamente.

-   Depois que um usuário cria uma conta de email, o dispositivo é bloqueado imediatamente.

-   Se um usuário bloqueado registrar o dispositivo no Intune e corrigir os problemas de não conformidade, o acesso ao email será desbloqueado em até dois minutos.

-   Se o usuário cancelar o registro de seu dispositivo, o email será bloqueado após seis horas, aproximadamente.

Para ver alguns **cenários de exemplo de como você poderá configurar uma política de acesso condicional para proteger o acesso ao dispositivo**, consulte [Proteger o acesso a email – cenários de exemplo](restrict-email-access-example-scenarios.md).

## <a name="monitor-the-compliance-and-conditional-access-policies"></a>Monitorar a conformidade e políticas de acesso condicional

#### <a name="to-view-devices-that-are-blocked-from-exchange"></a>Para exibir dispositivos que foram bloqueados do Exchange

No painel do Intune, escolha o bloco **Dispositivos Bloqueados do Exchange** para mostrar o número de dispositivos bloqueados e links para obter mais informações.
![Captura de tela do painel do Intune mostrando o número de dispositivos que são impedidos de acessar o Exchange](../media/IntuneSA6BlockedDevices.PNG)

## <a name="next-steps"></a>Próximas etapas
- [Proteger o acesso ao SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)

- [Proteger o acesso ao Skype for Business Online](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
