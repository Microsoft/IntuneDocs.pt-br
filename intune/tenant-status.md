---
title: Página Status do Locatário do Microsoft Intune
titleSuffix: Microsoft Intune
description: Use a página Status do Locatário do Intune para exibir detalhes importantes do locatário sem sair do portal do Intune
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/23/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0cde1977b0c126f478abae06860110acc2f10444
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61514167"
---
# <a name="intune-tenant-status-page"></a>Página Status do Locatário do Intune
A página Status do Locatário é um hub centralizado em que é possível exibir os detalhes atuais e importantes sobre o seu locatário. Os detalhes incluem a disponibilidade e o uso da licença, o status do conector e comunicações importantes sobre o serviço do Intune.  

Para exibir o painel, no portal do Azure, acesse **Intune > Status do Locatário**.  O Status do Locatário é exibido no **grupo Ajuda e suporte**.  

A página é dividida em quatro áreas:

## <a name="tenant-details"></a>Detalhes do locatário
Detalhes do Locatário fornece informações rápidas sobre o locatário. Exiba detalhes como o nome e a localização do locatário, a Autoridade de MDM e o número de versão do serviço de locatários. O número da versão do serviço é um link que abre o artigo *Novidades no Intune* no Microsoft Docs. Em *Novidades*, é possível ler sobre os recursos e atualizações mais recentes dos serviços do Intune.  

Esta seção também fornece informações básicas sobre as licenças disponíveis e quantas estão atribuídas a usuários. As licenças dos dispositivos não são mostradas.

## <a name="connector-status"></a>Status do conector
O status do conector é um ponto único centralizado para examinar o status de todos os conectores disponíveis para o Intune.  

Os conectores são:
- **Conexões configuradas com serviços externos**. Por exemplo, o serviço *Apple Volume Purchase Program* ou o serviço *Windows Autopilot*.  O status desse tipo de conector se baseia na hora da última sincronização bem-sucedida.
- **Certificados ou credenciais necessários para se conectar a um serviço não gerenciado externo**, como certificados *APNs* (Apple Push Notification Service). O status desse tipo de conector se baseia no carimbo de data/hora de expiração do certificado ou da credencial.  

Por padrão, a exibição mostra até cinco conectores. Selecione **Ver todos os conectores** para expandir essa lista e exibir todos os conectores disponíveis, incluindo os conectores não configurados para uso.  

Os conectores não íntegros são sempre exibidos na parte superior da lista. Em seguida, são exibidos os conectores com avisos e, depois, a lista de conectores íntegros. Os conectores que você ainda não configurou são exibidos por último.

Quando há mais de um único conector de qualquer tipo, o status é um resumo de todos esses mesmos conectores. O status menos íntegro de qualquer conector único é usado como a integridade do grupo.  

**Status do conector:**
- **Não íntegro:**
    - O certificado ou a credencial expirou
    - A última sincronização foi há três ou mais dias
- **Aviso:**
    - O certificado ou a credencial expirará dentro de sete dias
    - A última sincronização foi há mais de um dia
- **Íntegro:**
    - O certificado ou a credencial não expirará nos próximos sete dias
    - A última sincronização foi há menos de um dia  

Quando você seleciona um conector na lista, o portal apresenta a página relevante para criar ou configurar esse conector.  Por exemplo, quando você seleciona o conector **Data de Expiração do VPP**, a página **Tokens do Volume Purchase Program do iOS** é aberta, na qual você pode exibir mais detalhes sobre esse conector. Em seguida, você pode criar uma configuração ou editar e corrigir problemas com uma existente.  

## <a name="intune-service-health"></a>Integridade do serviço do Intune  
É possível exibir detalhes de incidentes ativos e avisos sem precisar navegar até o Painel de Integridade do Serviço do Microsoft 365 nem para o Centro de Mensagens, ambos localizados no [centro de administração do Microsoft 365](https://admin.microsoft.com). Somente os incidentes nos quais foi observado um impacto que afetará o locatário são mostrados.  

Quando você seleciona um incidente, os detalhes do incidente são apresentados diretamente na página Status do Locatário. Para exibir avisos e incidentes passados, selecione **Ver Incidentes/Avisos passados**. O centro de administração do Microsoft 365 será aberto e, em seguida, você poderá exibir avisos e incidentes dos últimos 30 dias para seu locatário.  

Para exibir informações da *Integridade do Serviço Intune*, sua conta precisa ter a função **Administrador Global** ou **Administrador de Serviços** no Azure Active Directory ou no centro de administração do Microsoft 365. Para atribuir essas permissões, entre no [Centro de administração do Microsoft 365](https://admin.microsoft.com) com permissões de Administrador Global. Selecione **Usuários > Usuários Ativos** e, em seguida, selecione a conta que exige o acesso. Selecione **Editar** em Funções, *Administrador de Serviços* ou *Administrador Global* e, em seguida, escolha **Salvar** a edição para atribuir as permissões.  

Você só pode configurar as opções de comunicação para a Integridade do Serviço Intune por meio do centro de administração do Microsoft 365.

## <a name="intune-news"></a>Notícias do Intune  
Exiba comunicações informativas da equipe do serviço Intune sem precisar navegar para o Centro de Mensagens do Office. As comunicações incluem mensagens sobre as alterações que ocorreram recentemente no serviço Intune ou que serão feitas em breve em seu locatário.  

Por padrão, as últimas 10 mensagens ativas são exibidas. Para exibir mensagens mais antigas, selecione **Ver mensagens antigas** para abrir o *Centro de Mensagens* no centro de administração do Microsoft 365.  

Para exibir informações das Notícias do Intune, sua conta precisa ter a função **Administrador Global** ou **Administrador de Serviços** no Azure Active Directory ou a função **Leitor do Centro de Mensagens** no centro de administração do Microsoft 365.  Para atribuir essa permissão, entre no [Centro de administração do Microsoft 365](https://admin.microsoft.com) com permissões de administrador. Selecione **Usuários > Usuários Ativos** e, em seguida, selecione a conta que exige o acesso. Selecione **Editar** em *Funções*, *Administrador de Comunicações de Equipes* e, em seguida, escolha **Salvar** a edição para atribuir as permissões.  

Você só pode configurar as opções de comunicação para as Notícias do Intune por meio do centro de administração do Microsoft 365.
