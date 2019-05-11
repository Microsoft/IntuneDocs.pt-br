---
ms.openlocfilehash: fbfff91d2993becc99e2132285bef78d245ff50e
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61497933"
---
## <a name="enable-windows-10-automatic-enrollment"></a>Habilitar o registro automático do Windows 10

O registro automático permite que os usuários registrem seus dispositivos com Windows 10 no Intune ao adicionar a conta de trabalho a seus dispositivos pessoais, ou ao ingressar seus dispositivos corporativos ao Azure Active Directory. Em segundo plano, o dispositivo do usuário registra-se e ingressa no Azure Active Directory. Depois de registrado, o dispositivo é gerenciado com o Intune.

**Pré-requisitos**
- Assinatura do Azure Active Directory Premium ([assinatura de avaliação](http://go.microsoft.com/fwlink/?LinkID=816845))
- Assinatura do Microsoft Intune


### <a name="configure-automatic-mdm-enrollment"></a>Configurar o registro automático do MDM

1. Entre no [Portal de Gerenciamento do Azure](https://portal.azure.com) (https://manage.windowsazure.com) e selecione **Azure Active Directory**.

   ![Captura de tela do portal do Azure](../media/auto-enroll-azure-main.png)

2. Selecione **Mobilidade (MDM e MAM)**.

   ![Captura de tela do portal do Azure](../media/auto-enroll-mdm.png)

3. Selecione **Microsoft Intune**.

   ![Captura de tela do portal do Azure](../media/auto-enroll-intune.png)

4. Configure **Escopo de Usuário MDM**. Especifique quais dispositivos dos usuários devem ser gerenciados pelo Microsoft Intune. Os dispositivos do Windows 10 desses usuários serão automaticamente registrados para gerenciamento com o Microsoft Intune.

   - **Nenhum**
   - **Alguns**
   - **Todos**

   ![Captura de tela do portal do Azure](../media/auto-enroll-scope.png)

5. Use os valores padrão para as seguintes URLs:
   - **URL dos Termos de uso do MDM**
   - **URL de Descoberta do MDM**
   - **URL da Conformidade do MDM**

6. Selecione **Salvar**.

Por padrão, autenticação de dois fatores não está habilitada para o serviço. No entanto, a autenticação de dois fatores é recomendável ao registrar um dispositivo. Antes de solicitar a autenticação de dois fatores para esse serviço, você deve configurar um provedor de autenticação de dois fatores no Azure Active Directory e configurar suas contas de usuário para autenticação multifator. Consulte [Guia de Introdução com o servidor de autenticação multifator do Azure](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud).
