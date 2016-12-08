---
title: "Pré-requisitos para registro de dispositivo móvel | Microsoft Intune"
description: "Configure os pré-requisitos de MDM (gerenciamento de dispositivo móvel) e prepare-se para registrar diferentes sistemas operacionais."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 44fd4af0-f9b0-493a-b590-7825139d9d40
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 391612c35a7665073ca8a5c629169e5be967ab59


---

# <a name="prerequisites-for-mobile-device-management-in-intune"></a>Pré-requisitos para gerenciamento de dispositivo móvel no Intune
Permitir que os funcionários registrem seus dispositivos móveis com o Intune exige as seguintes etapas. Essas mesmas etapas são necessárias para gerenciar dispositivos da empresa.

|Etapas|Detalhes|  
|-----------|-------------|  
|**Etapa 1:** [Habilitar conexões](#step-1-enable-connections)|Verifique se seu nome de domínio personalizado foi configurado e se a comunicação de rede está pronta|  
|**Etapa 2:** [Configurar a autoridade de MDM](#step-2-set-mdm-authority)|A autoridade de gerenciamento de dispositivo móvel define o serviço atribuído aos dispositivos|
|**Etapa 3:** [Criar grupos](#step-3-create-groups)|Definir configurações voltadas para o usuário para o aplicativo do Portal da Empresa|  
|**Etapa 4:** [Configurar o Portal da Empresa](#step-4-configure-company-portal)|Definir configurações voltadas para o usuário para o aplicativo do Portal da Empresa|  
|**Etapa 5:** [Atribuir licenças de usuário](#step-5-assign-user-licenses)|Atribuir licenças do Intune aos usuários para que possam registrar dispositivos|
|**Etapa 6:** [Habilitar registro](#step-6-enable-enrollment)|Habilite as configurações específicas da plataforma para gerenciamento do Windows e iOS. Os dispositivos Android não precisam de qualquer configuração adicional.|
|**Etapa 7:** [Próximas etapas](#step-7-next-steps)|Habilite as configurações específicas da plataforma para gerenciamento do Windows e iOS. Os dispositivos Android não precisam de qualquer configuração adicional.|

Procurando o Intune com o Configuration Manager?
> [!div class="button"]
[Exibir documentos do SCCM >](https://docs.microsoft.com/sccm/mdm/deploy-use/setup-hybrid-mdm)

## <a name="step-1-enable-connections"></a>Etapa 1: Habilitar conexões

Antes de habilitar o registro de dispositivo móvel, certifique-se de ter feito o seguinte:
- [Examinar as portas e URLs de rede necessárias](../get-started/network-infrastructure-requirements-for-microsoft-intune)
- [Adicionar e verificar o nome de domínio](../get-started/domain-names-for-microsoft-intune)

## <a name="step-2-set-mdm-authority"></a>Etapa 2: Configurar a autoridade de MDM
A autoridade de MDM define o serviço de gerenciamento que tem permissão para gerenciar um conjunto de dispositivos. As opções para a autoridade de MDM incluem o Intune e o Configuration Manager com Intune. Se você definir o Configuration Manager como a autoridade de gerenciamento, nenhum outro serviço poderá ser usado para gerenciamento de dispositivo móvel.

>[!IMPORTANT]
> Considere atentamente se você quer gerenciar dispositivos móveis usando apenas o Intune (serviço online) ou o System Center Configuration Manager com Intune (solução de software local em conjunto com o serviço online). Depois de configurar a autoridade de gerenciamento de dispositivo móvel, ela não poderá ser alterada.



1.  No [Console de administração do Microsoft Intune](http://manage.microsoft.com), selecione **Administrador** &gt; **Gerenciamento de Dispositivo Móvel**.

2.  Na lista **Tarefas**, clique em **Configurar autoridade de gerenciamento de dispositivo móvel**. A caixa de diálogo **Definir autoridade MDM** é aberta.

    ![Definir a caixa de diálogo de autoridade de MDM](../media/intune-mdm-authority.png)

3.  O Intune solicita a confirmação de que você deseja o Intune como autoridade MDM. Marque a caixa de seleção e escolha **Sim** para usar o Microsoft Intune para gerenciar dispositivos móveis.

## <a name="step-3-create-groups"></a>Etapa 3: Criar grupos

Você pode criar grupos de usuários e dispositivos para simplificar o gerenciamento e melhorar o direcionamento dos aplicativos, políticas e recursos da empresa que são implantados. [Saiba como criar grupos](use-groups-to-manage-users-and-devices-with-microsoft-intune.md#create-groups).

## <a name="step-4-configure-company-portal"></a>Etapa 4: Configurar o Portal da Empresa

O Portal da Empresa do Intune é onde os usuários acessam os dados da empresa e podem fazer tarefas comuns, como o registro de dispositivo, a instalação de aplicativos e a localização de informações de assistência do departamento de TI.

> [!TIP]
> Quando você personaliza o Portal da Empresa, as configurações se aplicam ao site do Portal da Empresa e aos aplicativos do Portal da Empresa.

Personalizar o Portal da Empresa ajuda a fornecer uma experiência familiar e útil para os usuários finais. Para fazer isso, basta fazer logon no [Console de administração do Microsoft Intune](https://manage.microsoft.com) como administrador de serviços ou locatário, escolher **Administrador** &gt; **Portal da Empresa** e definir as configurações do Portal da Empresa.

![admin-console-admin-workspace-comp-portal-settings](../media/cp_sa_cpsetup.PNG)

### <a name="company-contact-information-and-privacy-statement"></a>Declaração de privacidade e informações de contato de empresa

O nome da empresa é exibido como o título do Portal da Empresa. Os detalhes e as informações de contato são exibidos para os usuários na tela Contatar TI do Portal da Empresa. A política de privacidade é exibida quando um usuário clica no link de privacidade.

|Nome do campo|Comprimento máx.|Mais informações|
    |----------|------------------------|----------------|
    |Nome da empresa|40|Este é o nome exibido como título do Portal da Empresa. **Observação**: apenas caracteres alfanuméricos. Este campo não dá suporte a caracteres especiais.|
    |Nome do contato do departamento de TI|40|Esse nome é exibido na página **Contatar TI**.|
    |Telefone do departamento de TI|20|Este número de contato é exibido na página **Contatar TI**.|
    |Endereço de email do departamento de TI|40|Este endereço de contato é exibido na página **Contatar TI**. Você deve inserir um endereço de email válido no formato **alias@domainname.com**.|
    |Informações adicionais|120|Estas informações são exibidas na página **Contatar TI**.|
    |URL de política de privacidade de empresa|79|Você pode especificar a política de privacidade de sua própria empresa que será exibida quando os usuários clicarem nos links de privacidade do Portal da Empresa. Você deve digitar uma URL válida no formato https://www.contoso.com.|

### <a name="support-contacts"></a>Contatos de suporte
O site de suporte é exibido para os usuários no Portal da Empresa para que eles possam acessar o suporte online.

|Nome do campo|Comprimento máx.|Mais informações|
    |----------|------------------------|----------------|
    |URL do site de suporte|150|Se tiver um site de suporte que queira que os usuários usem, especifique o URL aqui. A URL deve estar no formato https://www.contoso.com. Se você não especificar uma URL, nada será exibido no site de suporte da página **Contatar TI**, no Portal da Empresa.|
    |Nome do site|40|Este é o nome amigável exibido para a URL do site de suporte. Se você especificar uma URL do site de suporte e nenhum nome amigável, **Ir para o site da TI** será exibido na página **Contatar IT** do Portal da Empresa.|


### <a name="company-branding-customization"></a>Personalização da identidade visual da empresa

Você pode personalizar o Portal da Empresa com o logotipo e o nome da empresa, uma cor de tema e uma tela de fundo.

|Nome do campo|Mais informações|
    |----------|----------------|
    |Cores do tema|Selecione uma cor de tema para aplicar ao Portal da Empresa.|
    |Incluir o logotipo da empresa|Ao habilitar esta opção, você pode carregar o logotipo da empresa para ser exibido no Portal da Empresa. Você pode carregar dois logotipos: um que será exibido quando o segundo plano do Portal da Empresa for branco e outro que será exibido quando o segundo plano estiver usando a sua cor de tema selecionada. Cada logotipo deve ser um arquivo .png ou .jpg, ter a resolução mínima de 400 x 100 pixels e ter 750 KB ou menos em tamanho.|
    |Escolha uma tela de fundo para o aplicativo do Portal da Empresa|Esta configuração afeta somente a tela de fundo do aplicativo do Portal da Empresa.|


Depois de salvar suas alterações, é possível usar os links fornecidos na parte inferior da página do **Portal da Empresa** do console de administração para exibir o site do Portal da Empresa. Esses links não podem ser alterados. Quando um usuário entra, esses links exibem o Portal da Empresa das suas assinaturas.

## <a name="step-5-assign-user-licenses"></a>Etapa 5: Atribuir licenças de usuário

Você usa o **Portal de gerenciamento do Office 365** para adicionar manualmente usuários baseados em nuvem e atribuir licenças a contas de usuário baseadas em nuvem e contas sincronizadas do seu Active Directory local ao Azure AD (Azure Active Directory). É possível [sincronizar usuários locais com o Azure AD](../get-started/domain-names-for-microsoft-intune#to-synchronize-on-premises-users-with-azure-ad.md).

1.  Entre no [Portal de gerenciamento do Office 365](https://portal.office.com/Admin/Default.aspx) usando suas credenciais de administrador de locatário.

2.  Selecione a conta de usuário a que deseja atribuir uma licença de usuário do Intune e marque a caixa de seleção **Microsoft Intune** nas propriedades da conta de usuário.

3.  Agora a conta de usuário será adicionada ao grupo de usuários do Microsoft Intune, o que concede ao usuário permissões para usar o serviço e registrar seus dispositivos para gerenciamento.

### <a name="to-synchronize-on-premises-users-with-azure-ad"></a>Para sincronizar usuários locais com o Azure AD

1. [Adicione o sufixo UPN](https://technet.microsoft.com/en-us/library/cc772007.aspx) a seu domínio personalizado no seu Active Directory local.
2. Defina o novo sufixo UPN para os usuários locais que você pretende importar.
3. Execute [Sincronização do Azure AD Connect](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/) para integrar seus usuários locais com o AD do Azure.
4. Depois que as informações da conta foram sincronizadas com êxito, você pode atribuir licenças do Microsoft Intune usando o [Portal de gerenciamento do Office 365](https://portal.office.com/Admin/Default.aspx).

## <a name="step-6-enable-enrollment"></a>Etapa 6: Habilitar registro
Depois de configurar a autoridade de MDM, você precisa configurar o gerenciamento de dispositivos para os sistemas operacionais aos quais sua organização quer dar suporte. As etapas necessárias para configurar o gerenciamento de dispositivos variam de acordo com o sistema operacional. Por exemplo, o sistema operacional Android não requer nenhuma ação no console de administração do Intune. Por outro lado, o Windows e iOS exigem uma relação de confiança entre os dispositivos e o Intune para permitir o gerenciamento.

Configurar o gerenciamento para as seguintes plataformas:
- [iOS e Mac](set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Android](set-up-android-management-with-microsoft-intune.md)
- [Android for Work](set-up-android-for-work.md)
- [PCs e laptops com Windows](set-up-windows-device-management-with-microsoft-intune.md)
- [Windows 10 Mobile e Windows Phone](set-up-windows-phone-management-with-microsoft-intune.md)

Você também pode habilitar o [registro de dispositivos corporativos](manage-corporate-owned-devices).

## <a name="step-7-next-steps"></a>Etapa 7: Próximas etapas

Agora que o registro está habilitado, você deve configurar o gerenciamento para atender às necessidades da sua empresa. Veja a seguir algumas opções de gerenciamento:

- [Implantar políticas que gerenciam configurações e recursos em dispositivos](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
- [Habilitar o acesso a recursos da empresa como email, Wi-Fi e VPN](enable-access-to-company-resources-with-microsoft-intune.md)
- [Adicionar aplicativos](add-apps.md) e [implantar aplicativos](deploy-apps.md) em dispositivos gerenciados
- [Criar políticas de conformidade de dispositivo](introduction-to-device-compliance-policies-in-microsoft-intune.md) e [restringir o acesso com base na conformidade](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)



<!--HONumber=Nov16_HO1-->


