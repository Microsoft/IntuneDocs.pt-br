## <a name="enable-windows-10-automatic-enrollment"></a>Habilitar o registro automático do Windows 10

O registro automático permite que os usuários registrem computadores Windows 10 e dispositivos Windows 10 Mobile da empresa ou pessoais no Intune adicionando uma conta corporativa ou de estudante e concordando em ser gerenciados. Simples assim. Em segundo plano, o dispositivo do usuário registra e ingressa no Azure Active Directory. Depois de registrado, o dispositivo é gerenciado com o Intune.

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

4. Configure quais usuários serão registrados automaticamente.

  ![Captura de tela do portal do Azure](../media/auto-enroll-scope.png)

  Use os valores padrão para as seguintes URLs:
  - **Registro do MDM**
  - **Termos de uso do MDM**
  - **Conformidade do MDM**

5. Especifica quais dispositivos dos usuários devem ser gerenciados pelo Microsoft Intune. Os dispositivos do Windows 10 desses usuários serão automaticamente registrados para gerenciamento com o Microsoft Intune.

  - **Todos**
  - **Grupos**
  - **Nenhum**

6. Selecione **Salvar**.
