---
title: Política de conformidade do dispositivo para dispositivos Jamf | Microsoft Intune
titlesuffix: Microsoft Intune
description: Use políticas de conformidade do Microsoft Intune com acesso condicional do Azure Active Directory para ajudar a proteger dispositivos gerenciados pelo Jamf.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/02/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c87fd2bd-7f53-4f1b-b985-c34f2d85a7bc
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 65a82a171253a40b05c42abec3a12371c471e860
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55837383"
---
# <a name="enforce-compliance-on-macs-managed-with-jamf-pro"></a>Impor a conformidade em Macs gerenciados com Jamf Pro

Aplica-se a: Intune no portal do Azure

Você pode usar o Azure Active Directory e as políticas de acesso condicional do Microsoft Intune para garantir que os usuários finais estejam em conformidade com os requisitos organizacionais. Você pode aplicar essas políticas aos Macs [gerenciados com Jamf Pro](conditional-access-integrate-jamf.md). Isso exige acesso aos consoles do Intune e do Jamf Pro.

## <a name="set-up-device-compliance-policies-in-intune"></a>Configurar as políticas de conformidade do dispositivo no Intune

1. Abra o Microsoft Azure, então navegue até **Intune** > **Conformidade do Dispositivo** > **Políticas**. Você pode criar políticas para o macOS, incluindo a escolha de uma série de ações (por exemplo, enviar emails de aviso) para usuários e grupos que não estão em conformidade.
2. Procure os grupos que você quer e aplique as políticas neles.

> [!Note]
> O Intune exige a conformidade da criptografia completa de disco.

## <a name="deploy-the-company-portal-app-for-macos-in-jamf-pro"></a>Implantar o aplicativo do Portal da Empresa para macOS no Jamf Pro

Você deve implantar o aplicativo de Portal da Empresa para macOS no Jamf Pro como uma instalação de segundo plano seguindo o procedimento abaixo:

1. Em um dispositivo macOS, baixe a versão atual do [aplicativo do Portal da Empresa para macOS](https://go.microsoft.com/fwlink/?linkid=862280). Não instalar; você precisa de uma cópia do aplicativo para carregar Jamf Pro.
2. Abra o Jamf Pro, depois navegue até **Gerenciamento do computador** > **Pacotes**.
3. Crie um novo pacote com o aplicativo Portal da Empresa para macOS, depois clique em **Salvar**.
4. Abra **Computadores** > **Políticas**, depois selecione **Novo**.
5. Use o conteúdo **Geral** para definir configurações para a política. Essas configurações devem ser:
   - Gatilho: selecione **Registro concluído** e **Check-in recorrente**
   - Frequência de execução: selecione **Uma vez por computador**
6. Selecione a carga **Pacotes** e clique em **Configurar**.
7. Clique em **Adicionar** para selecionar o pacote com o aplicativo Portal da Empresa.
8. Escolha **Instalar** no menu pop-up **Ação**.
9. Defina as configurações para o pacote.
10. Clique na guia **Escopo** para especificar em quais computadores o aplicativo Portal da Empresa deve ser instalado. Clique em **Salvar**. A política executará os dispositivos dentro do escopo na próxima vez o gatilho selecionado for disparado no computador e atender aos critérios da carga **Geral**.

## <a name="create-a-policy-in-jamf-pro-to-have-users-register-their-devices-with-azure-active-directory"></a>Criar uma política no Jamf Pro para fazer os usuários registrarem seus dispositivos com o Azure Active Directory

> [!NOTE]
> Você precisa [implantar o Portal da Empresa](conditional-access-assign-jamf.md#deploy-the-company-portal-app-for-macos-in-jamf-pro) para macOS antes de executar as próximas etapas.  

Os usuários finais precisam iniciar o aplicativo Portal da Empresa por meio do Serviço de Autoatendimento do Jamf para registrar o dispositivo com o Azure AD como um dispositivo gerenciado pelo Jamf Pro. Isso exigirá que os usuários finais executem uma ação. É recomendável que você [contate seu usuário final](end-user-educate.md) por email, por notificações do Jamf Pro ou por quaisquer outros métodos para notificar os usuários finais a clicar no botão no Autoatendimento do Jamf.

> [!WARNING]
> O aplicativo do Portal da Empresa deve ser iniciado no Autoatendimento do Jamf para iniciar o registro do dispositivo. <br><br>Iniciar o aplicativo do Portal da Empresa manualmente (por exemplo, nas pastas Aplicativos ou Downloads) não registrará o dispositivo. Se um usuário final iniciar o Portal da Empresa manualmente, ele verá um aviso, 'AccountNotOnboarded'.

1. No Jamf Pro, navegue até **Computadores** > **Políticas** e crie uma nova política para registro do dispositivo.
2. Configure o conteúdo **Integração do Microsoft Intune**, incluindo a frequência de disparo e de execução.
3. Clique na guia **Escopo** e defina o escopo da política para todos os dispositivos de destino.
4. Clique na guia **Autoatendimento** para disponibilizar a política no Serviço de Autoatendimento do Jamf. Inclua a política na categoria **Conformidade do Dispositivo**. Clique em **Salvar**.

## <a name="removing-a-jamf-managed-device-from-intune"></a>Removendo um dispositivo gerenciado Jamf do Intune

É possível remover um dispositivo gerenciado pelo Jamf do console do Intune selecionando **Excluir** na exibição **Todos os dispositivos**. A exclusão de dispositivos em massa pode ser habilitada selecionando vários aplicativos e clicando em **Excluir**.

Obtenha informações sobre como [remover um dispositivo gerenciado pelo Jamf nos documentos do Jamf Pro](https://www.jamf.com/jamf-nation/articles/80/unmanaging-computers-while-preserving-their-inventory-information). Você também pode registrar um tíquete de suporte com o [Suporte do Jamf](https://www.jamf.com/support/) para obter suporte adicional. 

## <a name="next-steps"></a>Próximas etapas

- [Acesso condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
- [Instrodução ao acesso condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)
