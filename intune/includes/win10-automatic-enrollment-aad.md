---
ms.openlocfilehash: 6f5b0c8df86cf5bf1206c1cccb879e37c7944a21
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "71912788"
---
## <a name="enable-windows-10-automatic-enrollment"></a>Habilitar o registro automático do Windows 10

O registro automático permite que os usuários registrem seus dispositivos Windows 10 no Intune. Para fazer o registro, os usuários adicionam a conta de trabalho aos seus dispositivos pessoais ou ingressam os dispositivos corporativos no Azure Active Directory. Em segundo plano, o dispositivo registra-se e ingressa no Azure Active Directory. Depois de registrado, o dispositivo é gerenciado com o Intune.

**Pré-requisitos**

- Assinatura do Azure Active Directory Premium ([assinatura de avaliação](http://go.microsoft.com/fwlink/?LinkID=816845))
- Assinatura do Microsoft Intune

### <a name="configure-automatic-mdm-enrollment"></a>Configurar o registro automático do MDM

1. Entre no [Portal do Azure](https://portal.azure.com) e selecione **Azure Active Directory**.

   ![Captura de tela do portal do Azure](../enrollment/media/windows-enroll/auto-enroll-azure-main.png)

2. Selecione **Mobilidade (MDM e MAM)** .

   ![Captura de tela do portal do Azure](../enrollment/media/windows-enroll/auto-enroll-mdm.png)

3. Selecione **Microsoft Intune**.

   ![Captura de tela do portal do Azure](../enrollment/media/windows-enroll/auto-enroll-intune.png)

4. Configure **Escopo de Usuário MDM**. Especifique quais dispositivos dos usuários devem ser gerenciados pelo Microsoft Intune. Esses dispositivos Windows 10 podem ser registrados automaticamente para gerenciamento com o Microsoft Intune.

   - **Nenhum** - registro automático do MDM desabilitado
   - **Alguns** - selecione os **Grupos** que podem inscrever seus dispositivos com Windows 10 automaticamente
   - **Todos** - todos os usuários podem inscrever seus dispositivos com Windows 10 automaticamente

      > [!IMPORTANT]
      > Para dispositivos BYOD, o escopo do usuário de MAM terá precedência se o escopo do usuário de MAM e o escopo do usuário de MDM (registro automático de MDM) estiverem habilitados para todos os usuários (ou para os mesmos grupos de usuários). Se você tiver configurado as políticas de WIP (Proteção de Informações do Windows), o dispositivo as usará em vez de registrar-se no MDM.
      >
      > Para dispositivos corporativos, o escopo do usuário MDM terá precedência se ambos os escopos estiverem habilitados. Os dispositivos são registrados no MDM.

   > [!NOTE]
   > O escopo de usuário do MDM deve ser definido como um grupo do Azure AD que contém objetos de usuário.

   ![Captura de tela do portal do Azure](../enrollment/media/windows-enroll/auto-enroll-scope.png)

5. Use os valores padrão para as seguintes URLs:
    - **URL dos Termos de uso do MDM**
    - **URL de Descoberta do MDM**
    - **URL da Conformidade do MDM**

6. Selecione **Salvar**.

Por padrão, autenticação de dois fatores não está habilitada para o serviço. No entanto, a autenticação de dois fatores é recomendável ao registrar um dispositivo. Para habilitar a autenticação de dois fatores, configure um provedor de autenticação de dois fatores no Azure AD e as suas contas de usuário para a autenticação multifator. Consulte [Guia de Introdução com o servidor de autenticação multifator do Azure](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud).
