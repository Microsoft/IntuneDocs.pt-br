---
title: Categorizar dispositivos com o mapeamento de grupos de dispositivos
description: "Use o mapeamento do grupo de dispositivos do Microsoft Intune para agrupar dispositivos em categorias que você define para facilitar o gerenciamento desses dispositivos."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8b8c06a3-6b6c-4cf1-8646-b24fa9b1a39e
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d6783f0dbf21d8bb1e652522df7ae1f37cbf4ffd
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2017
---
# <a name="categorize-devices-with-device-group-mapping-in-microsoft-intune"></a>Categorize os dispositivos com o mapeamento do grupo de dispositivos no Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Use o **mapeamento do grupo de dispositivos** do Microsoft Intune para adicionar dispositivos aos grupos automaticamente, com base nas categorias que você definir para facilitar o gerenciamento desses dispositivos. 

O mapeamento do grupo de dispositivos usa o seguinte fluxo de trabalho:
1. Crie categorias para os usuários escolherem quando registrarem seus dispositivos
2. Crie grupos ou use grupos existentes para cada categoria que você deseja usar. De acordo com a versão do Intune que você está usando, tais grupos serão do Intune ou grupos de segurança do Azure Active Directory.
2. Você configura as regras que mapeiam a categoria escolhida para o grupo de dispositivos que você criou.
3. Quando os usuários finais de dispositivos iOS e Android registram seus dispositivos, eles devem escolher uma categoria na lista de categorias configuradas. Para atribuir uma categoria a um dispositivo Windows, os usuários finais devem usar o site do Portal da Empresa (consulte **Depois de configurar os grupos de dispositivos** neste tópico para obter mais detalhes).
4. Depois, é possível implantar políticas e aplicativos nesses grupos.

Você pode criar as categorias de dispositivo que desejar, por exemplo:
* Dispositivo de ponto de venda
* Dispositivo de demonstração
* Vendas
* Contabilização
* Manager

## <a name="important-information-about-a-change-in-group-management-for-intune"></a>Informações importantes sobre uma alteração no gerenciamento de grupos para o Intune

Com base nos seus comentários, estamos unificando a experiência de agrupamento e direcionamento no Enterprise Mobility + Security. Por esse motivo, em breve converteremos os grupos do Intune em grupos de segurança baseados no Azure Active Directory. Após essa alteração, você não criará grupos usando o Intune novamente. Em vez disso, você poderá criá-los no portal do Azure. Essa alteração ocorrerá de forma gradual e você pode ler os detalhes completos e a linha do tempo [neste tópico](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).

### <a name="which-procedure-in-this-topic-should-you-use-to-configure-device-group-mapping"></a>Qual procedimento deste tópico você deve usar para configurar o mapeamento de grupo de dispositivos?

