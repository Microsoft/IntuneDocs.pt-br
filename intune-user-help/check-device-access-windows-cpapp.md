---
title: Verificar o acesso do dispositivo | Microsoft Docs
description: Verifique o acesso do dispositivo para descobrir se ele atende aos requisitos e pode acessar recursos corporativos ou de estudante.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/05/2018
ms.topic: article
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 49075fd750ade6aaa412d551f4177822b52ce7f2
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72490095"
---
# <a name="check-access-from-company-portal-app-for-windows"></a>Verificar o acesso do aplicativo Portal da Empresa para Windows

Verifique se seu dispositivo tem acesso a recursos corporativos ou de estudante. 

As organizações impõem requisitos &ndash; como limites de criptografia e de senha &ndash; para garantir que apenas dispositivos seguros e confiáveis acessem seus dados. Os dispositivos gerenciados devem atender e manter esses requisitos para acessar os recursos da organização.

A ação **Verificar acesso** avalia as configurações do seu dispositivo e seu status de acesso. A página **Detalhes do dispositivo** lista as configurações que você precisa ajustar para recuperar o acesso. 

Conclua as etapas neste artigo para verificar o acesso do aplicativo Portal da Empresa para Windows.  

## <a name="check-access-from-device-details-page"></a>Verificar o acesso na página Detalhes do dispositivo  
1. Abra o aplicativo Portal da Empresa para Windows e acesse **Meus dispositivos**.  

    ![Exemplo de captura de tela do aplicativo Portal da Empresa para Windows, Página inicial, realçando a seção Meus dispositivos.](./media/1809_CheckAccess_Context_Select_Device.png)  
2. Selecione um dispositivo.  
3. Na página **Detalhes do dispositivo**, selecione **Verificar acesso**. O aplicativo sincroniza seu dispositivo aos requisitos atuais da sua organização e verifica para garantir se seu dispositivo corresponde a eles. Essa verificação pode levar alguns minutos.  

    ![Exemplo de captura de tela do aplicativo Portal da Empresa para Windows, página Detalhes do dispositivo, realçando a seção Verificar acesso.](./media/1809_CheckAccess_Checking_Status.png) 

4. Examine a atualização do status. Ela mostrará a que seu dispositivo **Pode acessar os recursos da sua organização** ou **Não pode acessar os recursos da sua organização**.  

   ![Exemplo de captura de tela do aplicativo Portal da Empresa para Windows, página Detalhes do dispositivo, realçando a seção Status.](./media/1809_CheckAccess_Device_details_status1.png)  
   
5. Se o dispositivo não puder acessar os recursos, vá para o alerta na parte superior da página. Clique em **Mais** para expandir seus detalhes. Clique em **Menos** para recolhê-los.  

    ![Exemplo de captura de tela do aplicativo Portal da Empresa para Windows, página Detalhes do dispositivo, realçando o alerta na parte superior da página.](./media/1809_CheckAccess_Device_details_alert1.png)  

6. Quando aplicável, a mensagem mostra outros links de ajuda e ações de correção. Selecione uma ou mais dessas opções para começar a solução de problemas imediatamente. As ações resolver, sincronizar e contatar &ndash;descritas abaixo&ndash; ficam visíveis apenas ao usar o Portal da Empresa no dispositivo afetado.  

     * **Como resolver isso** abre um artigo de ajuda relevante se disponível.  
     * **Resolver** redireciona você para a configuração em seu dispositivo.  
     * **Sincronizar** avalia seu dispositivo para garantir que ele corresponda aos requisitos de sua organização.  
     * **Contatar TI** redireciona você para as informações de contato da sua equipe de TI.   
 
6. Depois de atualizar as configurações, clique em **Verificar acesso** para confirmar o status do seu dispositivo.  

    ![Exemplo de captura de tela do aplicativo Portal da Empresa para Windows, página Detalhes do dispositivo, realçando a seção Status.](./media/1809_CheckAccess_Device_details_status1.png)  

## <a name="check-access-from-device-context-menu"></a>Verificar acesso no menu de contexto do dispositivo  
1. Abra o aplicativo Portal da Empresa para Windows e acesse **Meus dispositivos**.  

    ![Exemplo de captura de tela do aplicativo Portal da Empresa para Windows, Página inicial, realçando a seção Meus dispositivos.](./media/1809_CheckAccess_Context_Select_Device.png)  

2. Clique com o botão direito do mouse ou pressione e segure um dispositivo para abrir seu [menu de contexto](https://docs.microsoft.com//windows/uwp/design/controls-and-patterns/menus).  

    ![Exemplo de captura de tela do aplicativo Portal da Empresa para Windows, Página inicial. O menu de contexto do dispositivo está visível na seção **Meus dispositivos** da página e mostra as ações "Renomear", "Remover" e "Verificar acesso".](./media/1809_DeviceContextMenu_Windows_CP.png)  
3. Selecione **Verificar acesso**. O aplicativo sincroniza seu dispositivo aos requisitos atuais da sua organização e verifica para garantir se seu dispositivo é correspondente. Essa verificação pode levar alguns minutos.  
 
4. Uma mensagem é exibida embaixo do dispositivo para informar que ele **Pode acessar os recursos corporativos** ou **Não pode acessar os recursos corporativos**. 

    ![Exemplo de captura de tela do aplicativo Portal da Empresa para Windows, página Detalhes do dispositivo, realçando a seção Status.](./media/1809_CheckAccess_Context_Menu_Alert2.png) 

5. Se o dispositivo não puder acessar os recursos, selecione o dispositivo.  
6. Na página **Detalhes do dispositivo**, acesse o alerta na parte superior da página. Clique em **Mais** para expandir seus detalhes. Clique em **Menos** para recolhê-los.  

    ![Exemplo de captura de tela do aplicativo Portal da Empresa para Windows, página Detalhes do dispositivo, realçando o alerta na parte superior da página.](./media/1809_CheckAccess_Device_details_alert1.png)  

6. Quando aplicável, a mensagem mostra outros links de ajuda e ações de correção. Selecione uma ou mais dessas opções para começar a solução de problemas imediatamente. As ações resolver, sincronizar e contatar &ndash;descritas abaixo&ndash; ficam visíveis apenas ao usar o Portal da Empresa no dispositivo afetado.  

     * **Como resolver isso** abre um artigo de ajuda relevante se disponível.  
     * **Resolver** redireciona você para a configuração em seu dispositivo.  
     * **Sincronizar** avalia seu dispositivo para garantir que ele corresponda aos requisitos de sua organização.  
     * **Contatar TI** redireciona você para as informações de contato da sua equipe de TI.    

7. Depois de atualizar as configurações, clique em **Verificar acesso** na parte inferior da página.  

    ![Exemplo de captura de tela do aplicativo Portal da Empresa para Windows, página Detalhes do dispositivo, realçando o botão Verificar acesso.](./media/1809_CheckAccess_Device_details_button.png) 


Precisa de mais ajuda? Localize as informações de contato do suporte de sua empresa no [site do Portal da Empresa](https://go.microsoft.com/fwlink/?linkid=2010980).
