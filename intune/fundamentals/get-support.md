---
title: Como obter suporte para o Microsoft Intune
titleSuffix: Microsoft Intune
description: Conecte-se e ligue para o suporte das assinaturas de avaliação e paga do Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 08/01/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 7fc95d17-098e-4da5-8a09-a96476569dd9
ms.reviewer: cacamp
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 91627a47f9dccfb436e64aaadeeb392648dff821
ms.sourcegitcommit: 0be25b59c8e386f972a855712fc6ec3deccede86
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72585290"
---
# <a name="how-to-get-support-for-microsoft-intune"></a>Como obter suporte para o Microsoft Intune  

[!INCLUDE [azure_portal](../../intune-classic/includes/note-for-both-portals.md)]  
  
A Microsoft fornece suporte técnico global, de pré-vendas, cobrança e assinatura para o Microsoft Intune. O suporte está disponível online e por telefone para versões de avaliação e assinaturas pagas. O suporte técnico online está disponível apenas em inglês e japonês. O suporte via telefone e o suporte de cobrança online estão disponíveis em outros idiomas.

Como administrador do Intune, você pode usar a opção **Ajuda e Suporte** para abrir um tíquete de suporte online para o Intune no portal do Azure. Para criar e gerenciar um incidente de suporte, sua conta deve ter uma função do Azure AD (Azure Active Directory) que inclui a *ação* **microsoft.office365.supportTickets/tickets/manage**. Para saber mais sobre funções e as permissões do Azure AD necessárias para criar um tíquete de suporte, confira [Funções de administrador no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal).  

>[!IMPORTANT]  
> Para obter suporte técnico de produtos de terceiros que funcionam com o Intune (como, Saaswedo, Cisco ou Lookout) entre em contato primeiro com o fornecedor do produto. Antes de abrir uma solicitação de suporte do Intune, verifique se você configurou o outro produto corretamente.
>
> Para obter informações sobre como solucionar problemas relacionados ao Microsoft Intune, consulte a [seção Solucionar problemas](help-desk-operators.md) da documentação do Intune.

## <a name="known-issues-for-creating-support-incidents"></a>Problemas conhecidos para a criação de incidentes de suporte  

Se sua conta tiver as permissões necessárias, mas não conseguir acessar a Ajuda e Suporte, ou criar ou gerenciar um incidente de suporte, veja os problemas conhecidos a seguir e suas resoluções:  
- Token de usuário obsoleto em sua conta. Para resolver esse problema, saia de todas as sessões de console ativas, entre novamente e, em seguida, tentar criar ou gerenciar um incidente de suporte. 
- Várias sessões ativas. Se você estiver conectado com mais de um usuário ou sessão, desconecte todos os consoles com exceção de um. Em seguida, com uma única sessão ativa, tente criar ou gerenciar um incidente de suporte.

Estas são as ações adicionais que podem ser necessárias para resolver problemas de acesso:
- Limpe todos os cookies de sua sessão de navegador ativa e tente criar ou gerenciar novamente um incidente de suporte.
- Use um sessão de navegação InPrivate para entrar no Intune e tente criar ou gerenciar um incidente de suporte.  

