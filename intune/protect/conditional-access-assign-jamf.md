---
title: Política de conformidade do dispositivo para dispositivos Jamf
titleSuffix: Microsoft Intune
description: Use políticas de conformidade do Microsoft Intune com Acesso Condicional do Azure Active Directory para ajudar a proteger dispositivos gerenciados pelo Jamf.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/02/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c87fd2bd-7f53-4f1b-b985-c34f2d85a7bc
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d3552eca925865eb3278b50490a6b70ee5807e2b
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72502459"
---
# <a name="enforce-compliance-on-macs-managed-with-jamf-pro"></a>Impor a conformidade em Macs gerenciados com Jamf Pro

Ao [integrar o Jamf Pro com o Intune](conditional-access-integrate-jamf.md), é possível usar as políticas de Acesso Condicional para impor a conformidade em seus dispositivos Mac com seus requisitos organizacionais.  Este artigo ajudará você com as seguintes tarefas:  

- Criar políticas de Acesso Condicional.
- Configurar o Jamf Pro para implantar o aplicativo Portal da Empresa do Intune em dispositivos gerenciados com o Jamf.
- Configurar dispositivos para se registro no Azure AD quando o usuário do dispositivo entrar no aplicativo Portal da Empresa iniciado pelo aplicativo de Autoatendimento do JAMF. O registro de dispositivo estabelece uma identidade no Azure AD que permite que o dispositivo seja avaliado por políticas de Acesso Condicional para acessar os recursos da empresa.  
 
Os procedimentos neste artigo exigem acesso aos consoles do Intune e do Jamf Pro.

## <a name="set-up-device-compliance-policies-in-intune"></a>Configurar as políticas de conformidade do dispositivo no Intune

1. Entre no [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) e acesse **Conformidade do dispositivo** > **Políticas**. 
2. Se você estiver usando uma política criada anteriormente, selecione essa política no console e siga para a próxima etapa deste procedimento.  
   
   Selecione **Criar Política** e especifique os detalhes de uma política com uma *Plataforma* do **macOS**. Defina as *Configurações* e *Ações para não conformidade* para atender aos seus requisitos organizacionais e, em seguida, selecione **Criar** para salvar a política.

3. No painel *Visão geral* das políticas, selecione **Atribuições**. Use as opções disponíveis para configurar quais usuários e grupos de segurança do Azure AD (Azure Active Directory) recebem essa política. A integração do Jamf com o Intune não é compatível com a política de conformidade direcionada a grupos de dispositivos. 

4. Ao selecionar **Salvar**, a política é implantada para os usuários.  

As políticas implantadas são direcionadas aos dispositivos usados pelos usuários atribuídos. Esses dispositivos são avaliados quanto à conformidade. Os dispositivos em conformidade são marcados como compatíveis na configuração "*Exigir que o dispositivo seja marcado como em conformidade*" no Azure AD.  

> [!NOTE]
> O Intune exige a conformidade da criptografia completa de disco.

## <a name="deploy-the-company-portal-app-for-macos-in-jamf-pro"></a>Implantar o aplicativo do Portal da Empresa para macOS no Jamf Pro

Crie uma política no Jamf Pro para implantar o Portal da Empresa do Intune. Essa política implanta o aplicativo do portal da empresa de modo que fique disponível no Autoatendimento do Jamf. Crie essa política antes de criar a política no Jamf Pro para os usuários registrarem dispositivos no Azure AD.  

Para concluir o procedimento a seguir, é necessário ter acesso a um dispositivo macOS e ao portal do Jamf Pro. 

### <a name="to-deploy-the-company-portal-app"></a>Para implantar o aplicativo do portal da empresa  

