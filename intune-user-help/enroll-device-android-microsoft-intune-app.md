---
title: Registrar dispositivos corporativos com aplicativos do Microsoft Intune | Microsoft Docs
description: Descreve como registrar um dispositivo Android corporativo no Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/19/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 0ed3a002-7533-4001-ae24-e10b64b66620
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7e68e404a91927192f1006626d1b865acd5eb589
ms.sourcegitcommit: d258bcf6716c8a2589d3f8dada819905ee80f233
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66197045"
---
# <a name="enroll-your-corporate-device-with-the-microsoft-intune-app"></a>Registrar dispositivos corporativos com aplicativos do Microsoft Intune

Registre seu dispositivo Android corporativo para obter acesso seguro ao email da empresa, aplicativos e outros dados que sua organização disponibiliza. O aplicativo do Microsoft Intune é compatível com dispositivos corporativos que executam o Android 6.0 e posteriores. Ele será automaticamente instalado nos dispositivos novos e redefinido para as configurações de fábrica durante o registro. 

Há quatro maneiras de registrar. Sua organização deve permitir que você saiba qual opção usar.
 
* NFC (Comunicação a curta distância)  
* Token  
* Código QR   
* Registro sem toque do Google  

## <a name="enroll-device"></a>Registrar o dispositivo 
Conclua estas etapas para configurar e registrar seu dispositivo.  

> [!NOTE]
> O fabricante do dispositivo ou a versão Android pode exigir que você conclua as etapas adicionais que não são abordadas neste procedimento. As cores e o texto que você vê nas capturas de tela também podem aparecer diferentes em seu dispositivo.  

