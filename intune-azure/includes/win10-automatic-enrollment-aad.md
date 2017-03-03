## <a name="set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium"></a>Configurar o registro automático do Windows 10 e Windows 10 Mobile com o Azure Active Directory Premium

O registro automático permite que os usuários registrem computadores Windows 10 e dispositivos Windows 10 Mobile da empresa ou pessoais no Intune adicionando uma conta corporativa ou de estudante e concordando em ser gerenciados. Simples assim. Em segundo plano, o dispositivo do usuário registra e ingressa no Azure Active Directory. Depois de registrado, o dispositivo é gerenciado com o Intune.

**Pré-requisitos**
- Assinatura do Azure Active Directory Premium ([assinatura de avaliação](http://go.microsoft.com/fwlink/?LinkID=816845))
- Assinatura do Microsoft Intune


### <a name="configure-automatic-mdm-enrollment"></a>Configurar o registro automático do MDM

1. No [portal de gerenciamento do Azure](https://portal.azure.com) (https://manage.windowsazure.com), navegue até o nó do **Active Directory** e selecione o diretório.

2. Escolha a guia **Aplicativos**. **Microsoft Intune** aparece na lista de aplicativos.

    ![Aplicativos do Azure AD com o Microsoft Intune](../media/aad-intune-app.png)

3. Selecione a seta para **Microsoft Intune**. Uma página que permite que você configure o Microsoft Intune será aberta.

4. Clique em **Configurar** para começar a configurar o registro automático de MDM com o Microsoft Intune.

5. Use os valores padrão para as seguintes URLs:

  - **Registro do MDM**
  - **Termos de uso do MDM** 
  - **Conformidade do MDM**

6.  Especifica quais dispositivos dos usuários devem ser gerenciados pelo Microsoft Intune. Os dispositivos do Windows 10 desses usuários serão automaticamente registrados para gerenciamento com o Microsoft Intune.

  - **Todos**
  - **Grupos**
  - **Nenhum**

7. Selecione **Salvar**.