1. Em um dispositivo macOS, baixe, mas não instale, a versão atual do [aplicativo do Portal da Empresa para macOS](https://go.microsoft.com/fwlink/?linkid=862280). Você só precisa de uma cópia do aplicativo para carregar o aplicativo no Jamf Pro.  

2. Abra o Jamf Pro e acesse **Gerenciamento do computador** > **Pacotes**.

3. Crie um novo pacote com o aplicativo Portal da Empresa para macOS, depois selecione **Salvar**.

4. Abra **Computadores** > **Políticas**, depois selecione **Novo**.

5. Use o conteúdo **Geral** para definir configurações para a política. Essas configurações devem ser:
   - Gatilho: selecione **Registro concluído** e **Check-in recorrente**
   - Frequência de execução: selecione **Uma vez por computador**

6. Selecione a carga **Pacotes** e clique em **Configurar**.

7. Clique em **Adicionar** para selecionar o pacote com o aplicativo Portal da Empresa.

8. Selecione **Instalar** no menu pop-up **Ação**.
9. Defina as configurações para o pacote.

10. Selecione a guia **Escopo** para especificar em quais computadores o aplicativo Portal da Empresa será instalado. Selecione **Salvar**. A política será executada nos dispositivos dentro do escopo na próxima vez o gatilho selecionado for disparado no computador e os critérios da carga **Geral** forem atendidos.

## <a name="create-a-policy-in-jamf-pro-to-have-users-register-their-devices-with-azure-active-directory"></a>Criar uma política no Jamf Pro para fazer os usuários registrarem seus dispositivos com o Azure Active Directory  

Depois de [implantar o Portal da Empresa](conditional-access-assign-jamf.md#deploy-the-company-portal-app-for-macos-in-jamf-pro) para macOS por meio do Autoatendimento do Jamf Pro, você pode criar a política do Jamf Pro que registra o dispositivo do usuário no Azure AD. 

O registro do dispositivo requer que um usuário do dispositivo selecione manualmente o aplicativo Portal da Empresa do Intune no Autoatendimento do Jamf. Recomendamos que você entre em [contato com os usuários finais](../fundamentals/end-user-educate.md) por email, notificações do Jamf Pro ou qualquer outro método usado pela sua organização para direcioná-los a realizar essa ação para registrar os dispositivos. 

> [!WARNING]
> Iniciar o aplicativo Portal da Empresa manualmente (por exemplo, nas pastas Aplicativos ou Downloads) não registrará o dispositivo. Se um usuário do dispositivo iniciar o Portal da Empresa manualmente, ele verá um aviso, **“AccountNotOnboarded”** .

### <a name="to-create-the-registration-policy"></a>Para criar a política de registro  

1. No Jamf Pro, acesse **Computadores** > **Políticas** e crie uma nova política para registro do dispositivo.

2. Configure o conteúdo **Integração do Microsoft Intune**, incluindo a frequência de disparo e de execução.

3. Selecione a guia **Escopo** e defina o escopo da política para todos os dispositivos de destino.

4. Selecione a guia **Autoatendimento** para disponibilizar a política no Serviço de Autoatendimento do Jamf. Inclua a política na categoria **Conformidade do Dispositivo**. Clique em **Salvar**.

## <a name="validate-intune-and-jamf-integration"></a>Validar a integração do Intune e do Jamf  

Use o console do Jamf Pro para confirmar se a comunicação entre o Jamf Pro e o Microsoft Intune foi bem-sucedida. 

- No Jamf Pro, acesse **Configurações** > **Gerenciamento Global** > **Integração do Microsoft Intune** e, em seguida, selecione **Testar**. 

    O console exibe uma mensagem com o êxito ou a falha da conexão.  

Se o teste de conexão do console do Jamf Pro falhar, examine a configuração do JAMF. 


## <a name="removing-a-jamf-managed-device-from-intune"></a>Removendo um dispositivo gerenciado Jamf do Intune

É possível remover um dispositivo gerenciado pelo Jamf do console do Intune selecionando **Excluir** na exibição **Todos os dispositivos**. A exclusão de dispositivos em massa pode ser habilitada selecionando vários aplicativos e clicando em **Excluir**.

Obtenha informações sobre como [remover um dispositivo gerenciado pelo Jamf nos documentos do Jamf Pro](https://www.jamf.com/jamf-nation/articles/80/unmanaging-computers-while-preserving-their-inventory-information). Você também pode registrar um tíquete de suporte com o [Suporte do Jamf](https://www.jamf.com/support/) para obter suporte adicional. 

## <a name="next-steps"></a>Próximas etapas

- [Acesso condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
- [Introdução ao Acesso Condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)