1. Ligue o dispositivo novo ou redefinido para as configurações de fábrica.  
2. Na tela **Boas-vindas**, selecione seu idioma.   Se você tiver sido instruído a registrar com um código QR ou NFC, siga a etapa abaixo que corresponde ao método.  
     * NFC: toque em seu dispositivo compatível com NFC em relação a um dispositivo do programador para se conectar à rede da sua organização. Siga os prompts na tela. Quando você chegar à tela de Termos de Serviço do Chrome, vá para a etapa 5.  

      * Código QR: conclua as etapas em [Registro de código QR](#qr-code-enrollment).  

      Se você tiver sido instruído a usar outro método, vá para a etapa 3.    

1. Conecte-se ao Wi-Fi e toque em **AVANÇAR**. Siga a etapa que corresponde ao seu método de registro. 

    * Token: quando você acessar a tela de conexão do Google, conclua as etapas em [Registro de Token](#token-enrollment).    
    * Registro sem toque do Google: depois de se conectar ao Wi-Fi, seu dispositivo será reconhecido pela sua organização. Vá para a etapa 4 e siga os prompts na tela até que a configuração seja concluída.    
 
       ![Imagem de exemplo da tela dos termos do Google que você verá se estiver usando o registro sem toque do Google, realçando o botão Aceitar e Continuar.](./media/google-zero-touch-intune-app-01.png)   
   
4. Examine os termos do Google. Em seguida, toque em **ACEITAR E CONTINUAR**.  

      ![Imagem de exemplo da tela dos termos do Google, realçando o botão Aceitar e Continuar.](./media/fully-managed-intune-app-04.png)   

6. Examine os Termos de Serviço do Chrome. Em seguida, toque em **ACEITAR E CONTINUAR**.  

   ![Imagem de exemplo da tela dos Termos de Serviço do Chrome, realçando o botão Aceitar e Continuar.](./media/fully-managed-intune-app-06.png)   

7. Em telas de entrada, entre com sua conta corporativa ou de estudante.   

    a. Insira seu email e toque em **Avançar**.      
    b. Insira sua senha e toque em **Entrar**.  

8. Dependendo dos requisitos da sua organização, talvez seja solicitado que você atualize as configurações, como bloqueio de tela ou criptografia. Se você vir esses prompts, toque em **CONFIGURAR** e siga as instruções na tela.  

   ![Imagem de exemplo da tela Configurar seu telefone de trabalho, realçando o botão Configurar.](./media/fully-managed-intune-app-10.png)   

9. Para instalar aplicativos de trabalho em seu dispositivo, toque em **INSTALAR**. Após a instalação ser concluída, toque em **AVANÇAR**.  

   ![Imagem de exemplo da tela Configurar seu telefone de trabalho, realçando o botão Instalar.](./media/fully-managed-intune-app-11.png)   

10. Quando você receber a mensagem de que o dispositivo está pronto, toque **CONCLUIR**. 

11. Acesse seus aplicativos e abra o aplicativo do Microsoft Intune. Selecione **ENTRAR**. 

12. Na tela **Configurar acesso**, você verá uma lista de tarefas pendentes. Toque em **CONTINUAR**.  

       ![Imagem de exemplo do aplicativo do Microsoft Intune, tela Configurar acesso, mostrando as tarefas pendentes.](./media/fully-managed-intune-app-14.png)   

13. Quando o registro do dispositivo for concluído, toque **CONTINUAR**. O Microsoft Intune pode solicitar que você atualize as configurações de dispositivos adicionais.   

       ![Imagem de exemplo do aplicativo do Microsoft Intune, tela Atualizar configurações do dispositivo.](./media/fully-managed-intune-app-15-2.png)   

14. A instalação estará concluída quando todos os itens na lista mostrarem um círculo verde. Agora você pode acessar recursos da empresa.  

       ![Imagem de exemplo do aplicativo do Microsoft Intune, tela Configurar acesso, mostrando as tarefas concluídas.](./media/fully-managed-intune-app-16.png)   


## <a name="qr-code-enrollment"></a>Registro de código QR  
Nesta seção, você leia seu código QR fornecido pela empresa.  Quando você terminar, será redirecionado para as etapas de registro do dispositivo.     
  
1. Na tela **Boas-vindas**, toque na tela de cinco vezes para iniciar a configuração do código QR.  

   ![Imagem da tela Boas-vindas da configuração do dispositivo, realçando as instruções para tocar a tela.](./media/qr-code-intune-app-01.png)  

2. Siga as instruções na tela para se conectar ao Wi-Fi.  
3. Se seu dispositivo não tiver um leitor de código QR, as telas de configuração mostrarão o progresso quando um leitor for instalado. Aguarde a conclusão da instalação.  
4. Quando solicitado, leia o código QR do perfil de registro que sua organização forneceu para você.  
5. Volte para [Registrar dispositivo](#enroll-device), etapa 4 para continuar a configuração.  

## <a name="token-enrollment"></a>Registro de token  
Nesta seção, você digitará o token fornecido da empresa. Quando você terminar, será redirecionado para as etapas de registro do dispositivo.  

1. Na tela de credenciais do Google, na caixa **Email ou telefone**, digite **afw#setup**. Toque em **Próximo**. 

   ![Imagem de exemplo da tela de credenciais do Google, mostrando que "afw#setup" foi digitado no campo.](./media/token-intune-app-01.png)   

2. Escolha **Instalar** para o aplicativo **Política do Dispositivo Android**. Prossiga com a instalação. Dependendo do seu dispositivo, talvez você precise examinar e aceitar termos adicionais.    

3. Na tela **Registrar este dispositivo**, selecione **Avançar**.  

   ![Imagem de exemplo da tela Registrar este dispositivo. Mostra a ilustração de um código QR, realça o botão Avançar.](./media/token-intune-app-02.png)  

4. Selecione **Inserir código**.

   ![Captura de tela de exemplo de um leitor de código QR ativo. Realça o botão Inserir código.](./media/token-intune-app-03.png)  

5. Na tela **Ler ou inserir código**, digite o código que sua organização forneceu.  Clique em **Avançar**.  

   ![Imagem de exemplo da tela Ler ou inserir código, realçando o botão Avançar.](./media/token-intune-app-04.png)  

6. Volte para [Registrar dispositivo](#enroll-device), etapa 4 para continuar a configuração.  



## <a name="next-steps"></a>Próximas etapas   
Ainda precisa de ajuda? Entre em contato com o suporte de sua empresa (consulte o [site do Portal da Empresa](https://go.microsoft.com/fwlink/?linkid=2010980) para obter as informações de contato) ou escreva para a <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with enrolling my Android device&body=Describe the issue you're experiencing here.">equipe de Android da Microsoft</a>.  
