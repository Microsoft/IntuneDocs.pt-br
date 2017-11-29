---
title: "Aplicar políticas de conformidade aos dispositivos gerenciados por Jamf"
titlesuffix: Azure portal
description: Use a conformidade para ajudar a proteger dispositivos gerenciados pelo Jamf.
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c87fd2bd-7f53-4f1b-b985-c34f2d85a7bc
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6184552ce901ffc062f0453f169ec992049ae69b
ms.sourcegitcommit: 82088d297eef629e3da6011681ead442ae7e25f7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2017
---
# <a name="enforce-compliance-on-macs-managed-with-jamf-pro"></a>Impor a conformidade em Macs gerenciados com Jamf Pro

|Aplica-se a: Intune no Portal do Azure |
|--|
|Procurando uma documentação sobre o Intune no portal clássico? [Clique aqui](/intune/introduction-intune?toc=/intune-classic/toc.json).|
| |

|Atualmente em versão prévia privada|
|--|
|No momento, os recursos descritos neste tópico só estão disponíveis para clientes em versão prévia privada. Essa mensagem será removida quando eles forem lançados para todos os clientes.|
| |

Você pode usar o Azure Active Directory e as políticas de acesso condicional do Microsoft Intune para garantir que os usuários finais estejam em conformidade com os requisitos organizacionais. Você pode aplicar essas políticas aos Macs [gerenciados com Jamf Pro](conditional-access-integrate-jamf.md). Isso exige acesso aos consoles do Intune e do Jamf Pro.

## <a name="set-up-device-compliance-policies-in-intune"></a>Configurar as políticas de conformidade do dispositivo no Intune

1. Abra o Microsoft Azure, então navegue até **Intune** > **Conformidade do Dispositivo** > **Políticas**. Você pode criar políticas para macOS, incluindo a escolha de uma série de ações (por exemplo, enviar emails de aviso) para usuários e grupos que não estão em conformidade.
2. Procure os grupos que você quer e aplique as políticas neles.

## <a name="require-the-company-portal-app-for-macos"></a>Exigir o aplicativo Portal da Empresa para macOS

1. Em um dispositivo macOS, acesse https://aka.ms/macoscompanyportal para baixar a versão atual do aplicativo Portal da Empresa para macOS.
2. Abra o Jamf Pro, depois navegue até **Gerenciamento do computador** > **Pacotes**.
3. Crie um novo pacote com o aplicativo Portal da Empresa para macOS, depois clique em **Salvar**.
4. Abra **Computadores** > **Políticas**, depois selecione **Novo**.
5. Use a carga **Geral** para definir as configurações da política, incluindo a frequência de disparo e execução.
6. Selecione a carga **Pacotes** e clique em **Configurar**.
7. Clique em **Adicionar** para selecionar o pacote com o aplicativo Portal da Empresa.
8. Escolha **Instalar** no menu pop-up **Ação**.
9. Defina as configurações para o pacote.
10. Clique na guia **Escopo** para especificar em quais computadores o aplicativo Portal da Empresa deve ser instalado. Clique em **Salvar**. A política executará os dispositivos dentro do escopo na próxima vez o gatilho selecionado for disparado no computador e atender aos critérios da carga **Geral**.

## <a name="direct-your-users-to-register-jamf-pro-managed-devices-with-azure-active-directory"></a>Direcione seus usuários para registrar dispositivos gerenciados com o Jamf Pro com o Azure Active Directory

> [!NOTE]
> Você precisa [implantar o Portal da Empresa](conditional-access-assign-jamf.md#require-the-company-portal-app-for-macos) para macOS antes de executar as próximas etapas.  

Os usuários finais precisam iniciar o aplicativo Portal da Empresa por meio do Serviço de Autoatendimento do Jamf para registrar o dispositivo com o Azure AD como um dispositivo gerenciado pelo Jamf Pro.

1. No Jamf Pro, navegue até **Computadores** > **Políticas** e crie uma nova política para registro do dispositivo.
2. Configure a carga **Acesso Condicional**, incluindo a frequência de disparo e a execução. Defina a prioridade como **Após**.
3. Clique na guia **Escopo** e defina o escopo da política para todos os dispositivos de destino.
4. Clique na guia **Autoatendimento** para disponibilizar a política no Serviço de Autoatendimento do Jamf. Inclua a política na categoria **Conformidade do Dispositivo**. Clique em **Salvar**.
