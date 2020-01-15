---
title: Visão geral de cenários guiados
titleSuffix: Microsoft Intune
description: Saiba mais sobre cenários guiados do Intune disponíveis no portal de Gerenciamento de Dispositivo do Microsoft 365.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/09/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b833e5265387637a35bfcdf79f4ae5f37558de61
ms.sourcegitcommit: 637375a390b6e34f9c4415c77b99fe2980bbf554
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/10/2020
ms.locfileid: "75839129"
---
# <a name="intune-guided-scenarios-overview"></a>Visão geral de cenários guiados do Intune 

Um cenário guiado é uma série personalizada de etapas centradas em um caso de uso de ponta a ponta. Cenários comuns são baseados na função que um administrador, usuário ou dispositivo desempenha e sua organização. Essas funções normalmente exigem uma coleção de perfis, configurações, aplicativos e controles de segurança cuidadosamente orquestrados para fornecer as melhores experiência do usuário e segurança.    

Se você não estiver familiarizado com todas as etapas e recursos necessários para implementar um cenário específico do Intune, os cenários guiados poderão ser usados como seu ponto de partida. O cenário guiado montará políticas, aplicativos, atribuições e outras configurações de gerenciamento automaticamente. Além disso, os cenários guiados podem omitir deliberadamente determinadas opções que não são aplicáveis ou incomuns para o cenário fornecido. 

Os cenários guiados não são um espaço de gerenciamento diferente dos fluxos de trabalho normais do Intune. Esses fluxos de trabalho devem ser usados em conjunto com os fluxos de trabalho existentes do Intune para perfis, aplicativos e políticas. Após a conclusão de um cenário guiado, todo o gerenciamento futuro do cenário deve ocorrer em todos os menus existentes para políticas, aplicativos e perfis. Um cenário guiado não salva um tipo de recurso “cenário guiado” ou controla alterações futuras feitas nos recursos. Cada recurso criado por um cenário guiado será exibido na respectiva carga de trabalho. Todas as opções, mesmo as omitidas no cenário guiado, estarão disponíveis para edição nos menus existentes.  

## <a name="types-of-guided-scenarios"></a>Tipos de cenários guiados 

Para simplificar, todos os cenários guiados omitem recursos de escopo complexos, como Marcas de Escopo, grupos de exclusão e atribuições de grupo virtual. Todos os recursos criados por um cenário guiado herdarão cada marca de escopo do administrador que conclui o cenário. Determinados cenários oferecem algum nível de personalização da configuração comum para abranger cenários bem relacionados. Esses cenários dão suporte à atribuição de grupos a apenas grupos de inclusão. Para outros cenários guiados, todo o cenário garante uma experiência consistente sem oferecer nenhuma personalização e gera automaticamente um novo grupo para receber todas as atribuições. Depois que o cenário guiado for concluído, você estará livre para usar atribuições mais sofisticadas diretamente por meio de cargas de trabalho de política, aplicativo e perfil existentes.  

Os cenários a seguir são guiados: 
- Implantar o Microsoft Edge para dispositivos móveis 
- Experimentar um PC gerenciado em nuvem
- Proteger o Microsoft Office para dispositivos móveis 

## <a name="guided-scenario-functionality"></a>Funcionalidade de cenário guiado 

Os cenários guiados oferecem uma funcionalidade específica. Os detalhes a seguir ajudam a explicar o que você pode e não pode fazer ao seguir um cenário guiado.

### <a name="launching"></a>Inicializar  

Todos os cenários guiados estão disponíveis no **[Portal de Gerenciamento de Dispositivo](https://devicemanagement.microsoft.com)**  > **Solução de Problemas + suporte** > **Cenários guiados**. 

O cenário guiado começa com uma introdução que explica a finalidade do cenário e os pré-requisitos necessários para concluir a configuração. Neste ponto, suas permissões de administrador são verificadas quanto a todos os privilégios necessários para concluir o cenário.  

Depois que todas as verificações de pré-requisitos forem aprovadas, o cenário oferecerá configurações adequadas para personalização. O objetivo dos cenários guiados é apenas exigir a entrada do número mínimo de configurações e ocultar configurações incomuns ou avançadas até que seja necessário ou com base em circunstâncias especiais. Cada cenário guiado se vincula a uma documentação que fornece mais detalhes. 

Depois que todas as configurações obrigatórias forem inseridas, o cenário guiado apresentará um resumo das configurações inseridas e dos recursos que o cenário requer. Neste ponto, nada foi salvo, a menos que explicitamente indicado.

A próxima etapa é implantar o cenário. A implantação de um cenário cria e salva todos os recursos necessários e configurações selecionadas. O tempo que leva para uma implantação ser concluída varia de acordo com o cenário. Após a conclusão da implantação, o cenário guiado apresenta uma lista dos recursos criados com links para a exibição de gerenciamento de cada recurso, a carga de trabalho normal do recurso e a documentação. 

> [!IMPORTANT]
> A lista apresentada no fim do cenário guiado não é salva e só pode ser exibida enquanto o cenário guiado está aberto.  
Se houver um erro ao implantar o cenário, todas as alterações serão revertidas. 

### <a name="editing"></a>Editar 

Os cenários guiados não podem ser usados para editar os recursos existentes. Depois de criados, todos os recursos, grupos e atribuições deverão ser editados usando as cargas de trabalho existentes.

### <a name="monitoring"></a>Monitoramento 

Os cenários guiados não podem ser usados para monitorar os recursos existentes além do processo de criação inicial. Depois de criados, todos os recursos, grupos e atribuições deverão ser monitorados usando as cargas de trabalho existentes. 

### <a name="retiring"></a>Desativar 

Os cenários guiados não podem ser usados para desativar recursos existentes, além da limpeza automatizada durante um erro na implantação inicial. Depois de criados, todos os recursos, grupos e atribuições deverão ser desativados usando as cargas de trabalho existentes. 

### <a name="updating"></a>Atualizar

À medida que a tecnologia evolui, o Intune pode atualizar periodicamente um cenário guiado para aprimorar a experiência do usuário, a segurança ou outros aspectos do cenário. Essa atualização afetará apenas as novas implantações feitas pelo cenário guiado. O Intune não atualizará os recursos existentes gerados anteriormente pelo cenário guiado para fazer a correspondência de novas melhores práticas ou recomendações.  

## <a name="next-steps"></a>Próximas etapas

Para começar rapidamente a usar o Microsoft Intune, percorra os cenários guiados do Intune. Se você for novo no Intune, configure o locatário do Intune seguindo o [início rápido de avaliação gratuita](free-trial-sign-up.md).
