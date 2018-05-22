---
title: Pré-requisitos para registro de dispositivos móveis
description: Configure os pré-requisitos de MDM (gerenciamento de dispositivo móvel) e prepare-se para registrar diferentes sistemas operacionais.
keywords: ''
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/31/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 44fd4af0-f9b0-493a-b590-7825139d9d40
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 57dfc1bf2765de6c2e02352caca58f3859742fd6
ms.sourcegitcommit: 49dc405bb26270392ac010d4729ec88dfe1b68e4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/21/2018
---
# <a name="prerequisites-for-mobile-device-management-in-intune"></a>Pré-requisitos para gerenciamento de dispositivo móvel no Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

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
> [Exibir documentos do SCCM >](https://docs.microsoft.com/sccm/mdm/deploy-use/setup-hybrid-mdm)

## <a name="step-1-enable-connections"></a>Etapa 1: Habilitar conexões

Antes de habilitar o registro de dispositivo móvel, certifique-se de ter feito o seguinte:
- [Examinar as portas e URLs de rede necessárias](/intune/network-bandwidth-use)
- [Adicionar e verificar o nome de domínio](/intune/custom-domain-name-configure)

## <a name="step-2-set-mdm-authority"></a>Etapa 2: Configurar a autoridade de MDM
A autoridade de MDM define o serviço de gerenciamento que tem permissão para gerenciar um conjunto de dispositivos. As opções para a autoridade de MDM incluem o Intune e o Configuration Manager com Intune. Se você definir o Configuration Manager como a autoridade de gerenciamento, nenhum outro serviço poderá ser usado para gerenciamento de dispositivo móvel.

>[!IMPORTANT]
> No Configuration Manager versão 1610 ou posterior e no Microsoft Intune versão 1705, você altera a autoridade de MDM sem precisar contatar o Suporte da Microsoft e sem cancelar o registro e registrar novamente os dispositivos gerenciados existentes. Para obter detalhes, consulte [O que fazer se você escolher a configuração incorreta de autoridade de MDM](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting).

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com), selecione **Administrador** &gt; **Gerenciamento de Dispositivo Móvel**.

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


|          Nome do campo           | Comprimento máx. |                                                                                       Mais informações                                                                                        |
|-------------------------------|------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         Nome da empresa          |     40     |                Este é o nome exibido como título do Portal da Empresa. <strong>Observação</strong>: apenas caracteres alfanuméricos. Este campo não dá suporte a caracteres especiais.                |
|  Nome do contato do departamento de TI   |     40     |                                                                Esse nome é exibido na página <strong>Contatar TI</strong>.                                                                |
|  Telefone do departamento de TI   |     20     |                                                           Este número de contato é exibido na página <strong>Contatar TI</strong>.                                                           |
|  Endereço de email do departamento de TI  |     40     |             Este endereço de contato é exibido na página <strong>Contatar TI</strong>. Você deve inserir um endereço de email válido no formato <strong>alias@domainname.com</strong>.              |
|    Informações adicionais     |    120     |                                                            Estas informações são exibidas na página <strong>Contatar TI</strong>.                                                             |
| URL de política de privacidade de empresa |     79     | Você pode especificar a política de privacidade de sua própria empresa que será exibida quando os usuários clicarem nos links de privacidade do Portal da Empresa. Você deve inserir uma URL válida no formato https://www.contoso.com. |

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

