---
title: Integrar o Jamf Pro ao Microsoft Intune para fins de conformidade
titlesuffix: ''
description: Use políticas de conformidade do Microsoft Intune com acesso condicional do Azure Active Directory para ajudar a proteger dispositivos gerenciados pelo Jamf.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4b6dcbcc-4661-4463-9a36-698d673502c6
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: e936ecd4ce6a9b0fa447ecfe8e45e04a78999a2b
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52185008"
---
# <a name="integrate-jamf-pro-with-intune-for-compliance"></a>Integrar o Jamf Pro ao Intune para fins de conformidade

Aplica-se a: Intune no Portal do Azure

Se sua organização usar o [Jamf Pro](https://www.jamf.com) para gerenciar os Macs de seus usuários finais, use as políticas de conformidade do Microsoft Intune com acesso condicional do Azure Active Directory para garantir que os dispositivos em sua organização estejam em conformidade.

## <a name="prerequisites"></a>Pré-requisitos

Você precisa do seguinte para configurar o acesso condicional com o Jamf Pro:

- Jamf Pro 10.1.0 ou mais recente
- [Aplicativo Portal da Empresa para macOS](https://aka.ms/macoscompanyportal)
- Dispositivos macOS com OS X 10.11 Yosemite ou mais recente

## <a name="connecting-intune-to-jamf-pro"></a>Conectar o Intune ao Jamf Pro

Você pode conectar o Intune ao Jamf Pro:

1. Criando um novo aplicativo no Azure
2. Permitindo a integração do Intune ao Jamf Pro
3. Configurar o acesso condicional no Jamf Pro

## <a name="create-a-new-application-in-azure-active-directory"></a>Criar um novo aplicativo no Azure Active Directory

1. Abra **Azure Active Directory** > **Registros de aplicativo**.
2. Clique em **+Novo registro do aplicativo**.
3. Insira um **nome de exibição**, como **Acesso condicional no Jamf**.
4. Selecione **Aplicativo Web/API**.
5. Especifique o **URL de logon** usando sua URL de instância Jamf Pro.
6. Clique em **Criar aplicativo**.
7. Salve a **ID do aplicativo** recém-criado e, em seguida, abra **Configurações** e navegue até **Acesso à API** > **Chaves** para criar uma nova Chave de Aplicativo. Insira um **Descrição**, quanto tempo aguardar antes que ela **Expire** e salve a Chave do Aplicativo.

   > [!IMPORTANT]
   > A Chave de Aplicativo é mostrada apenas uma vez durante esse processo. Salve-a em algum lugar onde é possível recuperá-la facilmente.

8. Abra **Configurações** e, em seguida, navegue até **Acesso à API** > **Permissões necessárias** e exclua todas as permissões.

   > [!NOTE]
   > Adicione uma nova permissão necessária. O aplicativo só funcionará corretamente se tiver a permissão exata necessária.

9. Selecione **API do Microsoft Intune** e clique em **Selecionar**.
10. Escolha **Enviar atributos do dispositivo ao Microsoft Intune** e clique em **Selecionar**.
11. Clique no botão **Conceder Permissões** depois de salvar as permissões necessárias para o aplicativo.

    > [!NOTE]
    > Se a Chave de Aplicativo expirar, você deverá criar uma nova Chave de Aplicativo no Microsoft Azure e, depois, atualizar os dados do Acesso Condicional no Jamf Pro. O Azure permite que você tenha a chave antiga e a nova chave ativas para evitar interrupções no serviço.

## <a name="enable-intune-to-integrate-with-jamf-pro"></a>Permitir a integração do Intune ao Jamf Pro

1. No Portal do Microsoft Azure, abra **Microsoft Intune** > **Conformidade do dispositivo** > **Gerenciamento de dispositivos do parceiro**.
2. Habilite o Conector de Conformidade para Jamf colando a ID do Aplicativo no campo **ID de Aplicativo do Azure Active Directory para Jamf**.
3. Clique em **Salvar**.

## <a name="configure-microsoft-intune-integration-in-jamf-pro"></a>Configurar a Integração do Microsoft Intune no Jamf Pro

1. No Jamf Pro, navegue até **Gerenciamento Global** > **Acesso Condicional**. Clique no botão **Editar** na guia **Integração do Microsoft Intune**.
2. Marque a caixa de seleção **Habilitar a Integração do Microsoft Intune**.
3. Forneça as informações necessárias sobre o seu locatário do Azure, incluindo **Local**, **Nome de domínio** e a **ID do Aplicativo** e **Chave de Aplicativo** salvas nas etapas anteriores.
4. Clique em **Salvar**. O Jamf Pro testará suas configurações e verificará o êxito.

## <a name="set-up-compliance-policies-and-register-devices"></a>Configurar políticas de conformidade e registrar dispositivos

Depois de concluir a configuração da integração entre o Intune e o Jamf, é necessário [aplicar políticas de conformidade a dispositivos gerenciados pelo Jamf](conditional-access-assign-jamf.md).

## <a name="information-shared-from-jamf-pro-to-intune"></a>Informações compartilhadas do Jamf Pro com o Intune

O Jamf Pro captura informações de inventário sobre os dispositivos macOS gerenciados. O Jamf Pro reporta estas informações para o Intune:

* ID do dispositivo do Azure AD
* Estado de inventário do JAMF (estado de inventário de um computador com check-in realizado no Jamf Pro nas últimas 24 horas)
* Versão do SO
* ID do usuário do Azure AD
* Criptografado (FileVault 2)
* Status do gatekeeper
* Senha: número mínimo de conjuntos de caracteres
* Expiração da senha (dias)
* Tipo de senha - simples, alfanumérica ou desconhecido
* Impedir o logon automático
* Comprimento de senha obrigatório
* Senha: número de senhas anteriores para evitar a reutilização
* Proteção de integridade do sistema
* Hora do último check-in
* Tipo de arquitetura
* Slots de RAM disponíveis
* Capacidade da bateria
* ROM de inicialização
* Velocidade do barramento
* Tamanho do cache
* Nome do Dispositivo
* Junção de Domínios
* ID do Jamf
* Endereço MAC
* Marca
* Modelo
* Identificador de modelo
* Velocidade do NIC
* Número de núcleos
* Número de Processadores
* SO
* Plataforma
* Velocidade do Processador
* Tipo de Processador
* Endereço MAC secundário
* Número de Série
* Versão do SMC
* Total de RAM
* UDID
* Email do usuário

## <a name="next-steps"></a>Próximas etapas

- [Aplicar políticas de conformidade aos dispositivos gerenciados por Jamf](conditional-access-assign-jamf.md)
