---
title: Registrar seu dispositivo Android no Intune | Microsoft Docs
description: Descreve como registrar um dispositivo Android no Intune
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0ed3a002-7533-4001-ae24-e10b64b66620
ms.reviewer: arnab
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 385565bd1ce05c9402a52cdd6eeb93f58caaf72a
ms.openlocfilehash: 02bd3d2f62bd8b8e3f590de4bc8f4e6099f4917d


---


# <a name="enroll-your-android-device-in-intune"></a>Registrar seu dispositivo Android no Intune

Se sua empresa ou escola usa o Microsoft Intune, você pode registrar seu dispositivo Android para obter acesso a email, arquivos e outros recursos corporativos. Quando você registra os dispositivos, o departamento de TI pode gerenciar recursos corporativos ou de estudante e mantê-los seguros, dando-lhe a liberdade de usar seu dispositivo preferido para realizar o trabalho. Para saber mais sobre registro, consulte [What happens when I install and Company Portal app and enroll my device? (O que acontece quando instalo o aplicativo Portal da Empresa e registro meu dispositivo?)](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-android.md).

Essas instruções de registro são para dispositivos Samsung KNOX Android e dispositivos Android “nativos” (que não são Samsung Knox). Para verificar se você tem um dispositivo Samsung KNOX, vá para **Configurações** &gt; **Sobre o dispositivo**. Se você não vê a “versão do KNOX” listada, tem um dispositivo Android nativo.

Antes ou após o registro, você poderá ser solicitado a escolher uma categoria que melhor descreva como você usa o dispositivo. O administrador de TI usa essa categoria para ajudar a verificar os aplicativos aos quais você tem acesso.

Se houver erro ao tentar registrar o dispositivo no Intune, você pode [enviar erros de registro ao administrador de TI](send-enrollment-errors-to-your-it-administrator-android.md).

**Para registrar seu dispositivo Android:**