Em virtude da implementação faseada dos grupos de segurança do Azure Active Directory, você deve abrir o espaço de trabalho **Grupos** no [console de administração do Intune](https://manage.microsoft.com) para identificar o procedimento a se usar:

-  Se um link para o portal do Azure for exibido, você não está mais usando os grupos do Intune. Siga o procedimento [Como configurar o mapeamento do grupo de dispositivos para grupos do Azure Active Directory](/intune-classic/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune#how-to-configure-device-group-mapping-for-azure-active-directory-groups) abaixo.
-  Se um link para o portal do Azure não for exibido, você ainda está usando os grupos do Intune. Siga o procedimento [Como configurar o mapeamento do grupo de dispositivos para grupos do Intune](/intune-classic/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune#how-to-configure-device-group-mapping-for-intune-groups) abaixo.

## <a name="how-to-configure-device-group-mapping-for-intune-groups"></a>Como configurar o mapeamento do grupo de dispositivos para grupos do Intune
1. Para cada categoria de dispositivos que você deseja usar, crie um grupo de dispositivos do Intune ou identifique um grupo existente. Para obter informações sobre como criar grupos, consulte [Use groups to manage users and devices with Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md) (Usar grupos para gerenciar usuários e dispositivos com o Microsoft Intune).
2. No [Console de administração do Microsoft Intune](https://manage.microsoft.com), selecione **Administrador**.
3. No espaço de trabalho **Administração**, expanda o **Gerenciamento de Dispositivo Móvel** e escolha **Mapeamento do Grupo de Dispositivos**.
4. Na página **Mapeamento do Grupo de Dispositivos**, habilite o mapeamento do grupo de dispositivos.
5. Escolha **Adicionar** para criar uma nova regra de mapeamento.
6. Na caixa de diálogo **Add device group mapping rule** (Adicionar regra de mapeamento do grupo de dispositivos), digite o nome da categoria que você deseja criar e, na lista suspensa, escolha a coleção de dispositivos para a qual você deseja mapear essa categoria. Escolha **Adicionar** depois de concluir.
7. Quando terminar de adicionar categorias e grupos, escolha **Salvar**.



## <a name="how-to-configure-device-group-mapping-for-azure-active-directory-groups"></a>Como configurar o mapeamento do grupo de dispositivos para grupos do Azure Active Directory

### <a name="step-1---create-device-categories-in-the-intune-administration-console"></a>Etapa 1 – Criar categorias de dispositivo no console de administração do Intune
1. No [Console de administração do Microsoft Intune](https://manage.microsoft.com), selecione **Administrador**.
3. No espaço de trabalho **Administração**, expanda o **Gerenciamento de Dispositivo Móvel** e escolha **Categorias de Dispositivo**.
4. Na página **Categorias de Dispositivo**, será exibida uma lista na qual você poderá configurar categorias de dispositivo: 
- Você pode digitar um nome e clicar em **Adicionar**, para adicioná-la como uma nova categoria de dispositivo.
- Além disso, você pode selecionar uma categoria e a **Excluir** em seguida.

Você usará o nome da categoria do dispositivo quando criar grupos de segurança do Azure Active Directory na etapa 2.

### <a name="step-2---create-azure-active-directory-security-groups"></a>Etapa 2 – Criar grupos de segurança do Azure Active Directory

Nesta etapa, você criará grupos dinâmicos no portal do Azure com base na categoria do dispositivo e no nome da categoria do dispositivo.

Para continuar, consulte o tópico [Usar atributos para criar regras avançadas](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) na documentação do Azure Active Directory.
Use as informações desse tópico para criar um grupo de dispositivos com uma regra avançada usando o atributo **deviceCategory**.
Por exemplo, (**dispositivo.Categoriadodispositivo -eq** ”<*nome da categoria do dispositivo obtido no console de administração do Intune*>”)


## <a name="after-you-configure-device-groups"></a>Depois de configurar os grupos de dispositivos

Quando os usuários finais de dispositivos iOS e Android registram seus dispositivos, eles devem escolher uma categoria na lista de categorias configuradas. Depois que eles escolherem uma categoria e concluírem o registro, o dispositivo será adicionado ao grupo de dispositivos do Intune ou ao grupo de segurança do Active Directory que corresponde à categoria escolhida.

Para atribuir uma categoria a um dispositivo Windows, os usuários finais devem usar o site do Portal da Empresa (portal.manage.microsoft.com) após o registro do dispositivo. Em um dispositivo Windows, acesse o site e, em seguida, **Menu** > **Meus Dispositivos**. Escolha um dispositivo registrado listado na página e, depois, selecione uma categoria. 

Depois de escolher uma categoria, o dispositivo é adicionado automaticamente ao grupo correspondente que você criou. Se um dispositivo já estiver registrado antes da configuração de categorias, o usuário final verá uma notificação sobre o dispositivo no site do Portal da Empresa e deverá selecionar uma categoria na próxima vez que acessar o aplicativo do Portal da Empresa no iOS ou no Android.



### <a name="see-also"></a>Consulte também
[Usar grupos para gerenciar usuários e dispositivos com o Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)
