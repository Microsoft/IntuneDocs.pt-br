## <a name="enable-windows-10-automatic-enrollment"></a>Habilitar o registro automático do Windows 10

O registro automático permite que os usuários registrem seus dispositivos Windows 10 no Intune. Para fazer o registro, os usuários adicionam a conta de trabalho aos seus dispositivos pessoais ou ingressam os dispositivos corporativos no Azure Active Directory. Em segundo plano, o dispositivo registra-se e ingressa no Azure Active Directory. Depois de registrado, o dispositivo é gerenciado com o Intune.

**Pré-requisitos**
- Assinatura do Azure Active Directory Premium ([assinatura de avaliação](http://go.microsoft.com/fwlink/?LinkID=816845))
- Assinatura do Microsoft Intune


### <a name="configure-automatic-mdm-enrollment"></a>Configurar o registro automático do MDM

1. Entre no [Portal do Azure](https://portal.azure.com) e selecione **Azure Active Directory**.

  ![Captura de tela do portal do Azure](../media/auto-enroll-azure-main.png)

2. Selecione **Mobilidade (MDM e MAM)**.

  ![Captura de tela do portal do Azure](../media/auto-enroll-mdm.png)

3. Selecione **Microsoft Intune**.

  ![Captura de tela do portal do Azure](../media/auto-enroll-intune.png)

4. Configure **Escopo de Usuário MDM**. Especifique quais dispositivos dos usuários devem ser gerenciados pelo Microsoft Intune. Esses dispositivos Windows 10 podem ser registrados automaticamente para gerenciamento com o Microsoft Intune.

  - **Nenhum**
  - **Alguns**
  - **Todos**

   ![Captura de tela do portal do Azure](../media/auto-enroll-scope.png)

5. Use os valores padrão para as seguintes URLs:
    - **URL dos Termos de uso do MDM**
    - **URL de Descoberta do MDM**
    - **URL da Conformidade do MDM**

    > [!IMPORTANT]
    > Se **Escopo de usuário do MAM** e registro automático do MDM (**Escopo de usuário do MDM**) estiverem habilitados para um grupo, apenas o MAM será habilitado. Apenas o MAM é adicionado para usuários nesse grupo quando eles ingressam o dispositivo pessoal no local de trabalho. Os dispositivos não são automaticamente registrados no MDM.

6. Selecione **Salvar**.

Por padrão, autenticação de dois fatores não está habilitada para o serviço. No entanto, a autenticação de dois fatores é recomendável ao registrar um dispositivo. Para habilitar a autenticação de dois fatores, configure um provedor de autenticação de dois fatores no Azure AD e as suas contas de usuário para a autenticação multifator. Consulte [Guia de Introdução com o servidor de autenticação multifator do Azure](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud).
