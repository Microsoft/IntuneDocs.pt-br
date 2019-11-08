---
title: Registrar um dispositivo Android com o Portal da Empresa do Intune | Microsoft Docs
description: Descreve como registrar um dispositivo Android com o Portal da Empresa do Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: 0ed3a002-7533-4001-ae24-e10b64b66620
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5baf0e9079cc148101a68e5cd2d3a4ed500f567f
ms.sourcegitcommit: 60f0ff6d2efbae0f2ce14b9a9f3f9267309e209b
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73414805"
---
# <a name="enroll-your-device-with-company-portal"></a>Registrar seu dispositivo com o Portal da Empresa  
Registre seu dispositivo Android pessoal ou corporativo para obter acesso seguro aos dados, aplicativos e email da empresa. O Portal da Empresa é compatível com dispositivos Android, incluindo o Samsung Knox, que executam o Android 4.4 e posteriores.  
</br>
> [!VIDEO https://www.youtube.com/embed/k0Q_sGLSx6o?rel=0]

> [!NOTE]
> O Samsung Knox é um tipo de segurança que certos dispositivos Samsung usam para proteção adicional além da fornecida pelo Android de maneira nativa. Para verificar se você tem um dispositivo Samsung Knox, acesse **Configurações** > **Sobre o dispositivo**. Caso você não veja a **versão do Knox** listada, é porque tem um dispositivo Android nativo.

## <a name="enroll-device"></a>Registrar o dispositivo  
Certifique-se de [Instalar o aplicativo gratuito do Portal da Empresa do Intune do Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal). 

Durante o registro, pode ser solicitado que você escolha uma categoria que melhor descreva como você usa o dispositivo. O suporte de sua empresa usa sua resposta para verificar os aplicativos aos quais tem acesso.  

1. Abra o aplicativo Portal da Empresa e entre com sua conta corporativa ou de estudante.  

2. Se você for solicitado a aceitar os termos e condições da sua organização, toque em **ACEITAR TUDO**.  

   ![Imagem de exemplo do Portal da Empresa, tela de termos, realçando o botão "aceitar tudo".](./media/accept-terms-1911.png)  


3. Examine o que a sua organização pode e não consegue ver. Toque em **CONTINUAR**.


    ![Exemplo de imagem de Portal da Empresa, nós nos preocupamos com sua tela de privacidade, destacando o botão continuar.](./media/android-privacy-screen-1911.png)  
4. Examine o que esperar nas próximas etapas. Em seguida, toque em **Avançar**.  

    ![Exemplo de imagem de Portal da Empresa, a próxima tela, destacando o botão Avançar.](./media/android-whats-next-1911.png)  


5. Dependendo da sua versão do Android, você pode ser solicitado a permitir o acesso a determinadas partes do seu dispositivo. Esses prompts são exigidos pelo Google e não são controlados pela Microsoft.  

    Toque em **permitir** para as seguintes permissões:  
    * **Permitir que o portal da empresa faça e gerencie chamadas telefônicas**: essa permissão permite que seu dispositivo Compartilhe seu número de identidade internacional de equipamentos de estação móvel (IMEI) com o Intune, o provedor de gerenciamento de dispositivos da sua organização. É seguro permitir essa permissão. A Microsoft nunca fará ou gerenciará chamadas telefônicas.  
    * **Permitir que Portal da empresa acesse seus contatos**: essa permissão permite que o aplicativo portal da empresa crie, use e gerencie sua conta corporativa.  É seguro permitir essa permissão. A Microsoft nunca acessará seus contatos. 

    Se você negar a permissão, será solicitado novamente na próxima vez que entrar no Portal da Empresa. Para desligar essas mensagens, selecione **Nunca perguntar novamente**. Para gerenciar permissões de aplicativo, vá para o aplicativo Configurações > **aplicativos** > **Portal da Empresa** > **permissões** > **telefone**.  

6. Ative o aplicativo de administrador do dispositivo. 

    Portal da Empresa precisa de permissões de administrador de dispositivo para gerenciar seu dispositivo com segurança. Ativar o aplicativo permite que sua organização identifique possíveis problemas de segurança, como tentativas repetidas com falha para desbloquear seu dispositivo e responder adequadamente.  

    ![Imagem de exemplo da tela ativar administrador do dispositivo, realçando o botão Ativar.](./media/activate-device-administrator-1911.png)  

> [!NOTE]
> A Microsoft não controla as mensagens nesta tela. Entendemos que sua frase pode parecer um pouco drástica. Portal da Empresa não pode especificar quais restrições e acesso são relevantes para sua organização. Se você tiver dúvidas sobre como sua organização usa o aplicativo, entre em contato com o seu profissional de suporte de ti. Acesse o [site do Portal da Empresa](https://go.microsoft.com/fwlink/?linkid=2010980) para localizar as informações de contato da sua organização.  


7. Seu dispositivo começa a se registrar. Se você estiver usando um dispositivo Samsung Knox, será solicitado a revisar e confirmar a política de privacidade do agente ELM primeiro.   

    ![Imagem de exemplo da tela de política de privacidade do Samsung Knox que aparece durante o registro.](./media/and-enroll-7-knox-privacy-policy.png)  

8. Na tela **configuração de acesso da empresa** , verifique se o dispositivo está registrado. Toque em **CONTINUAR**.  

    ![Exemplo de imagem de Portal da Empresa, tela de configuração de acesso da empresa, mostrando que o dispositivo gerenciado foi concluído.](./media/update-settings-1911.png)  

9. Sua organização pode exigir que você atualize as configurações do dispositivo. Toque em **resolver** para ajustar uma configuração. Quando você terminar de atualizar as configurações, toque em **continuar**.  

   ![Exemplo de imagem de Portal da Empresa, atualizar configurações do dispositivo, realçar os botões resolver e continuar.](./media/resolve-settings-1911.png)  

10. Quando a instalação estiver concluída, toque em **concluído**.    

    ![Exemplo de imagem de Portal da Empresa, tela de configuração de acesso da empresa, mostrando a configuração concluída e realçando o botão concluído.](./media/android-enrollment-done-1911.png) 

## <a name="next-steps"></a>Próximas etapas  

Antes de tentar instalar um aplicativo escolar ou de trabalho, vá para **configurações** > **segurança**e ative **fontes desconhecidas**. Se não ativar essa opção, você verá a seguinte mensagem ao tentar instalar os aplicativos: "Instalação bloqueada. Por motivos de segurança, seu dispositivo está definido para bloquear as instalações de aplicativos obtidos de fontes desconhecidas." Você pode tocar em **configurações** na mensagem para ir diretamente para **fontes desconhecidas**.  

> [!Note]
> Se sua organização estiver usando software de gerenciamento de despesas de telecomunicações, você terá algumas etapas adicionais para concluir antes de o dispositivo estar totalmente inscrito. Saiba mais [aqui](enroll-your-device-with-telecom-expense-management-android.md).

Se houver erro ao tentar registrar o dispositivo no Intune, você poderá [enviar um email ao suporte de sua empresa](send-logs-to-your-it-admin-by-email-android.md).  

Ainda precisa de ajuda? Contate o suporte da sua empresa. Para obter as informações de contato, consulte o [site do Portal da Empresa](https://go.microsoft.com/fwlink/?linkid=2010980).  