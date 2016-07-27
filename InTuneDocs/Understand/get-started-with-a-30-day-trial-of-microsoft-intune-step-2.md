---
title: "Adicionar usuários à sua avaliação de 30 dias do Intune | Microsoft Intune"
description: "Como adicionar usuários, individualmente ou em massa, ao se inscrever para uma avaliação gratuita de 30 dias do Intune"
keywords: 
author: Staciebarker
manager: arob98
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9e40999b-46f7-447b-8974-72af82bec7ef
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 376e6c1ae229187ab8ec73390f091f1d534365dd
ms.openlocfilehash: 5a5ebe474580b98a3696bbd970c889837283b6f0


---

# Adicionar usuários à sua avaliação de 30 dias do Microsoft Intune
Agora que você configurou sua conta, poderá usar o assistente **Novos Usuários** para adicionar contas de usuário individuais ao Intune ou o assistente **Adicionar usuários em massa** para adicionar usuários em massa (consulte as instruções nesta seção).  Antes de começar, é importante entender como o Intune lida com contas de administrador.

Um administrador de locatários usa o Office 365 para adicionar usuários ao **Grupo Usuários** do Microsoft Intune. Adicionar usuários ao  **Grupo de Usuários** atribui licenças de assinatura do Intune aos usuários e também é a forma como você torna os usuários sejam exibidos no console de administração do Microsoft Intune.

Contas de administrador do Intune não são criadas no Centro de administração do Office 365, como as contas de usuário comuns. Em vez disso, você atribui o acesso somente leitura ou os direitos administrativos de acesso completo a usuários ao usar o console de administração no espaço de trabalho de **Administração** em **Gerenciamento de Administração**. Os administradores de serviço que recebem acesso somente leitura não podem alterar as configurações do Intune, mas podem exibir dados e executar relatórios. Os administradores de serviço com acesso completo têm todos os direitos administrativos disponíveis.

Você pode exibir informações do administrador de locatários ao usar o console de administração do Intune, mas não pode criar administradores de locatários neste local. Por padrão, o proprietário da assinatura torna-se um administrador de locatários para seu serviço do Microsoft Intune e tem acesso completo ao centro de administração do Office 365 e ao console de administração do Intune. Recomendamos que você crie pelo menos uma conta de administrador de locatários adicional ao usar o centro de administração do Office 365 para ajudar a delegar tarefas e garantir que sua conta de administrador de serviços do Intune não seja bloqueada se você esquecer sua senha.

## Para adicionar manualmente as contas de usuário individuais
Use as etapas a seguir para criar contas de usuário adicionais no seu locatário de avaliação. Lembre-se, cada conta de usuário que você adiciona conta como uma das 100 licenças que você obtém como parte da avaliação gratuita do Intune.

1.  No [Centro de administração do Office 365](http://go.microsoft.com/fwlink/?LinkID=787455), escolha **Adicionar Usuários** &gt; **Novo**&gt; **Usuário** para iniciar o assistente **Novos usuários**.

2.  Na página **Detalhes** , preencha os campos obrigatórios.

3.  Na página **Configurações** , defina o **local** do usuário.

4.  Na página **Grupo**, clique em **Avançar** para aceitar o padrão e atribuir uma licença do Intune à conta do usuário.

5.  Na página **Email** , especifique até cinco endereços de email que receberão a notificação do nome de usuário e senha temporária para a conta. Separe vários endereços de email usando ponto e vírgula (;). Quando estiver pronto, escolha **Criar** para adicionar o usuário a sua assinatura.

6.  Na página **Resultados** , você pode ver o nome da nova conta e sua senha temporária. O Intune cria a senha temporária automaticamente.

7.  Quando o novo usuário é exibido no Centro de administração do Office 365, verifique se o novo usuário foi criado com êxito:

    1.  No [console de administração do Intune](https://manage.microsoft.com/), escolha **Administrador** &gt; **Portal da Empresa** e role até a parte inferior da tela. Copie a URL mostrada em **Portal da Empresa do Intune**.

    2.  Abra uma nova janela do navegador em "modo de privacidade" (no Internet Explorer, escolha **Ferramentas** &gt; **Navegação InPrivate**) ou abra uma nova janela do navegador em um dispositivo diferente e, em seguida, navegue para a URL que você copiou na etapa anterior. Quando os usuários entrarem pela primeira vez, deverão fornecer uma nova senha para a conta.

## Adicionar usuários em massa
Para adicionar usuários em massa no Intune, use o assistente **Adicionar usuários em massa** para carregar um arquivo de valores separados por vírgulas (CSV) que contém os dados dos seus usuários. Os links do assistente permitem que você baixe um arquivo CSV de exemplo e o modelo em branco. A primeira linha do arquivo CSV deve conter, na ordem correta, cada um dos rótulos da coluna de dados do usuário. Então, para cada usuário do arquivo CSV, você deve incluir o **nome de usuário** (como **bob@contoso.com**) e um **nome de exibição** (como **Bob Kelly**).

1.  No [Centro de administração do Office 365](http://go.microsoft.com/fwlink/?LinkID=787455), escolha **Usuários** &gt; **Novo**.

2.  Escolha **Adicionar em massa** para iniciar o assistente Adicionar usuários em massa.

3.  Na página **Selecionar arquivo**, escolha **Procurar** para especificar e carregar um arquivo CSV existente no computador. Você também pode baixar um arquivo CSV de exemplo ou um arquivo de modelo em branco usando os links no assistente.

4.  Na página **Verificação**, examine os resultados e escolha **Exibir** para obter mais detalhes.

5.  Na página **Configurações**, confirme se o status de entrada é **Permitido** e defina o **local**. Essas configurações se aplicam a todas as contas de usuários adicionados pelo arquivo CSV.

6.  Na página **Grupo**, escolha **Avançar** para aceitar o padrão e atribuir uma licença do Intune a todos os usuários adicionados pelo arquivo CSV. Por padrão, a caixa de seleção é selecionada, o que atribui uma licença do Intune a cada conta.

7.  Na página **Email**, especifique até cinco endereços de email que receberão a notificação dos nomes de usuários e senhas temporárias que o Intune cria para cada conta. Separe vários endereços de email usando ponto-e- vírgula (;). Escolha **Criar** para adicionar os usuários à sua assinatura.

8.  Na página **Resultados** , você pode ver os nomes de conta e senha temporária para cada conta de usuário.

Cada conta de usuário adicionada por importação aparece agora no nó **Usuários** do Centro de administração do Office 365. Quando novos usuários entrarem pela primeira vez, deverão especificar uma nova senha para a conta de usuário.

### Próximas etapas
Parabéns! Você concluiu a etapa 2 do passo a passo da *avaliação do Microsoft Intune*.

>[!div class="step-by-step"]

>[&larr; **Inscreva-se para uma avaliação**](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-1.md)     [**Criar grupos** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md)  



<!--HONumber=Jul16_HO3-->


