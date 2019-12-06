---
title: Como obter suporte para o Microsoft Intune
titleSuffix: Microsoft Intune
description: Conecte-se e ligue para o suporte das assinaturas de avaliação e paga do Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 7fc95d17-098e-4da5-8a09-a96476569dd9
ms.reviewer: srik
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5aca7dbae7a74af399bcbf21aec1dd9dd2d1e851
ms.sourcegitcommit: 2fddb293d37453736ffa54692d03eca642f3ab58
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74390756"
---
# <a name="how-to-get-support-for-microsoft-intune"></a>Como obter suporte para o Microsoft Intune

A Microsoft fornece suporte técnico global, de pré-vendas, cobrança e assinatura para o Microsoft Intune. O suporte está disponível online e por telefone para versões de avaliação e assinaturas pagas. O suporte técnico online está disponível apenas em inglês e japonês. O suporte via telefone e o suporte de cobrança online estão disponíveis em outros idiomas.

Como administrador do Intune, você pode usar a opção **Ajuda e Suporte** para abrir um tíquete de suporte online para o Intune no portal do Azure. Para criar e gerenciar um incidente de suporte, sua conta deve ter uma função do Azure AD (Azure Active Directory) que inclua a *ação* **microsoft.office365.supportTickets**. Para saber mais sobre funções e as permissões do Azure AD necessárias para criar um tíquete de suporte, confira [Funções de administrador no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal).

>[!IMPORTANT]
> Para obter suporte técnico de produtos de terceiros que funcionam com o Intune (como, Saaswedo, Cisco ou Lookout) entre em contato primeiro com o fornecedor do produto. Antes de abrir uma solicitação de suporte do Intune, verifique se você configurou o outro produto corretamente.
>
> Para obter informações sobre como solucionar problemas relacionados ao Microsoft Intune, consulte a [seção Solucionar problemas](help-desk-operators.md) da documentação do Intune.


## <a name="help-and-support-experience"></a>Experiência de Ajuda e suporte

A experiência de Ajuda e suporte do Intune está disponível no [Centro de Administração do Gerenciador do Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431) e em todos os painéis (ou páginas) em Intune no portal do Azure.

