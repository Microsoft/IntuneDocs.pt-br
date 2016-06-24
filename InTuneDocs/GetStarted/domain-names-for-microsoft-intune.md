---
# required metadata

title: Nomes de domínio do Microsoft Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: c3c136f0-330d-432a-a91f-16f7dd097e55

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---



# Nomes de domínio do Microsoft Intune

Antes de configurar o Microsoft Intune, examine este tópico e outros requisitos listados em [What to know before you start Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md) (O que saber antes de começar a usar Microsoft Intune).

Quando a sua empresa se inscreve em um serviço baseado em nuvem da Microsoft, como o Intune, você recebe um nome de domínio inicial parecido com o seguinte: **contoso.onmicrosoft.com**. Nesse exemplo, **contoso** é o nome de domínio que você escolheu quando se inscreveu, e **onmicrosoft.com** é o sufixo atribuído às contas que adicionar à sua assinatura. Depois de concluir o processo de inscrição, não será possível alterar esse nome de domínio. No entanto, como um administrador global, você pode adicionar seus próprios nomes de domínio da empresa personalizados para usar com os serviços ou pode remover domínios que já tenham sido adicionados.

Por padrão, ao usar o domínio onmicrosoft, cada usuário importado receberá o sufixo **onmicrosoft.com** para o seu nome UPN.

Para usar um nome de domínio que de sua propriedade em vez do que recebeu na inscrição, você poderá adicionar o nome de domínio ao Azure Active Directory. Depois de adicionar o domínio e de verificar que ele é de sua propriedade, é possível criar contas e grupos que incluam o nome de domínio, alterando os registros de recurso de DNS no seu provedor de hospedagem DNS. Para simplificar o gerenciamento de contas de usuário, ao planejar usar um domínio personalizado, configure um nome de domínio personalizado para sua assinatura antes de começar a sincronizar usuários do Active Directory local.

Configurar nomes de domínio e registros de recursos DNS para o Intune é o mesmo que para outros locatários do Azure Active Directory. Consulte [Add your custom domain name to simplify sign-in using Azure Active Directory (Adicionar nome de domínio personalizado para simplificar a entrada usando o Azure Active Directory)](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/) para obter instruções.

### Consulte também
[O que saber antes de começar a usar o Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md)


<!--HONumber=May16_HO1-->


