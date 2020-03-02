---
title: Adicionar e atribuir o aplicativo do Portal da Empresa do Windows 10 a dispositivos provisionados pelo Autopilot
titleSuffix: Microsoft Intune
description: Adicione e atribua o aplicativo do Portal da Empresa do Windows 10 para Intune a dispositivos provisionados pelo Autopilot.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/21/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c13d8d774037f0d2db5832af7f39c864330fef30
ms.sourcegitcommit: 47c9af81c385c7e893fe5a85eb79cf08e69e6831
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/25/2020
ms.locfileid: "77577279"
---
# <a name="add-and-assign-the-windows-10-company-portal-app-for-autopilot-provisioned-devices"></a>Adicionar e atribuir o aplicativo do Portal da Empresa do Windows 10 a dispositivos provisionados pelo Autopilot

Para gerenciar dispositivos e instalar aplicativos, os usuários podem usar o aplicativo Portal da Empresa. Você pode atribuir o aplicativo Portal da Empresa do Windows 10 diretamente do Intune. 

## <a name="prerequisites"></a>Pré-requisitos

Para dispositivos provisionados pelo Autopilot do Windows 10, é recomendável associar a conta da Microsoft Store para Empresas ao Intune. Para obter mais informações, confira [Como gerenciar aplicativos adquiridos por volume na Microsoft Store para Empresas com o Microsoft Intune](~/apps/windows-store-for-business.md).

As etapas abaixo mostram como escolher o Portal da Empresa (offline) para ser instalado. O aplicativo Portal da Empresa será instalado no contexto do dispositivo quando atribuído ao grupo do Autopilot e instalado no dispositivo antes do logon pelo usuário. 

## <a name="configure-settings-to-show-offline-apps"></a>Definir configurações para mostrar os aplicativos offline
1. Conecte-se ao [Microsoft Store para Empresas](https://www.microsoft.com/business-store) com sua conta do administrador.
2. Selecione a guia **Gerenciar** na parte superior da janela.
3. No painel esquerdo, selecione **Configurações**.
4. Defina **Mostrar aplicativos offline**, em **Experiência de compra**, para **Ativado**.  
    Os aplicativos licenciados offline são exibidos.

## <a name="get-the-offline-company-portal-app"></a>Obter o aplicativo Portal da Empresa offline
1. Pesquise e selecione o aplicativo **Portal da Empresa**.
2. Defina o **Tipo de licença** como **Offline**.
3. Selecione **Obter o aplicativo** para adquirir e adicionar o aplicativo do Portal da Empresa offline ao seu inventário.

## <a name="assign-the-company-portal-app"></a>Atribuir o aplicativo do Portal da Empresa
1. Entre no  [Centro de administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) com sua conta do administrador. 
2. Selecione a guia **Aplicativos** no painel direito. 
3. Em **Por plataforma**, selecione **Windows**. 
4. Selecione  **Portal da Empresa (Offline)** .   
5. Você precisa aguardar a conclusão da agenda de sincronização ou então fazer uma sincronização manual do Centro de administração do Microsoft Endpoint Manager.
6. Atribua o aplicativo do Portal da Empresa como um aplicativo necessário para os grupos de dispositivos do Autopilot selecionados.

## <a name="next-steps"></a>Próximas etapas

- Para saber mais sobre como atribuir aplicativos, confira [Atribuir aplicativos a grupos](apps-deploy.md).

