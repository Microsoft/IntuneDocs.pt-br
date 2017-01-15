---
title: "Inscrever-se para uma avaliação gratuita de 30 dias do Microsoft Intune | Documentos da Microsoft"
description: "Inscreva-se e configure uma avaliação de 30 dias do Microsoft Intune."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 11/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 619a1d11-3d22-4635-8f70-770eba3e1712
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ca4af205f8f391089e86e0ee7787e32813d54cca
ms.openlocfilehash: 6bd6cc3470c93f96e7c71b5d1efe6d9ffc045a7e


---

# <a name="sign-up-for-a-microsoft-intune-free-trial"></a>Inscrever-se para uma avaliação gratuita do Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Este artigo explica como se inscrever para uma avaliação do Intune e prepara a sua avaliação com alguns usuários para que você possa seguir o guia de avaliação associado e ver como o Intune gerencia dispositivos móveis. <!---or app data when devices are not enrolled in Intune.--->

>[!Note]
> A partir de dezembro de 2016, o Microsoft Intune está migrando para o Portal do Azure e algumas inscrições de avaliação gratuita estarão no Intune no Portal do Azure, enquanto outras estarão no Intune clássico. Caso sua avaliação esteja no Portal do Azure, o [conteúdo de visualização do Intune Azure](https://docs.microsoft.com/en-us/intune-azure/introduction/what-is-microsoft-intune) será mais útil para você depois de concluir as etapas deste artigo.

## <a name="assumptions"></a>Suposições
Este artigo de inscrição e o guia de avaliação pressupõem que você está usando a versão de avaliação apenas para fins de avaliação e pretende iniciar com um ambiente limpo quando assinar.

Para facilitar o uso da versão de avaliação, estamos configurando um ambiente muito simples, que usa apenas o Intune e pressupõe que ele seja o único método de gerenciamento de dispositivos (conhecido como a autoridade de gerenciamento de dispositivo móvel). No entanto, neste guia, apontaremos para o conteúdo técnico mais profundo se você quiser explorar um pouco mais.

Na versão de avaliação, é possível fazer tudo o que se faz em uma versão de assinatura. A única diferença é que você está limitado a 100 contas de usuário na avaliação.

## <a name="sign-up-for-your-trial"></a>Inscrever-se para uma avaliação
Visite a página [Inscrição do Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) e preencha o formulário para se inscrever para uma assinatura de avaliação.

Se você tiver uma conta corporativa ou de estudante e quiser usá-la para sua avaliação do Intune, execute [estas instruções de conexão](https://docs.microsoft.com/en-us/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-1). No entanto, este artigo e seus guias de avaliação presumem que você não está usando uma conta dessas.

> [!TIP]
> Se a maioria de suas operações de TI e os usuários estiverem em uma localidade diferente da sua, convém definir essa localidade para a versão de avaliação para testar o desempenho.

### <a name="post-sign-up-considerations"></a>Considerações após a inscrição
Caso se inscreva para uma avaliação, você receberá uma mensagem de email com as informações da conta no endereço de email fornecido durante o processo de inscrição. Isso confirma que sua avaliação está ativa.

Depois de concluir o processo de inscrição, você será direcionado para uma página usada para adicionar usuários e atribuir a eles licenças usando o Centro de administração do Office 365. Na próxima vez que você se conectar no **Intune clássico** (https://manage.microsoft.com), você será direcionado automaticamente para o console de administração do Intune.

Caso sua avaliação esteja no **Portal do Azure**, acesse https://portal.azure.com e conecte-se com suas credenciais de avaliação do Intune.

## <a name="add-users"></a>Adicionar usuários
Antes de sair do Centro de administração do Office 365 para o Intune, será necessário adicionar alguns usuários à sua conta de avaliação.

No Centro de administração do Office 365, é possível adicionar usuários individualmente ou em massa carregando um arquivo .csv. Faremos ambos para configurar sua avaliação. No entanto, em seu ambiente de produção, você provavelmente desejará aproveitar suas contas de usuário do Azure Active Directory. Saiba mais sobre isso em nosso [Guia de Introdução](https://docs.microsoft.com/en-us/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3) e na seção [Próximas etapas](#Next-steps) deste artigo.

### <a name="add-an-individual-user"></a>Adicionar um usuário individual
1. Escolha uma das opções para adicionar um uso para abrir um formulário que permite que você crie um usuário. Somente os itens marcados com um asterisco (\*) são obrigatórios.
![Imagem das opções do botão Adicionar usuário](./media/sign-up/add-user.png)


2.  Ao adicionar o usuário, a etapa final será enviar um email com sua senha temporária do Intune. Para a finalidade dessa avaliação, use seu próprio endereço de email de trabalho para receber as informações de logon e veja o email que os usuários receberão. É possível usar essas identidades de usuário para registrar dispositivos de teste.<br/>

 ![Imagem da etapa final de adição de um usuário](./media/sign-up/new-user-2.png)

3. Se quiser atribuir a um usuário uma função administrativa, depois de criá-la, você poderá editar a função no Centro de administração do Office 365 selecionando o nome de usuário da lista de usuários e, em seguida, escolhendo **Editar** na linha de função para ver a lista de funções de usuário que você pode selecionar e atribuir a esse usuário.

 ![Imagem das opções de função de usuário](./media/sign-up/change-user-role.png)

### <a name="import-multiple-users"></a>Importar vários usuários
1. Você encontrará o assistente para importação de vários usuários na lista **Mais**.

 ![Imagem da opção para adicionar vários usuários](./media/sign-up/add-multiple-users.png)

2. Para ajudá-lo a configurar corretamente o seu arquivo .csv, você poderá baixar um arquivo de modelo para preencher com os dados do usuário. Baixe o arquivo .csv que contém os cabeçalhos e as informações de usuário de exemplo para ver exatamente o tipo de dados necessário para cada campo.

 ![Imagem da primeira etapa no assistente de registro em massa](./media/sign-up/bulk-enroll-step-1.png)


3. Depois que você criar e salvar o arquivo .csv, escolha **Procurar** para selecionar o arquivo. Verifique e escolha **Avançar**. Os usuários serão carregados e adicionados à lista de usuários ativos.

> [!NOTE]
> Os usuários não aparecerão no Intune até que tenham registrado um dispositivo a ser gerenciado.

Agora é hora de ir para o Intune para começar a gerenciar os usuários, seus aplicativos e seus dispositivos.

## <a name="keeping-the-admin-experiences-straight"></a>Mantendo as experiências do administrador objetivas
### <a name="classic-intune"></a>Intune clássico
Há dois portais que são usados para o Intune clássico:
- O Centro de administração do Office 365 ([portal.office.com](https://portal.office.com))
- O console de administração do Intune ([manage.microsoft.com](https://manage.microsoft.com))

Normalmente, você fará seu trabalho no console de administração do Intune, mostrado abaixo. Esse é o site no qual você pode configurar e gerenciar grupos, políticas, dispositivos e aplicativos.

![Imagem do console de administração do Intune](./media/sign-up/intune-admin-console.png)

No entanto, você usará o Centro de administração do Office 365, mostrado abaixo, para adicionar e gerenciar os usuários e outros aspectos da sua conta, incluindo cobrança e suporte.

![Imagem do centro de administração do Office 365](./media/sign-up/office-admin-center.png)

É possível navegar do Centro de administração do Office 365 para o console de administração do Intune. Os centros de administração estão no último item no painel de navegação à esquerda. Escolha **Intune** para abrir o console de administração do Intune em uma nova guia.

![Imagem de um link para o console de administração do Intune](./media/sign-up/link-to-intune.png)

Para voltar do Intune para o Centro de administração do Office 365, escolha a tarefa **Adicionar Usuários** na página Visão geral de grupos.

![Imagem de um link de volta para o Centro de administração do Office 365](./media/sign-up/task-add-users.png)

### <a name="intune-azure-preview"></a>Visualização do Intune no Azure
Há três portais que serão usados para a visualização do Intune Azure:
- O Centro de administração do Office 365 ([portal.office.com](https://portal.office.com))
- O painel do Intune no Azure ([portal.azure.com](https://portal.azure.com))
- O console de administração do Intune clássico ([manage.microsoft.com](https://manage.microsoft.com))

Na primeira conexão ao Intune no Azure, talvez você não o veja no painel do Azure. Para adicionar o serviço Intune ao painel do Azure:
1. Escolha **Mais serviços >** na lista de serviços do Azure à esquerda do painel e insira o Intune na caixa de pesquisa.
2. Escolha **Intune** na lista e selecione a estrela para adicionar o serviço à lista de serviços.<br/> ![Imagem da seleção do Intune na lista de serviços](./media/sign-up/azure-add-intune1.png)
3. Escolha **Intune** na lista de serviços para abrir o painel do Intune.

Normalmente, você fará seu trabalho no painel do Intune, mostrado abaixo. Esse é o site no qual você pode configurar e gerenciar grupos, políticas, dispositivos e aplicativos. É possível acessar o console de administração do Intune clássico por meio do painel, escolhendo o bloco **Abrir portal do Intune clássico**. Para retornar à visualização do Intune Azure, insira https://portal.azure.com na barra de endereços do navegador e escolha **Intune** novamente na lista de serviços.

 ![Imagem do painel do Intune](./media/sign-up/intune-azure-dashboard.png)


No entanto, você usará o Centro de administração do Office 365, mostrado abaixo, para adicionar e gerenciar os usuários e outros aspectos da sua conta, incluindo cobrança e suporte.

![Imagem do centro de administração do Office 365](./media/sign-up/office-admin-center.png)

Para ir do Centro de administração do Office 365 para o painel do Intune, insira https://portal.azure.com na barra de endereços do navegador. Escolha **Intune** na lista de serviços.

Para voltar do Intune ao Centro de administração do Office 365, insira https://portal.office.com na barra de endereços do navegador. Se você já estiver conectado ao Intune, será levado diretamente para o Centro de administração do Office 365.

## <a name="next-steps"></a>Próximas etapas
### <a name="classic-intune"></a>Intune clássico
Cenário de avaliação: [Avaliar o gerenciamento de dispositivo móvel no Microsoft Intune](mobile-device-management-trial-guide-microsoft-intune.md)

### <a name="intune-azure-preview"></a>Visualização do Intune no Azure
Saiba mais sobre o Intune em [Introduction to Microsoft Intune in the Azure portal preview](https://docs.microsoft.com/en-us/intune-azure/introduction/what-is-microsoft-intune) (Introdução ao Microsoft Intune na visualização do Portal do Azure)

### <a name="integration-with-other-products"></a>Integração com outros produtos
Saiba mais sobre como usar as contas de usuário do Azure Active Directory com o Intune:
- [Requisitos de identidade](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)
- [Requisitos de sincronização de diretórios](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)
- [Requisitos da autenticação multifator](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements)

Saiba mais sobre como usar o [Intune com System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/mdm/understand/hybrid-mobile-device-management)



<!--HONumber=Dec16_HO3-->