1.  Instale o aplicativo gratuito Portal da Empresa do Intune do [Google Play](http://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal).

2.  Abra o aplicativo Portal da Empresa do Microsoft Intune.

3.  Na tela de **Boas-vindas** do Portal da Empresa, toque em **Entrar** e entre com sua conta corporativa ou de estudante.

    ![android-company-portal-sign-in](./media/and-enroll-0-welcome-screen.png)   

4.  Se o seu administrador de TI tiver configurado termos e condições da empresa, toque em **ACEITAR** para aceitar os termos.

    ![android-company-portal-sign-in](./media/and-enroll-3-accept-terms.png)

5.  Conecte-se no aplicativo do Portal da Empresa usando sua conta e senha corporativa ou de estudante e, em seguida, toque em **Entrar**.

    ![android-company-portal-sign-in](./media/and-enroll-2-cp-sign-in.png)

6.  Na tela **Configuração de Acesso da Empresa**, toque em **Iniciar**.

    ![Tela Configuração de acesso da empresa](./media/and-enroll-4a-comp-access-setup.png)

7.  Na tela **Por que registrar seu dispositivo?** leia sobre o que você pode fazer ao registrar o dispositivo e, em seguida, toque em **CONTINUAR**.

    ![Tela Por que registrar seu dispositivo](./media/and-enroll-4b-why-enroll.png)

8.  Examine uma lista do que o administrador de TI pode e não pode ver em seu dispositivo e toque em **CONTINUAR**.

    ![Configurações de privacidade](./media/and-enroll-4c-we-care-privacy.png)

9.  Na tela **O que vem em seguida**, leia sobre o que acontece durante o registro e, em seguida, toque em **REGISTRAR**.

    ![Tela O que vem em seguida](./media/and-enroll-4d-what-comes-next.png)

10.  Se você estiver usando o Android 6.0 ou posterior, execute esta etapa. Caso contrário, vá para a próxima etapa.

    Se o administrador de TI tiver configurado algumas políticas, você poderá ver as seguintes mensagens:
    -   **Permitir que o Portal da Empresa faça e gerencie chamadas telefônicas?**

        ![android-company-portal-sign-in](./media/and-enroll-3a-allow-phone-access.png)

    Se você vir essa mensagem, toque em **PERMITIR**. É seguro tocar em PERMITIR, porque a **Microsoft nunca faz nem gerencia suas chamadas telefônicas**! O Google controla o texto da mensagem, e a Microsoft não pode alterá-lo. Ao permitir o acesso, você está apenas autorizando o dispositivo a enviar o número IMEI (Identidade de Equipamentos Móveis Internacional) para o Intune. O IMEI é um número, como um número de série, que identifica exclusivamente um dispositivo móvel.

    Se você negar acesso, a mensagem será exibida novamente na próxima vez que você entrar no Portal da Empresa, mas você poderá desligar as mensagens futuras tocando na caixa **Nunca perguntar novamente**. Se você decidir posteriormente permitir o acesso, acesse **Configurações** &gt; **Aplicativos** &gt; **Portal da Empresa** &gt; **Permissões** &gt; **Telefone** e ative a permissão.

    -   **Permitir que o Portal da Empresa acesse seus contatos?**

        ![android-company-portal-sign-in](./media/and-enroll-3b-allow-contacts-access.png)

    Se você vir essa mensagem, toque em **PERMITIR**. É seguro tocar em PERMITIR, porque a **Microsoft nunca acessa seus contatos!** O Google controla o texto da mensagem, e a Microsoft não pode alterá-lo. Ao permitir acesso, ele apenas autorizará o aplicativo do Portal da Empresa a criar, usar e gerenciar sua conta corporativa.

    Se você negar acesso, a mensagem será exibida novamente na próxima vez que você entrar no Portal da Empresa, mas você poderá desligar as mensagens futuras tocando na caixa **Nunca perguntar novamente**. Se você decidir posteriormente permitir o acesso, acesse **Configurações** &gt; **Aplicativos** &gt; **Portal da Empresa** &gt; **Permissões** &gt; **Telefone** e ative a permissão.

11.  Na tela **Ativar administrador do dispositivo**, clique em **Ativar**.

    ![Tela Ativar administrador do dispositivo](./media/and-enroll-5-activate.png)

12.  Siga os prompts para inserir um PIN ou senha. Se já tiver configurado um PIN ou senha neste dispositivo, você não verá esta tela ou será solicitado a inserir um novo PIN ou senha.

    ![Inserir o PIN ou a senha](./media/and-enroll-6-PIN-native.png)

13.  Se você estiver usando um dispositivo Samsung Knox, toque em **Confirmar** e você verá uma mensagem informando que seu dispositivo está sendo registrado. Se você estiver usando um dispositivo Android nativo, basta observar a tela abaixo mostrando que o dispositivo está sendo registrado.

    ![Política de privacidade do Samsung KNOX](./media/and-enroll-7-knox-privacy-policy.png)

    Esta tela mostra que seu dispositivo está sendo registrado.

    ![Tela de registro do dispositivo](./media/and-enroll-8-device-enrolling.png)

14. Quando a tela **Configuração de Acesso da Empresa** for exibida, toque em **CONTINUAR**. Se uma mensagem indicar que o dispositivo está fora de conformidade, siga as instruções para corrigir o problema e, em seguida, toque em **CONTINUAR**.

    ![Tela Configuração de acesso da empresa](./media/and-enroll-9-comp-access-setup.png)  

11. Na tela **Configuração de Acesso da Empresa completa**, toque em **CONCLUÍDO**. Agora, seu dispositivo está registrado.

    ![Tela Configuração de acesso da empresa concluída](./media/and-enroll-10-comp-access-setup-complete.png)

Antes de tentar instalar aplicativos corporativos, acesse **Configurações** &gt; **Segurança** e ative **Fontes desconhecidas**. Se não ativar essa opção antes de tentar instalar os aplicativos, você verá a mensagem: “Instalação bloqueada”. Por motivos de segurança, seu dispositivo está definido para bloquear as instalações de aplicativos obtidos de fontes desconhecidas." Você pode tocar em **Configurações** na caixa de diálogo de erro para ir para a opção **Fontes desconhecidas**.

Ainda precisa de ajuda? Entre em contato com o administrador de TI (consulte o [site do Portal da Empresa](http://portal.manage.microsoft.com) para obter as informações de contato) ou escreva para a equipe de Android da Microsoft em wintunedroidfbk@microsoft.com.



<!--HONumber=Dec16_HO3-->


