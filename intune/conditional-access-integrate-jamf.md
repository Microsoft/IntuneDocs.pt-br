---
title: Integrar o Jamf Pro ao Microsoft Intune para fins de conformidade | Microsoft Intune
description: Use políticas de conformidade do Microsoft Intune com acesso condicional do Azure Active Directory para ajudar a proteger dispositivos gerenciados pelo Jamf.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/16/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4b6dcbcc-4661-4463-9a36-698d673502c6
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: aa2fe73c0dab855f43daf71e9564f17490fa6366
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55846988"
---
# <a name="integrate-jamf-pro-with-intune-for-compliance"></a>Integrar o Jamf Pro ao Intune para fins de conformidade

Aplica-se a: Intune no portal do Azure

Caso sua organização use o [Jamf Pro](https://www.jamf.com) para gerenciar dispositivos Mac dos usuários finais, use as políticas de conformidade do Microsoft Intune com o acesso condicional do Azure Active Directory para garantir que os dispositivos em sua organização estejam em conformidade.

## <a name="prerequisites"></a>Pré-requisitos

Você precisa do seguinte para configurar o acesso condicional com o Jamf Pro:

- Jamf Pro 10.1.0 ou mais recente
- [Aplicativo Portal da Empresa para macOS](https://aka.ms/macoscompanyportal)
- Dispositivos macOS com OS X 10.11 Yosemite ou mais recente

## <a name="connecting-intune-to-jamf-pro"></a>Conectar o Intune ao Jamf Pro

Para conectar o Intune ao Jamf Pro:

1. Crie um aplicativo no Azure
2. Permitir a integração do Intune ao Jamf Pro
3. Configurar o acesso condicional no Jamf Pro

## <a name="create-an-application-in-azure-active-directory"></a>Crie um aplicativo no Azure Active Directory

1. No [portal do Azure](https://portal.azure.com), acesse **Azure Active Directory** > **Registros de aplicativo**.
2. Selecione **+Novo registro de aplicativo**.
3. Insira um **nome de exibição**, como **Acesso condicional no Jamf**.
4. Selecione **Aplicativo Web/API**.
5. Especifique o **URL de logon** usando sua URL de instância Jamf Pro.
6. Selecione **Criar**. O aplicativo é criado e o portal apresenta os detalhes do aplicativo.
7. Salve uma cópia da **ID do Aplicativo** para o novo aplicativo. Você especificará essa ID em um procedimento posterior. Em seguida, selecione **Configurações** e acesse **Acesso à API** > **Chaves**.
8. No painel *Chaves*, especifique uma **Descrição**, o tempo de espera necessário antes que ela **Expire** e, em seguida, selecione **Salvar** para gerar a Chave do Aplicativo (Valor).

   > [!IMPORTANT]
   > A Chave de Aplicativo é mostrada apenas uma vez durante esse processo. Salve-a em algum lugar onde é possível recuperá-la facilmente.

8. No painel *Configurações* do aplicativo, navegue para **Acesso à API** > **Permissões Necessárias**. Selecione as permissões existentes e, em seguida, clique em **Excluir** e exclua todas as permissões. A exclusão das permissões existentes é necessária conforme você adiciona uma nova permissão e o aplicativo funciona apenas se tem a permissão exata necessária.  
9. Para atribuir uma nova permissão, selecione **+Adicionar** > **Selecionar uma API** > **API do Microsoft Intune** e, em seguida, clique em **Selecionar**.
10. No painel *Habilitar Acesso*, selecione **Enviar atributos do dispositivo para o Microsoft Intune** e, em seguida, clique em **Selecionar** e em **Concluído**.
11. No painel *Permissões necessárias*, selecione **Conceder Permissões** e, em seguida, **Sim** para aplicar as permissões necessárias para o aplicativo.

    > [!NOTE]
    > Se a Chave de Aplicativo expirar, você deverá criar uma nova Chave de Aplicativo no Microsoft Azure e, depois, atualizar os dados do Acesso Condicional no Jamf Pro. O Azure permite que você tenha a chave antiga e a nova chave ativas para evitar interrupções no serviço.

## <a name="enable-intune-to-integrate-with-jamf-pro"></a>Permitir a integração do Intune ao Jamf Pro

1. No [portal do Azure](https://portal.azure.com), abra **Microsoft Intune** > **Conformidade do Dispositivo** > **Gerenciamento de dispositivos de parceiros**.
2. Habilite o Conector de Conformidade para o Jamf colando a ID do Aplicativo salva no procedimento anterior no campo **ID do Aplicativo do Azure Active Directory para o Jamf**.
3. Selecione **Salvar**.

## <a name="configure-microsoft-intune-integration-in-jamf-pro"></a>Configurar a Integração do Microsoft Intune no Jamf Pro

1. No Jamf Pro, navegue até **Gerenciamento Global** > **Acesso Condicional**. Clique no botão **Editar** na guia **Integração do Microsoft Intune**.
2. Marque a caixa de seleção **Habilitar a Integração do Microsoft Intune**.
3. Forneça as informações necessárias sobre o seu locatário do Azure, incluindo **Local**, **Nome de domínio** e a **ID do Aplicativo** e **Chave de Aplicativo** salvas nas etapas anteriores.
4. Selecione **Salvar**. O Jamf Pro testará suas configurações e verificará o êxito.

## <a name="set-up-compliance-policies-and-register-devices"></a>Configurar políticas de conformidade e registrar dispositivos

Depois de configurar a integração entre o Intune e o Jamf, você precisará [aplicar políticas de conformidade aos dispositivos gerenciados pelo Jamf](conditional-access-assign-jamf.md).



## <a name="next-steps"></a>Próximas etapas

- [Aplicar políticas de conformidade aos dispositivos gerenciados por Jamf](conditional-access-assign-jamf.md)
- [Dados enviados pelo Jamf ao Intune](data-jamf-sends-to-intune.md)
