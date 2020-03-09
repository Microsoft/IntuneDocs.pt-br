---
title: Criar política de Acesso Condicional do Exchange
titleSuffix: Microsoft Intune
description: Configurar o Acesso Condicional do Exchange Local e do Exchange Online Dedicado herdado no Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/26/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 127dafcb-3f30-4745-a561-f62c9f095907
ms.reviewer: demerson
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6650c091917ea265783044efd78b19a7e032e6a7
ms.sourcegitcommit: 5511b4f2b8a3383176a7afe2a22ad5a8d42caf7b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/28/2020
ms.locfileid: "78169290"
---
# <a name="configure-exchange-on-premises-access-for-intune"></a>Configurar o acesso local ao Exchange para o Intune

Este artigo mostra como configurar o Acesso Condicional para o Exchange local com base na conformidade do dispositivo.

Se você tiver um ambiente do Exchange Online Dedicado e precisar descobrir se ele está na configuração nova ou herdada, entre em contato com seu gerente de conta. Para controlar o acesso ao email para Exchange local ou para seu ambiente herdado do Exchange Online dedicado, configure o Acesso Condicional ao Exchange local no Intune.

## <a name="before-you-begin"></a>Antes de começar

Antes de poder configurar o Acesso Condicional, verifique se as seguintes configurações existem:

- Sua versão do Exchange é **Exchange 2010 SP1 ou posterior**. Há suporte para a matriz de CAS (Servidor de Acesso de Cliente) do servidor Exchange.

- Você precisa instalar e usar o [conector do Exchange local do Exchange ActiveSync](exchange-connector-install.md), que conecta o Intune ao Exchange local.

    >[!IMPORTANT]  
    >O Intune é compatível com vários conectores do Exchange locais por assinatura.  No entanto, cada conector do Exchange local é específico a um único locatário do Intune e não pode ser usado com nenhum outro locatário.  Se você tiver mais de uma organização do Exchange local, poderá configurar um conector separado para cada organização do Exchange.

- O conector para uma organização do Exchange local pode ser instalado em qualquer computador, desde que o computador possa se comunicar com o servidor do Exchange.

- Esse conector dá suporte a **ambiente de CAS do Exchange**. O Intune é compatível com a instalação diretamente do conector no servidor CAS do Exchange. Recomendamos que você instale-o em um computador separado devido à carga adicional que o conector coloca no servidor. Ao configurar o conector, você deve configurá-lo para que ele se comunique com um dos servidores de CAS do Exchange.

- O **Exchange ActiveSync** precisa ser configurado com autenticação baseada em certificado ou com entrada de credenciais de usuário.

- Quando políticas de Acesso Condicionais são configuradas e direcionadas ao usuário, antes de um usuário se conectar ao email, o **dispositivo** usado deverá:
  - Estar **registrado** no Intune ou em um computador ingressado no domínio.
  - **Registrado no Azure Active Directory**. Além disso, a ID do Exchange ActiveSync do cliente deve estar registrada com o Azure Active Directory.

- O DRS (Serviço de Registro de Dispositivos) do Azure AD será ativado automaticamente para clientes do Intune e do Office 365. Clientes que já implantaram o Serviço de Registro de Dispositivos do ADFS não veem os dispositivos registrados no Active Directory local. **Isso não se aplica a computadores Windows e dispositivos do Windows Phone**.

- **Estar em conformidade** com qualquer política de conformidade do dispositivo implantada nesse dispositivo.

- Se o dispositivo não atender às configurações de Acesso Condicional, uma das mensagens a seguir será apresentada ao usuário quando ele entrar:
  - Se o dispositivo não estiver registrado no Intune ou não estiver registrado no Azure Active Directory, a mensagem será exibida com instruções sobre como instalar o aplicativo Portal da Empresa, registrar o dispositivo e ativar o email. Esse processo também associa a ID do Exchange ActiveSync do dispositivo ao registro do dispositivo no Azure Active Directory.
  - Se o dispositivo não estiver em conformidade, será exibida uma mensagem que direcionará o usuário ao site Portal da Empresa do Intune ou ao aplicativo Portal da Empresa. No portal da empresa, ele pode encontrar informações sobre o problema e como corrigi-lo.