Você usa o **Portal de gerenciamento do Office 365** para adicionar manualmente usuários baseados em nuvem e atribuir licenças a contas de usuário baseadas em nuvem e contas sincronizadas do seu Active Directory local ao Azure AD (Azure Active Directory). É possível [sincronizar usuários locais com o Azure AD](/intune/users-permissions-add#how-to-sync-on-premises-users-with-azure-ad).

1.  Entre no [Portal de gerenciamento do Office 365](https://portal.office.com/Admin/Default.aspx) usando suas credenciais de administrador de locatário.

2.  Selecione a conta de usuário a que deseja atribuir uma licença de usuário do Intune e marque a caixa de seleção **Microsoft Intune** nas propriedades da conta de usuário.

3.  Agora a conta de usuário será adicionada ao grupo de usuários do Microsoft Intune, o que concede ao usuário permissões para usar o serviço e registrar seus dispositivos para gerenciamento.

### <a name="to-synchronize-on-premises-users-with-azure-ad"></a>Para sincronizar usuários locais com o Azure AD

1. [Adicione o sufixo UPN](https://technet.microsoft.com/library/cc772007.aspx) a seu domínio personalizado no seu Active Directory local.
2. Defina o novo sufixo UPN para os usuários locais que você pretende importar.
3. Execute [Sincronização do Azure AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) para integrar seus usuários locais com o AD do Azure.
4. Depois que as informações da conta foram sincronizadas com êxito, você pode atribuir licenças do Microsoft Intune usando o [Portal de gerenciamento do Office 365](https://portal.office.com/Admin/Default.aspx).

## <a name="step-6-enable-enrollment"></a>Etapa 6: Habilitar registro
Depois de configurar a autoridade de MDM, você precisa configurar o gerenciamento de dispositivos para os sistemas operacionais aos quais sua organização quer dar suporte. As etapas necessárias para configurar o gerenciamento de dispositivos variam de acordo com o sistema operacional. Por exemplo, o sistema operacional Android não requer nenhuma ação no console de administração do Intune. Por outro lado, o Windows e iOS exigem uma relação de confiança entre os dispositivos e o Intune para permitir o gerenciamento.

Configurar o gerenciamento para as seguintes plataformas:
- [iOS e Mac](set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Android](set-up-android-management-with-microsoft-intune.md)
- [Android for Work](set-up-android-for-work.md)
- [Windows 10 Mobile e Windows Phone](set-up-windows-device-management-with-microsoft-intune.md)
- [PCs e laptops com Windows](manage-windows-pcs-with-microsoft-intune.md) (software cliente do Intune)

Você também pode habilitar o [registro de dispositivos corporativos](manage-corporate-owned-devices.md).

## <a name="step-7-next-steps"></a>Etapa 7: Próximas etapas

Agora que o registro está habilitado, você deve configurar o gerenciamento para atender às necessidades da sua empresa. Veja a seguir algumas opções de gerenciamento:

- [Implantar políticas que gerenciam configurações e recursos em dispositivos](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
- [Habilitar o acesso a recursos da empresa como email, Wi-Fi e VPN](enable-access-to-company-resources-with-microsoft-intune.md)
- [Adicionar aplicativos](add-apps.md) e [implantar aplicativos](deploy-apps.md) em dispositivos gerenciados
- [Criar políticas de conformidade de dispositivo](introduction-to-device-compliance-policies-in-microsoft-intune.md) e [restringir o acesso com base na conformidade](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)

## <a name="what-to-do-if-you-choose-the-wrong-mdm-authority-setting"></a>O que fazer se você escolher a configuração incorreta de autoridade de MDM

Se você decidir que escolheu a configuração incorreta de autoridade de MDM e precisar alterá-la, terá as opções a seguir.

### <a name="change-the-mdm-authority-yourself"></a>Alterar a autoridade de MDM por conta própria
A partir do Configuration Manager versão 1610 e do Microsoft Intune versão 1705, você poderá alterar a autoridade de MDM do Microsoft Intune para o Configuration Manager (híbrido) ou vice-versa sem precisar contatar o Suporte da Microsoft e sem cancelar o registro e registrar novamente os dispositivos gerenciados existentes. Para obter detalhes, consulte [Alterar a autoridade de MDM]( /sccm/mdm/deploy-use/change-mdm-authority).

### <a name="contact-microsoft-support"></a>Contate o Suporte da Microsoft
Caso você tenha o Configuration Manager anterior à versão 1610, deverá contatar o Suporte da Microsoft. Não é possível alterar a configuração por conta própria. Antes de contatar o Suporte da Microsoft, examine as informações a seguir, que descrevem as informações que o Suporte da Microsoft precisará de você para fazer a alteração.

Há três maneiras possíveis pelas quais a autoridade de MDM pode ser redefinida. Na solicitação do Suporte, você precisará escolher a maneira que se aplica à sua situação. Se o cenário que você está solicitando não estiver listado, faça um acompanhamento com o Suporte da Microsoft.

O Suporte da Microsoft solicitará que você confirme as seguintes informações:

- ID do Locatário: o domínio usado para fazer logon no serviço (por exemplo, intune.onmicrosoft.com)
- A autoridade de MDM para a qual você deseja alterar
- Confirmação das etapas de pré-requisito concluídas, conforme listado abaixo

Se você estiver usando a coexistência, precisará verificar as listas de verificação do Intune e do Office 365.

#### <a name="reset-mdm-authority-from-intune-to-configuration-manager"></a>Redefinir a autoridade de MDM do Intune para o Configuration Manager

Conclua estas etapas antes de contatar o Suporte da Microsoft para redefinir sua autoridade de MDM.

- Desative todos os dispositivos no console de administração do Intune. Não tente desativar um dispositivo no próprio dispositivo. 
- Exclua o Service To Service Connector (em **Administração** > **Gerenciamento de Dispositivo Móvel** > **Microsoft Exchange**) ou desabilite o Exchange Connector se você o tiver configurado.
- Remova a função Gerenciador de Registro de Dispositivo em **Administrador** > **Gerenciador de Registro de Dispositivo**.
- Desligue o Mapeamento de Grupo de Dispositivos em **Administrador** > **Gerenciamento de Dispositivo Móvel** > **Mapeamento de Grupo de Dispositivos**.
- Exclua as chaves de sideload em **Administrador** > **Gerenciamento de Dispositivo Móvel** > **Windows** > **Chaves de Sideload**.
- Exclua o certificado APNs do iOS na página **Administrador** > **Gerenciamento de Dispositivo Móvel** > **iOS**.
- Exclua o token DEP do iOS na página **Administrador** > **Gerenciamento de Dispositivo Móvel** > **iOS**.
- Exclua todas as políticas destinadas a Dispositivos de MDM em **Política** > **Políticas de Configuração**.
- Exclua todos os aplicativos publicados destinados a Dispositivos de MDM em **Aplicativos** > **Software Gerenciado**.

#### <a name="reset-mdm-authority-from-configuration-manager-to-intune"></a>Redefinir a autoridade de MDM do Configuration Manager para o Intune

Conclua estas etapas antes de contatar o Suporte da Microsoft para redefinir sua autoridade de MDM.

- Desative todos os dispositivos (que são gerenciados como dispositivos móveis) no Console do Configuration Manager. Não tente desativar um dispositivo no próprio dispositivo. 
- Remova todos os usuários do Grupo de Usuários do Intune. Aponte a assinatura do Intune para uma coleção vazia de usuários ou remova todos os usuários da coleção de destino.  No CloudUserSync.log, confirme se os usuários foram removidos. 
- Desmarque a plataforma iOS para limpar o certificado APNs.
- Exclua todos os aplicativos publicados destinados a dispositivos de MDM.
- Exclua todas as políticas destinadas a dispositivos de MDM.
- Remova o Conector do Windows Intune por meio do Console do Configuration Manager (aplicável somente ao R2 SP1 ou abaixo).
-Remova a assinatura do Intune clicando com o botão direito do mouse na assinatura e selecionando **Excluir**.
- Reinicie o Serviço SMS Executive.
- Forneça para nós alguns usuários de exemplo para que possamos verificar, após a conclusão do processo, se as licenças do Configuration Manager foram removidas.

#### <a name="reset-mdm-authority-from-office-365-to-configuration-manager"></a>Redefinir a autoridade de MDM do Office 365 para o Configuration Manager

1. Vá até [https://protection.office.com](https://protection.office.com).
2. Selecione a guia **Políticas de Segurança** e selecione **Gerenciamento de Dispositivo**.
3. Desative todos os dispositivos escolhendo **Apagamento Seletivo**. Não tente desativar um dispositivo no próprio dispositivo. Se o apagamento seletivo estiver desabilitado, nenhuma ação adicional será necessária.
4. Selecione a guia **Políticas de Segurança** e selecione **Políticas de Segurança do Dispositivo**.
5. Selecione **Excluir** para todas as políticas existentes. Se as políticas estiverem em um estado pendente, nenhuma ação adicional será necessária.

>[!NOTE]
>O certificado APsN do iOS não pode ser excluído e permanece anexado à conta.

#### <a name="next-steps-for-mdm-authority-resets"></a>Próximas etapas para redefinições de autoridade de MDM

Depois que o Suporte da Microsoft verificar os itens da lista de verificação aplicável, a redefinição da autoridade de MDM poderá levar até três dias úteis, mas geralmente ocorre em um dia.

>[!IMPORTANT]
>Não tente configurar sua assinatura até que o Suporte da Microsoft confirme que a redefinição foi concluída com êxito. A configuração prematura poderá corromper a assinatura e/ou afetar sua capacidade de usar o serviço Intune.