Se as soluções anteriores não ajudarem, acesse o [Centro de administração do Microsoft 365](https://admin.microsoft.com) e crie um tíquete de suporte a partir daí. Estamos trabalhando em uma correção que estará disponível no segundo semestre.  

## <a name="help-and-support-experience"></a>Experiência de Ajuda e suporte  

A experiência de Ajuda e suporte para o Intune está disponível no [Portal de Gerenciamento de dispositivos do Microsoft 365](https://devicemanagement.microsoft.com) e em todas as folhas (ou páginas) do Intune no portal do Azure. 

![Folhas do Intune](./media/get-support/intune-blades.png)


A experiência de *Ajuda e suporte* é semelhante à experiência observada no [Centro de administração do Microsoft 365](https://admin.microsoft.com/) e substitui a anterior *Ajuda + suporte*, que permanece em vigor para outros serviços no Azure. 

Para acessar a Ajuda e suporte, use as seguintes opções:  
- **Painel de Gerenciamento de Dispositivos:**
  - Depois de selecionar uma área de recursos para o Intune, selecione a opção para **Ajuda e suporte**.
  - Em qualquer nó no portal de gerenciamento de dispositivos, selecione o ícone **?** ícone no canto superior direito do portal e use o menu suspenso para selecionar o serviço para o qual você deseja ajuda. O ícone **?** no portal Gerenciamento de dispositivos dá suporte a vários serviços e você deve selecionar o serviço específico para o qual deseja assistência.  

    ![Selecione o serviço](./media/get-support/select-a-service.png)

    Depois de selecionar um serviço, você verá a página *Ajuda e suporte* desse serviço, onde poderá [especificar detalhes](#specify-details-about-an-issue) sobre o problema específico para o qual deseja obter ajuda.  

    Se os resultados da sua pesquisa não corresponderem às expectativas do serviço, verifique se o serviço correto foi selecionado. A seleção de serviço aparece logo após *Ajuda e suporte*.  Se o serviço certo não foi selecionado, clique em *Selecionar um serviço* para retornar à lista suspensa de seleção de serviço.   

    ![Confirme o serviço](./media/get-support/confirm-your-service-selection.png) 


- **No portal do Azure:**
  - Selecione **Ajuda e suporte** em qualquer folha ou página do Intune

  No portal do Azure, se você selecionar o ícone **?** no canto superior direito ou **Ajuda + suporte** no painel de navegação à esquerda, você abre a *Ajuda + suporte* para o Azure. Na *Ajuda + suporte* do Azure, não é possível abrir diretamente um incidente de suporte do Intune, mas você pode acessar a página *Ajuda e suporte* do Intune executando as seguintes ações: 
  1. Selecione Nova solicitação de suporte.
  2. Para Tipo de problema, especifique Técnico.
  3. Para Serviço, especifique Microsoft Intune.
  4. Selecione o link Página de Ajuda e Suporte do Intune.

> [!NOTE]  
> Se a instância do Intune estiver hospedada na nuvem privada para entidades governamentais, também conhecidas como uma nuvem soberana, como o Azure Governamental, confira o [Suporte do Intune para a nuvem privada governamental](#intune-support-for-private-cloud-for-government), posteriormente neste artigo. A experiência de *Ajuda e suporte* do Intune não estará disponível na nuvem privada governamental até o final deste ano. 


Quando você abre a *Ajuda e suporte*, o portal exibe uma exibição que depende se você tem ou não incidentes de suporte ativos, e quando você tem o Suporte Premier, alguns elementos e opções adicionais:
- **Nenhum incidente de suporte ativo**: Você verá a página **Precisa de ajuda?**, como pode ser visto na imagem a seguir no painel Gerenciamento de Dispositivos.  
- **Incidentes de suporte ativos**: Você verá a página [Tíquetes de suporte](#view-support-cases), que exibe a lista dos seus incidentes ativos.  
- **Contrato de suporte Premier**: Sua experiência é a mesma das duas primeiras opções, embora você veja os seguintes elementos adicionais na página Precisa de ajuda?: 
  - Após o título de página **Precisa de ajuda?**, você verá o banner do Suporte Premier:  
    ![Banner do Suporte Premier](./media/get-support/premier-banner.png)
  - Na seção **Obter Suporte** da página, você pode definir o nível inicial de **Gravidade** ao criar uma solicitação de serviço por telefone.


![Painel de Gerenciamento de Dispositivo e a página Precisa de Ajuda?](./media/get-support/help-support-dashboard.png)

Nessa exibição, você pode executar as seguintes ações:

1. [Especificar detalhes](#specify-details-about-an-issue) sobre o problema específico com o qual você deseja obter ajuda  
2. [Exibir a ajuda contextual](#view-context-sensitive-help) e soluções relacionadas com base nos detalhes especificados por você  
3. [Obter suporte](#get-support) usando email ou telefone  
4. [Exibir casos de suporte](#view-support-cases) abertos anteriormente usando esse novo fluxo de trabalho  

### <a name="specify-details-about-an-issue"></a>Especificar os detalhes sobre um problema 

Quando você abre a Ajuda e suporte em uma localização com suporte da nova experiência, a página **Precisa de ajuda?** é aberta. Nessa página, você pode especificar os detalhes sobre um problema. Conforme você insere detalhes, o console oferece consultas comuns com base em palavras-chave que você usa. Selecione uma opção oferecida ou complete sua própria descrição do problema. Se você inserir sua própria descrição, selecione **Obter ajuda** para enviá-la. Depois de enviar uma consulta, o console retorna informações contextuais que podem ajudar a solucionar o problema.

A seguir, estão exemplos de consultas que você pode enviar:
  
- *Não é possível restaurar o dispositivo iOS*  
- *Não é possível criar política de Acesso Condicional*  

![Especificar o problema na página Precisa de Ajuda?](./media/get-support/describe-the-issue.png)

### <a name="view-context-sensitive-help"></a>Exibir ajuda contextual 

Depois de selecionar uma opção oferecida ou enviar sua própria consulta, os resultados contextuais aparecerão em **Exibir soluções**. Esses resultados incluem orientação de autoatendimento específicas do Intune e resultados adicionais retornados de uma pesquisa na Web com base em critérios de consulta.  
![Exibir resultados](./media/get-support/view-results.png)

### <a name="get-support"></a>Obter suporte 

Se a orientação baseada na Web ou em autoatendimento não ajudar a resolver o problema, use o console para abrir um problema de suporte por email ou telefone.  
Na página **Precisa de Ajuda?**, selecione a opção que você deseja usar.  

  > [!NOTE] 
  > As solicitações de suporte por email não estão disponíveis para todos os locatários.  

- Para uma solicitação por email, forneça seu endereço de email e, opcionalmente, adicione anexos aos seu envio. Selecione **Enviar** para abrir a solicitação. 

  ![Solicitação por email](./media/get-support/email-support.png)
  
- Para uma solicitação por telefone, informe o número de telefone. Opcionalmente, você pode incluir seu endereço de email e adicionar anexos ao seu envio. Selecione Ligar para mim para enviar a solicitação.  



   ![Solicitação por telefone](./media/get-support/phone-support.png)

**Suporte Premier**:  
Se você possui um contrato de suporte Premier, tem as mesmas opções para criar um incidente de suporte por telefone. Você também pode especificar a **Gravidade** para o retorno de chamada do suporte e optar por criar o tíquete de suporte em relação ao seu contrato de Missão Crítica.  

![Opções de suporte Premier](./media/get-support/premier-phone-support-options.png)


### <a name="view-support-cases"></a>Exibir casos de suporte  

Selecione o botão de histórico para exibir os incidentes de suporte que você criou.  

![Exibir casos de suporte](./media/get-support/view-support-tickets.png)

- Somente os casos de suporte que você abrir usando o novo fluxo de trabalho ficarão visíveis de dentro desse fluxo de trabalho. Para exibi-los, use uma exibição de Ajuda e suporte no console do Gerenciamento de Dispositivos ou em uma folha do Intune no portal do Azure. Esses casos têm números de oito dígitos. Você também pode exibir esses casos no centro de administração do Microsoft 365.  

- Os casos que você abriu quando não estava usando a experiência de Ajuda e suporte do Intune permanecem inalterados. Para exibi-los, é necessário usar uma exibição de Ajuda e suporte que não faça parte da experiência do Intune ou o painel de Gerenciamento de Dispositivos. Esses casos têm números que começam com **117** ou **118** e têm 15 dígitos. Para exibi-los:

    1. Entre no Azure (<https://portal.azure.com>) com suas credenciais de administrador do Intune e selecione o *?* no canto superior direito do portal e selecione *Ajuda + suporte* para ir para a página [Ajuda + suporte do Azure](https://ms.portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/overview).

    2. Na página **Ajuda + suporte**, é possível ver a lista de **Solicitações de suporte recentes** e selecioná-las para ver detalhes adicionais.
 

## <a name="azure-help--support-experience"></a>Experiência de Ajuda + suporte do Azure 

Quando você usa o painel de navegação esquerdo **Ajuda + suporte**, ou usa a opção **?** no canto superior direito do portal do Azure, você abre a experiência de suporte da Ajuda+ do Azure, que é diferente da ajuda e da experiência do Intune.  

A partir de abril de 2019, você não poderá acessar a experiência de *Ajuda + suporte* do Azure para obter assistência com o Intune, a menos que sua assinatura esteja em uma nuvem privada para entidades governamentais.  

Se a instância do Intune não for executada em uma nuvem privada governamental, a navegação pela *Ajuda + suporte* do Azure redirecionará você para a experiência de *Ajuda e suporte* do Intune para criar e gerenciar incidentes de suporte.  


## <a name="intune-support-for-private-cloud-for-government"></a>Suporte do Intune para nuvem privada governamental  

Quando sua assinatura do Intune está hospedada na nuvem privada para entidades governamentais, também conhecida como uma nuvem soberana como o Azure Governamental, você ainda não tem acesso à experiência de suporte e Ajuda do Intune mais recente.  Em vez disso, use as informações a seguir e obtenha suporte para o Intune. 


### <a name="create-an-online-support-ticket"></a>Criar um tíquete de suporte online 

>[!IMPORTANT]    
> À medida que *Ajuda e suporte* faz a transição para um novo sistema que ainda não está disponível para a nuvem privada governamental, quando você cria um incidente de suporte, o portal identifica um caso de suporte que usa um número de identificação de 15 dígitos. Quando o caso de 15 dígitos é criado, um espelho desse caso é criado para uso pelo Suporte da Microsoft. Esse caso de espelho é criado em um novo sistema de suporte, usa uma ID de caso de 8 dígitos e é usado pelos serviços de suporte para acompanhar todo o trabalho e as comunicações de seu incidente de suporte. Logo após a criação do seu caso de 15 dígitos, você receberá um email que identifica o número de 8 dígitos do caso de suporte espelhado que é usado pelos serviços de suporte.  
> 
> Dê suporte ao trabalho pessoal e comunique-se a partir do caso de suporte de 8 dígitos e use apenas o caso de suporte de 8 dígitos para registrar as comunicações e acompanhar o progresso do incidente. Portanto, você receberá atualizações por email desse caso de suporte de 8 dígitos que serve como seu histórico de trabalho de caso. Nenhum detalhe é registrado no incidente de suporte de 15 dígitos. Quando o suporte é concluído e o caso de suporte de 8 dígitos é encerrado, esse status é refletido no caso de suporte de 15 dígitos que você pode visualizar no portal do Azure.  Nenhuma outra atualização ou alteração de status deve ser esperada para o caso de suporte de 15 dígitos.  
> 
> Quando as transições entre ferramentas de suporte forem concluídas no final deste ano, a experiência de suporte do Intune hospedada na nuvem do governo será semelhante à experiência padrão da *Ajuda e suporte* atualmente disponível para assinaturas do Intune hospedadas na nuvem pública.  


1. Entre no Portal do Azure (<https://portal.azure.com>) com suas credenciais de administrador do Intune e selecione o **?** no canto superior direito do portal e selecione **Ajuda + suporte** para ir para a página [Ajuda + suporte do Azure](https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/overview).

   ![Imagem do link de ponto de interrogação com o link de Ajuda + suporte realçado](./media/get-support/azure-get-support.png)

2. Na página **Ajuda + suporte** do Azure, selecione **Nova solicitação de suporte**.

   ![Imagem do link Nova solicitação de suporte realçado na página Ajuda e suporte](./media/get-support/azure-support-ticket-link.png)

3. Na guia **Básico**, para a maioria dos problemas de suporte técnico do Intune, escolha as seguintes opções:
   - **Tipo de problema**: **Técnico**
   - **Assinatura**: <*sua assinatura*>
   - **Serviço**: **Microsoft Intune**
   - **Tipo de problema**: Escolha seu tipo de problema no menu suspenso.
   - **Subtipo de problema**: Escolha o subtipo de problema no menu suspenso.
   - **Assunto**: descreva resumidamente o problema para o qual você deseja obter ajuda.

   ![Imagem da guia Informações Básicas na página Ajuda + suporte – Nova solicitação de suporte](./media/get-support/help-new-support-case-basics.png)

   Escolha **Avançar: Soluções** para continuar.
4. Na guia **Soluções**, examine as etapas recomendadas que podem ajudar você a resolver o problema sem precisar abrir um tíquete. Se você ainda quiser criar uma solicitação de suporte depois de verificar as etapas, clique em **Avançar: Detalhes**.

   ![Imagem da guia Soluções na página Ajuda + suporte – Nova solicitação de suporte](./media/get-support/help-new-support-case-solutions.png)
5. Na guia **Detalhes**, preencha os detalhes de seu problema, o método de suporte, suas informações de contato e, em seguida, clique em **Avançar: Examinar + criar**.

   ![Imagem da guia Detalhes na página Ajuda + suporte – Nova solicitação de suporte](./media/get-support/help-new-support-case-details.png)
6. Examine as informações, verifique se estão corretas e, em seguida, escolha **Criar** para enviar sua solicitação de suporte.

   ![Imagem da guia Examinar + criar na página Nova solicitação de suporte](./media/get-support/help-new-support-case-create.png)

>[!IMPORTANT]
>Se tiver uma dúvida referente à cobrança ou à assinatura, você poderá abrir uma ocorrência para obter suporte por meio do [Centro de administração do Microsoft 365](https://admin.microsoft.com/Support/SupportEntry.aspx).

### <a name="view-support-requests"></a>Exibir todas as solicitações de suporte  

Você pode exibir suas solicitações de suporte no portal do Azure. No entanto, informações limitadas estão disponíveis.  Para exibir seus incidentes: 

1. Entre no Azure (<https://portal.azure.com>) com suas credenciais de administrador do Intune e selecione o **?** no canto superior direito do portal e selecione **Ajuda + suporte** para ir para a página [Ajuda + suporte do Azure](https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/overview).

2. Na página **Ajuda + suporte**, é possível ver a lista de **Solicitações de suporte recentes**.

   > [!IMPORTANT]  
   > Os clientes da nuvem privada governamental podem exibir apenas o número do caso de suporte de 15 dígitos e o status do incidente. Todas as comunicações de casos e acompanhamento de trabalho ou alertas são enviados por email e referenciam o número do caso de suporte de 8 dígitos criado como um espelho do caso de suporte aberto no console do Intune.   

## <a name="additional-resources"></a>Recursos adicionais  

- [Suporte de cobrança e gerenciamento de assinaturas](https://support.office.com/article/Contact-Office-365-for-business-support-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)
- [Licenciamento por volume](https://go.microsoft.com/fwlink/p/?LinkID=282015)
- [Solucionar problemas do Intune](help-desk-operators.md)
