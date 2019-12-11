---
title: Conjuntos de políticas
titleSuffix: Microsoft Intune
description: Use conjuntos de políticas para agrupar coleções de objetos de gerenciamento no Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/15/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: craigma
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e539f44fc9c9b4e7382368c0f3ad9f79bb1c98b1
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72585651"
---
# <a name="use-policy-sets-to-group-collections-of-management-objects"></a>Use conjuntos de políticas para agrupar coleções de objetos de gerenciamento

Os conjuntos de políticas permitem que você crie um pacote de referências para entidades de gerenciamento já existentes que precisam ser identificadas, direcionadas e monitoradas como uma única unidade conceitual. Um conjunto de políticas é uma coleção atribuível de aplicativos, políticas e outros objetos de gerenciamento que você criou. A criação de um conjunto de políticas permite que você selecione muitos objetos diferentes de uma só vez e os atribua em um único lugar. À medida que sua organização muda, você pode revisitar um conjunto de políticas para adicionar ou remover seus objetos e atribuições. Você pode usar um conjunto de políticas para associar e atribuir objetos existentes, como aplicativos, políticas e VPNs em um único pacote. 

> [!IMPORTANT]
> Para obter uma lista de problemas conhecidos relacionados a conjuntos de políticas, confira [Problemas conhecidos de conjuntos de políticas](~/fundamentals/policy-sets.md#policy-sets-known-issues).

Os conjuntos de políticas não substituem conceitos ou objetos existentes. Você pode continuar atribuindo objetos individuais e também pode referenciá-los como parte de um conjunto de políticas. Portanto, as alterações nesses objetos individuais serão refletidas no conjunto de políticas. 

Você pode usar conjuntos de políticas para:

- Agrupar objetos que precisam ser atribuídos em conjunto
- Atribuir os requisitos mínimos de configuração da sua organização em todos os dispositivos gerenciados
- Atribuir os aplicativos mais usados ou relevantes a todos os usuários

Você pode incluir os seguintes objetos de gerenciamento em um conjunto de políticas:
- Aplicativos
- Políticas de configuração de aplicativo
- Políticas de proteção do aplicativo
- Perfis de configuração do dispositivo
- Políticas de conformidade do dispositivo
- Restrições de tipo de dispositivo
- Perfis de implantação do Windows Autopilot
- Página de status de registro

Quando você cria um conjunto de políticas, você cria uma única unidade de atribuição e gerencia associações entre diferentes objetos. Um conjunto de políticas será uma referência a objetos externos a ele. Todas as alterações nos objetos incluídos afetarão o conjunto de políticas também. Depois de criar um conjunto de políticas, você pode exibir e editar seus objetos e atribuições repetidamente. 

> [!NOTE]
> Os conjuntos de políticas dão suporte às configurações do Windows, Android, macOS e iOS e podem receber multiplataforma.

## <a name="how-to-create-a-policy-set"></a>Como criar um conjunto de políticas

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Na folha **Intune**, escolha **Conjuntos de Políticas** > **Conjuntos de políticas** > **Criar**.
3. Na página **Conceitos Básicos**, adicione os seguintes valores:
    - **Nome do conjunto de políticas** – forneça um nome para esse conjunto de políticas.
    - **Descrição** – de maneira opcional, forneça uma descrição para o conjunto de políticas.
   <p>
   <img alt="Create policy set - Basics" src="~/fundamentals/media/policy-sets/policy-sets-01.png">

4. Clique em **Avançar: Gerenciamento de aplicativos**.<br>
   Na página **Gerenciamento de aplicativos**, você pode opcionalmente [adicionar aplicativos](~/apps/apps-add.md), [políticas de configuração de aplicativos](~/apps/app-configuration-policies-overview.md) e [políticas de proteção de aplicativo](~/apps/app-protection-policy.md) ao seu conjunto de políticas. Para obter informações sobre o gerenciamento de aplicativos, confira [O que é o gerenciamento de aplicativos do Microsoft Intune?](~/apps/app-management.md). 
5. Clique em **Avançar: Gerenciamento de dispositivos**.<br>
   A página **Gerenciamento de dispositivos** permite que você adicione objetos de gerenciamento de dispositivos ao conjunto de políticas, como [perfis de configuração de dispositivo](~/configuration/device-profiles.md) e [políticas de conformidade do dispositivo](~/protect/device-compliance-get-started.md). Inclua todos os objetos associados, como outras políticas, certificados e perfis de linha de base de segurança.
6. Clique em **Avançar: Registro de dispositivo**.<br>
   A página **Registro de dispositivo** permite que você adicione objetos de registro de dispositivo ao seu conjunto de políticas, como [restrições de tipo de dispositivo](~/enrollment/enrollment-restrictions-set.md), [perfis de implantação do Windows Autopilot](~/enrollment/enrollment-autopilot.md) e [perfis de página de status de registro](~/enrollment/windows-enrollment-status.md).
7. Clique em **Avançar: Atribuições**.<br>
   A página **Atribuições** permite que você possa atribuir o conjunto de políticas a usuários e dispositivos. É importante observar que você pode atribuir um conjunto de políticas a um dispositivo seja ou não esse dispositivo gerenciado pelo Intune.
8. Clique em **Avançar: Examinar + criar** para examinar os valores que você inseriu para o perfil.
9. Quando terminar, clique em **Criar** para criar o conjunto de políticas no Intune. 

## <a name="policy-sets-known-issues"></a>Problemas conhecidos de conjuntos de políticas

Os conjuntos de políticas, novos na versão 1910, têm os seguintes problemas conhecidos.

- Ao criar um conjunto de políticas, se um administrador com escopo tentar criar um conjunto de políticas sem nenhuma marca de escopo selecionada, ao acessar a página **Examinar + Criar**, a validação falhará e um erro será exibido na barra de status. O administrador deve mudar para uma página diferente no processo e retornar para a página **Examinar + Criar**. Isso habilitará a opção **Criar**.  
 
- No momento, há suporte para os seguintes tipos de aplicativo em conjuntos de políticas:
    - Aplicativo da loja iOS
    - Aplicativo de linha de negócios iOS
    - Aplicativo de linha de negócios iOS gerenciado
    - Aplicativos da loja Android
    - Aplicativo de linha de negócios Android
    - Aplicativo de linha de negócios Android gerenciado
    - Office 365 ProPlus Suite (Windows 10)
    - Link da Web
    - Aplicativo iOS interno
    - Aplicativo interno Android

- Não há suporte para a definição de uma atribuição de conjunto de políticas de **Todos os Usuários** como **Perfil do Autopilot**.

- Os conjuntos de políticas têm as seguintes restrições de registro e problemas de ESP (Página de Status de Registro):
    - As restrições e a ESP não dão suporte a atribuições de grupo virtual.
    - As restrições e a ESP não dão estritamente suporte a atribuições de grupo de exclusão. 
    - As restrições e a ESP usam resolução de conflitos com base em prioridade. As restrições e a ESP poderão não ser aplicadas aos mesmos usuários que o restante de payloads de um conjunto de políticas se as Restrições e a ESP também forem direcionadas por Restrições e a ESP de prioridade mais alta.
    - As Restrições e a ESP padrão não podem ser adicionadas a um conjunto de políticas.

- Os tipos de política de MAM que dão suporte a conjuntos de políticas incluem o seguinte: 
    - Proteção de aplicativo gerenciado direcionado a MDM para WIP (Windows) de MAM 
    - Proteção de aplicativo gerenciado direcionado para iOS de MAM
    - Proteção de aplicativo gerenciado direcionado para Android de MAM
    - Configuração de aplicativos gerenciados direcionados para iOS de MAM
    - Configuração de aplicativos gerenciados direcionados para Android de MAM

- Os tipos de política de MAM que não dão suporte a conjuntos de políticas incluem o seguinte: 
    - Proteção de aplicativo gerenciado direcionado para WIP (Windows) de MAM

- A política de processos de MAM definem as atribuições como atribuições diretas para os seguintes tipos de política:
    - Proteção de aplicativo gerenciado direcionado para iOS de MAM
    - Proteção de aplicativo gerenciado direcionado para Android de MAM
    - Configuração de aplicativos gerenciados direcionados para iOS de MAM
    - Configuração de aplicativos gerenciados direcionados para Android de MAM

    Se uma política fosse adicionada a um conjunto de políticas implantado em um grupo, o grupo seria exibido como atribuído diretamente na carga de trabalho, não "atribuído por meio do conjunto de políticas". Como um resultado disso, o MAM não processa exclusões de atribuição de grupo de conjuntos de políticas.

- O MAM não dá suporte à implantação para grupos virtuais **Todos os Usuários** e **Todos os Dispositivos** para tipos de política.

## <a name="next-steps"></a>Próximas etapas

- [Registrar dispositivos no Microsoft Intune](~/enrollment/index.yml).