A experiência de *Ajuda e suporte* é semelhante à experiência observada no [Centro de administração do Microsoft 365](https://admin.microsoft.com/) e substitui a anterior *Ajuda + suporte*, que permanece em vigor para outros serviços no Azure.

> [!TIP]
> A partir de 18 de novembro de 2019, uma experiência atualizada e simplificada no console para obter ajuda e suporte será lançada para os locatários. Se essa nova experiência ainda não estiver disponível para você, estará em breve.

### <a name="options-to-access-help-and-support"></a>Opções para acessar a Ajuda e suporte

Quando você usa um locatário recém-criado para o Intune, é possível que a abertura da *Ajuda e Suporte* falhe e exiba a seguinte mensagem:

- *Encontramos um problema desconhecido. Atualize a página, mas se o problema persistir, crie um caso no [Centro de Administração do M365](https://admin.microsoft.com) e indique a ID da sessão fornecida.*

Os detalhes do erro incluem, entre outros, os detalhes de *ID da Sessão* e da *Extensão*. 
 
Esse problema ocorre quando você ainda não autenticou sua nova conta de locatário por meio do **Centro de Administração do M365**, em https://admin.microsoft.com, ou do **portal do Office 365**, em https://portal.office.com. Para resolver esse problema, selecione o link do *Centro de Administração do M365* na mensagem, ou acesse https://portal.office.com e faça login. Após a autenticação em qualquer site, a *Ajuda e Suporte* do Intune se tornará acessível.


**Acessar a Ajuda e Suporte**:

- **No portal do Azure**

  - Selecione **Ajuda e suporte** em qualquer folha ou página do Intune.

  > [!NOTE]  
  > Se a instância do Intune estiver hospedada na nuvem privada para o governo, também conhecidas como uma nuvem soberana, como o Azure Governamental, confira o [Suporte do Intune para a nuvem privada governamental](#intune-support-for-private-cloud-for-government), posteriormente neste artigo. A experiência de *Ajuda e suporte* do Intune não estará disponível na nuvem privada governamental até o próximo ano.

- **No Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft**
  - Depois de selecionar uma área de recursos para o Intune, selecione a opção para **Ajuda e suporte**.
  - Em qualquer nó no Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft, selecione o ícone **?** ícone no canto superior direito do portal e use o menu suspenso para selecionar o serviço para o qual você deseja ajuda. O ícone **?** no Centro de Administração do Gerenciador de Ponto de Extremidade dá suporte a vários serviços. É necessário selecionar o serviço específico para o qual deseja receber assistência.  

    ![Selecione o serviço](./media/get-support/select-a-service.png)

    Depois de selecionar um serviço, você verá a página *Ajuda e suporte* desse serviço, onde poderá especificar detalhes para [encontrar soluções](#find-solutions) para o problema específico.

    Quando os resultados da sua pesquisa não corresponderem às expectativas do serviço, verifique se o serviço correto foi selecionado. A seleção de serviço aparece logo após *Ajuda e suporte*.  Se o serviço certo não foi selecionado, clique em *Selecionar um serviço* para retornar à lista suspensa de seleção de serviço.

    ![Confirme o serviço](./media/get-support/confirm-your-service-selection.png)

###  <a name="the-support-experience"></a>A experiência de suporte

  Quando você abre a Ajuda e Suporte, o portal exibe a janela **Precisa de ajuda?** :

  ![Exibir a janela de ajuda necessária](./media/get-support/need-help.png)

  No canto superior esquerdo, há três ícones que você pode selecionar para abrir painéis diferentes da janela *Precisa de ajuda?* . O painel que você está visualizando está identificado pelo sublinhado.

  Os clientes com um contrato de suporte **Premier** ou **Unificado** têm [opções adicionais](#premier-and-unified-support-customers) para suporte e veem uma faixa em *Precisa de ajuda?* semelhante à imagem a seguir: ![Faixa Premier](./media/get-support/premier-banner.png)

  *Precisa de ajuda?* abre no painel *Localizar Soluções*. No entanto, se você tiver um caso de suporte ativo, a janela será aberta no painel *Solicitações de serviço*, no qual poderá visualizar os detalhes sobre os casos de suporte ativos e fechados.

#### <a name="find-solutions"></a>Localizar soluções

![Selecione o painel Localizar soluções](./media/get-support/find-solutions.png)

No painel *Localizar soluções*, insira alguns detalhes sobre um problema na caixa de texto fornecida. Com base no texto inserido sobre um problema, o painel é preenchido com informações que são possíveis correspondências. Você também receberá links para artigos recomendados que podem ajudá-lo a resolver o problema.

Ao encontrar uma correspondência forte para os detalhes que você descreveu, as dicas de solução de problemas podem aparecer direto na janela *Precisa de ajuda?* .

Por exemplo, você pode inserir **Erros de sincronização de senha**. Os resultados incluem a orientação de solução de problemas diretamente no painel e links para artigos recomendados de nossa biblioteca de documentação.

![Exibir as informações de solução de problemas](./media/get-support/troubleshooting-insights.png)

#### <a name="contact-support"></a>Contate o suporte

![Selecionar o painel Contate o suporte](./media/get-support/contact-support.png)

No painel *Contate o suporte*, você pode enviar uma solicitação de assistência. Esse painel estará disponível depois que você fornecer algumas palavras-chave básicas no painel *Localizar soluções*.

Ao solicitar assistência, forneça uma descrição do problema com o máximo de detalhes necessário.  Depois de confirmar seu telefone e enviar informações de contato por email, selecione o método de contato preferencial. A janela exibe um tempo de resposta para cada método de contato, o que fornece uma expectativa de quando você será contatado. Antes de enviar sua solicitação, anexe arquivos como logs ou capturas de tela que podem ajudar a fornecer mais detalhes sobre o problema.

![Formulário de contato com o suporte](./media/get-support/contact-support-form.png)

Depois de preencher as informações necessárias, selecione **Entrar em contato comigo** para enviar a solicitação.

#### <a name="service-requests"></a>Solicitações de serviço

![Selecione o painel Solicitações de serviço](./media/get-support/service-requests.png)

O painel *Solicitações de serviço* exibe seu histórico de casos. Os casos ativos estão na parte superior da lista, com os problemas fechados também disponíveis para revisão.

![Exibir sua lista de solicitações de serviço](./media/get-support/service-requests-pane.png)

Se você tiver um número de caso de suporte ativo, poderá inseri-lo aqui para acessar esse problema ou selecionar qualquer incidente na lista de incidentes ativos e fechados para visualizar mais informações sobre ele.

Ao terminar de visualizar os detalhes de um incidente, selecione a seta para a esquerda exibida na parte superior da janela de solicitações de serviço, logo acima dos três ícones do painel *Precisa de ajuda?* . A seta para trás retorna a exibição para a lista de incidentes de suporte que você abriu.

#### <a name="premier-and-unified-support-customers"></a>Clientes de suporte Premier e Unificado

Como cliente com um contrato de suporte **Premier** ou **Unificado**, você pode especificar uma gravidade para o problema e agendar um retorno de chamada de suporte para um horário e dia específicos. Essas opções estão disponíveis ao abrir ou enviar um novo problema e ao editar um caso de suporte ativo.

**Gravidade** – as opções para especificar a gravidade de um problema dependem do seu contrato de suporte:

- *Premier*: gravidade A, B ou C
- *Unificado*: crítico ou não crítico

Selecionar um problema de gravidade **A** ou **Crítico** limita você a um caso de suporte por telefone, que fornece a opção mais rápida para obter suporte.

**Agendamento de retorno de chamada** – você pode solicitar um retorno de chamada em um horário e dia específicos.

## <a name="azure-help--support-experience"></a>Experiência de Ajuda + suporte do Azure

Você não pode mais acessar a experiência de *Ajuda + suporte* do Azure para obter assistência com o Intune, a menos que sua assinatura esteja em uma nuvem privada para o governo.
Se a instância do Intune não for executada em uma nuvem privada governamental, a navegação pela *Ajuda + suporte* do Azure redirecionará você para a experiência de *Ajuda e suporte* do Intune para criar e gerenciar incidentes de suporte:

Quando você usa o painel de navegação esquerdo **Ajuda + suporte**, ou usa a opção **?** para abrir o painel *Ajuda* e, em seguida, seleciona **Ajuda + suporte**, você abre a página *Ajuda + suporte* do Azure. 


Nessa página, selecione **+ Nova solicitação de suporte** para abrir a guia *Básico* da página *Ajuda + suporte + Nova solicitação de suporte*.

![Ajuda + suporte](./media/get-support/help-plus-support.png)

Nessa página:

- Em *Tipo de problema*, selecione **Técnico**.
- Em *Serviço*, selecione **Microsoft Intune**.

  Em seguida, você verá um link que redireciona para a [página de Ajuda e suporte do Intune](https://aka.ms/intunehelpsupport).
  
  ![Nova solicitação de suporte](./media/get-support/new-request.png)


## <a name="intune-support-for-private-cloud-for-government"></a>Suporte do Intune para nuvem privada governamental

Quando sua assinatura do Intune está hospedada na nuvem privada para o governo, também conhecida como uma nuvem soberana como o Azure Governamental, você ainda não tem acesso à experiência de suporte e Ajuda do Intune mais recente.  Em vez disso, use as informações a seguir e obtenha suporte para o Intune.

### <a name="create-an-online-support-ticket"></a>Criar um tíquete de suporte online

>[!IMPORTANT]
> À medida que *Ajuda e suporte* faz a transição para um novo sistema que ainda não está disponível para a nuvem privada governamental, quando você cria um incidente de suporte, o portal identifica um caso de suporte que usa um número de identificação de 15 dígitos. Quando o caso de 15 dígitos é criado, um espelho desse caso é criado para uso pelo Suporte da Microsoft. Esse caso de espelho é criado em um novo sistema de suporte, usa uma ID de caso de 8 dígitos e é usado pelos serviços de suporte para acompanhar todo o trabalho e as comunicações de seu incidente de suporte. Logo após a criação do seu caso de 15 dígitos, você receberá um email que identifica o número de 8 dígitos do caso de suporte espelhado que é usado pelos serviços de suporte.
>
> Dê suporte ao trabalho pessoal e comunique-se a partir do caso de suporte de 8 dígitos e use apenas o caso de suporte de 8 dígitos para registrar as comunicações e acompanhar o progresso do incidente. Portanto, você receberá atualizações por email desse caso de suporte de 8 dígitos que serve como seu histórico de trabalho de caso. Nenhum detalhe é registrado no incidente de suporte de 15 dígitos. Quando o suporte é concluído e o caso de suporte de 8 dígitos é encerrado, esse status é refletido no caso de suporte de 15 dígitos que você pode visualizar no portal do Azure.  Nenhuma outra atualização ou alteração de status deve ser esperada para o caso de suporte de 15 dígitos.
>
> Quando as transições entre ferramentas de suporte forem concluídas no final deste ano, a experiência de suporte do Intune hospedada na nuvem do governo será semelhante à experiência padrão da *Ajuda e suporte* atualmente disponível para assinaturas do Intune hospedadas na nuvem pública.

1. Entre no Portal do Azure (<https://portal.azure.us>) com suas credenciais de administrador do Intune e selecione o **?** no canto superior direito do portal e selecione **Ajuda + suporte** para ir para a página [Ajuda + suporte do Azure](https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/overview).

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
