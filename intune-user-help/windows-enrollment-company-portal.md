---
title: Registro de dispositivo do Windows no Portal de empresa do Intune | Microsoft Docs
description: Comece a registrar um dispositivo Windows no Portal da empresa
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/12/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 36250832-c6fd-4e8d-b681-de735023ebc3
searchScope:
- User help
ROBOTS: ''
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: a637b6eed162243d2be81ac08fbcc055e1fd5816
ms.sourcegitcommit: fdc6261f4ed695986e06d18353c10660a4735362
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2019
ms.locfileid: "58068839"
---
# <a name="windows-device-enrollment-in-intune-company-portal"></a>Registro de dispositivo do Windows no Portal de empresa do Intune  

Registre seu dispositivo Windows no aplicativo do Portal da empresa Intune para obter acesso seguro ao trabalho e aplicativos de escola, emails e arquivos. Se sua organização requer ou recomenda determinados aplicativos, como o Office ou OneDrive, você vai recebê-los durante o registro, ou elas estarão disponíveis no Portal da empresa após o registro.  

Você pode registrar dispositivos Windows 10 por meio do site Portal da empresa *ou* aplicativo. Se você estiver registrando um dispositivo com uma versão anterior do Windows, você deve registrar o dispositivo por meio do site Portal da empresa.  

## <a name="install-company-portal-app"></a>Aplicativo Portal da empresa de instalação  
Talvez você já tenha o aplicativo de Portal da empresa instalado no seu dispositivo. Procure o aplicativo no seu __todos os aplicativos__ lista.  Se você não vir o Portal da Empresa na sua lista de aplicativos, siga essas etapas para instalá-lo.  

1. Abra **Microsoft Store** em seu dispositivo.

2. No **pesquisa** , digite **Portal da empresa**.

3. Na lista de resultados, selecione **Portal da Empresa** > **Instalar**.

4. Selecione **Instalar** ou **Gratuito**. Não há nenhuma diferença entre essas duas opções; as palavras serão exibidas com base em como a sua organização se configurar o aplicativo.  

## <a name="find-windows-10-version-number"></a>Localizar o número de versão do Windows 10  
Etapas de registro são diferentes para diferentes versões de dispositivos Windows 10. As etapas a seguir descrevem como localizar o número de versão no Windows 10 desktops e dispositivos móveis. Depois que você sabe sua versão, continue para as etapas de registro recomendados.  

### <a name="windows-10-desktop-devices"></a>Dispositivos com Windows 10 Desktop  

1. Vá até **Iniciar**.

2. Na barra de pesquisa, digite a frase "sobre seu PC." Selecione __sobre seu PC__ dos resultados.  


   ![configurações de pesquisa para "sobre seu pc"](media/searching_for_about_your_pc.png)  

3. Role para baixo até **especificações do Windows** para localizar o **versão** do Windows 10 que está instalado em seu computador.  


   ![Windows 10 Desktop – Sobre seu PC](media/settings_about_pc.png)  

4. Se sua versão for  

    *  __1607 ou posterior__: registrar seu dispositivo por meio das [ **configurações** > **conta** > **acessar trabalho ou escola**rota](enroll-windows-10-device.md#enroll-windows-10-version-1607-and-later-device).   
    * __1511 ou anterior__: registrar seu dispositivo por meio das [ **configurações** > **conta** > **suas contas** rota](enroll-windows-10-device.md#enroll-windows-10-version-1511-and-earlier-device).  

### <a name="windows-10-mobile-devices"></a>Dispositivos com Windows 10 Mobile       

1.  Vá para __todos os aplicativos__ e selecione o __configurações__ aplicativo.  
2.  Selecione __Sistema__ > __Sobre__.      
3.  Sob __informações do dispositivo__, localize o __versão__.  
4. Se sua versão for  

    *  __1607 ou posterior__: registrar seu dispositivo usando o [ **configurações** > **acessar trabalho ou escola** rota](enroll-windows-10-device.md#enroll-windows-10-version-1607-and-later-device).   
    * __1511 ou anterior__: registrar seu dispositivo usando o [ **configurações** > **contas** rota](enroll-windows-10-device.md#enroll-windows-10-version-1511-and-earlier-device).  

## <a name="enroll-non-windows-10-devices"></a>Registrar dispositivos não Windows 10  
Use os artigos a seguir para registrar outros dispositivos com suporte do Windows por meio do site Portal da empresa:   
* [Dispositivo Windows 8.1 ou Windows RT 8.1](enroll-your-W81-or-rt81-windows.md)  
* [Dispositivo Windows Phone 8.1](enroll-your-wp81-windows.md)    

## <a name="next-steps"></a>Próximas etapas  
Agora que você sabe que os dispositivos com suporte e seu número de versão do Windows 10, vá para o artigo de registro recomendados.  
 
Para obter mais informações sobre o gerenciamento de dispositivo, o Portal da empresa e como ambos são usadas nas escolas e no trabalho, consulte os seguintes artigos:  
* [Usar dispositivos gerenciados para acessar recursos corporativos ou de estudante](use-managed-devices-to-get-work-done.md)  
* [O que acontece quando você registra seu dispositivo no Intune](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows.md)  
* [Quais informações minha organização poderá ver quando eu registrar meu dispositivo?](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md)  

Precisa de ajuda? Contate o suporte da sua empresa. [Vá para o site de Portal da empresa](https://go.microsoft.com/fwlink/?linkid=2010980) para localizar a sua organização IT informações de contato.  