### <a name="support-for-mobile-devices"></a>Suporte para dispositivos móveis

- **Windows Phone 8.1 e posteriores** – para criar a política de acesso condicional, confira [Criar políticas de acesso condicional](../protect/create-conditional-access-intune.md)
- **Aplicativo de email nativos no iOS/iPadOS** – para criar a política de acesso condicional, confira [Criar políticas de acesso condicional](../protect/create-conditional-access-intune.md)
- **Clientes de email EAS, como Gmail no Android 4 ou posteriores** – para criar a política de acesso condicional, confira [Criar políticas de Acesso Condicional](../protect/create-conditional-access-intune.md)

- **Clientes de email do EAS em dispositivos de perfil de trabalho do Android** – dispositivos com perfil de trabalho do Android são compatíveis apenas com *Gmail* e *Nine Work for Android Enterprise*. Para obter Acesso Condicional para trabalhar com perfis de trabalho do Android, implante um perfil de email para os aplicativos *Gmail* ou *Nine Work for Android Enterprise* e implante esses aplicativos como uma instalação obrigatória. Depois de implantar o aplicativo, você pode configurar o acesso condicional com base no dispositivo.

#### <a name="to-set-up-conditional-access-for-android-work-profile-devices"></a>Para configurar o acesso condicional para dispositivos de perfil de trabalho do Android

  1. Entre no [Centro de Administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
  
  2. Implante o aplicativo Gmail ou Nine Work conforme **Necessário**.

  3. Selecione **Dispositivos** > **Perfis de configuração** > **Criar perfil**, insira **Nome** e **Descrição** para o perfil.

  4. Selecione **Android Enterprise** em **Plataforma**; selecione **Email** em **Tipo de perfil**.

  5. Defina as [configurações de perfil de email](https://docs.microsoft.com/intune/configuration/email-settings-android-enterprise#android-enterprise).

  6. Quando terminar, selecione **OK** > **Criar** para salvar suas alterações.

  7. Depois de criar o perfil de email, [atribua-o a grupos](https://docs.microsoft.com/intune/device-profile-assign).

  8. Configurar [acesso condicional baseado em dispositivo](https://docs.microsoft.com/intune/protect/conditional-access-intune-common-ways-use#device-based-conditional-access).

> [!NOTE]
> O uso do Microsoft Outlook para Android e iOS/iPadOS por meio do conector local do Exchange não é compatível. Se você quiser aproveitar as políticas de Acesso Condicional do Azure Active Directory e as Políticas de Proteção de Aplicativo do Intune com o Outlook para iOS/iPadOS e Android em suas caixas de correio locais, confira [Usando a Autenticação Moderna híbrida com o Outlook para iOS/iPadOS e Android](https://docs.microsoft.com/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth).

### <a name="support-for-pcs"></a>Suporte para computadores

O aplicativo nativo de **Email** do Windows 8.1 e versões posteriores (quando registrado no MDM com Intune)

## <a name="configure-exchange-on-premises-access"></a>Configurar o acesso local ao Exchange

Antes de poder usar o procedimento a seguir para configurar o controle de acesso local do Exchange, você deve instalar e configurar pelo menos um [conector do Exchange local do Intune](exchange-connector-install.md) para o Exchange local.

1. Entre no [Centro de Administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Vá para **Administração de locatário** > **Acesso ao Exchange** e, em seguida, selecione **Acesso local do Exchange**.

3. No painel **Acesso ao Exchange local**, escolha **Sim** para *Habilitar o controle de acesso do Exchange local*.

   > [!div class="mx-imgBorder"]
   > ![Captura de tela de exemplo da tela de acesso local do Exchange](./media/conditional-access-exchange-create/exchange-on-premises-access.png)

4. Em **Atribuição**, escolha **Selecionar grupos para incluir** e selecione um ou mais grupos para configurar o acesso.

   Os membros dos grupos selecionados têm a política de Acesso Condicional para acesso ao Exchange local aplicada a eles. Os usuários que recebem essa política precisam registrar seus dispositivos no Intune e atender aos perfis de conformidade antes de poderem acessar o Exchange local.

   > [!div class="mx-imgBorder"]
   > ![Selecionar grupos para incluir](./media/conditional-access-exchange-create/select-groups.png)

5. Para excluir grupos, escolha **Selecionar grupos para excluir** e, em seguida, selecione um ou mais grupos isentos de requisitos para registrar dispositivos e para ficar em conformidade com os perfis de conformidade antes de acessar o Exchange local.

   Selecione **Salvar** para salvar a configuração e retornar para o painel **Acesso do Exchange**.

6. Depois, defina as configurações para o conector do Exchange local do Intune. No console, selecione **Administrador do locatário** > **Acesso do Exchange**> **Conector local do Exchange ActiveSync** e selecione o conector para a organização do Exchange que você deseja configurar.

7. Para **Notificações de usuário**, selecione **Editar** para abrir o fluxo de trabalho **Editar organização**, em que é possível modificar a mensagem *Notificação do usuário*.

   > [!div class="mx-imgBorder"]
   > ![Captura de tela de exemplo do fluxo de trabalho Editar organização para notificações](./media/conditional-access-exchange-create/edit-organization-user-notification.png)

   Modificar a mensagem de email padrão que será enviada aos usuários se o dispositivo deles não estiver em conformidade e se quiserem acessar o Exchange local. O modelo de mensagem usa a linguagem de marcação. Também é possível ver a versão prévia de aparência da mensagem conforme você digita

   Selecione **Revisar + salvar** e **Salvar** para salvar suas edições e concluir a configuração de acesso ao Exchange local.

   > [!TIP]
   > Para saber mais sobre a linguagem de marcação, consulte este [artigo](https://en.wikipedia.org/wiki/Markup_language) da Wikipédia.

8. Em seguida, selecione **Configurações avançadas de acesso do Exchange ActiveSync** para abrir o fluxo de trabalho *Configurações avançadas de acesso do Exchange ActiveSync* no qual você configura as regras de acesso ao dispositivo.

   > [!div class="mx-imgBorder"]
   > ![Captura de tela de exemplo do fluxo de trabalho Editar Organização para configurações avançadas](./media/conditional-access-exchange-create/edit-organization-advanced-settings.png)

   - Para **Acesso de dispositivo não gerenciado**, defina a regra padrão global para acesso de dispositivos que não são afetados pelo Acesso Condicional ou outras regras:

     - **Permitir acesso**: todos os dispositivos podem acessar o Exchange local imediatamente. Os dispositivos que pertencem aos usuários nos grupos configurados como incluídos no procedimento anterior serão bloqueados se, posteriormente, forem avaliados como não compatíveis com as políticas ou não registrados no Intune.

     - **Bloquear acesso** e **Quarentena**: todos os dispositivos serão imediatamente impedidos de acessar o Exchange local inicialmente. Os dispositivos que pertencem aos usuários nos grupos configurados como incluídos no procedimento anterior obtêm acesso após o registro do dispositivo no Intune e são avaliados como compatíveis.

       Dispositivos Android que *não* executam o Samsung Knox Standard não dão suporte a essa configuração e estão sempre bloqueados.

   - Para **Exceções de plataforma de dispositivo**, selecione **Adicionar** e especifique os detalhes conforme necessário para o seu ambiente.

      Se a configuração **Acesso de dispositivo não gerenciado** estiver definida como **Bloqueado**, os dispositivos que estão registrados e em conformidade serão permitidos mesmo se houver uma exceção de plataforma para bloqueá-los.  

9. Selecione **OK** para salvar suas edições.

10. Selecione **Revisar + salvar** e **Salvar** para salvar a política de Acesso Condicional do Exchange.

## <a name="next-steps"></a>Próximas etapas

Em seguida, crie uma política de conformidade e a atribua aos usuários do Intune para avaliar os dispositivos móveis deles. Confira [Introdução à conformidade do dispositivo](device-compliance-get-started.md).

[Solucionar problemas do conector do Exchange local do Intune no Microsoft Intune](https://support.microsoft.com/help/4471887)
