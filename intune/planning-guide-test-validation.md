---
title: Teste e validação do Intune
titleSuffix: Microsoft Intune
description: Como testar e validar a solução específica para nuvem do Intune em seu ambiente.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 3/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4f82ee0c-4bd6-4623-9b10-9249d316ccf5
ms.reviewer: jeffbu, cgerth
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7aaeb94aad7e31c3346b088239024c14f9e190da
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2019
ms.locfileid: "67549345"
---
# <a name="intune-testing-and-validation"></a>Teste e validação do Intune

Ao testar a implementação do Microsoft Intune, considere a validação funcional e a validação de caso de uso. A validação funcional consiste em testar cada componente e configuração para determinar se estão funcionando corretamente. A validação de caso de uso envolve testes para verificar se os cenários com uma série de tarefas funcionam como o esperado. 

Recomendamos que você incorpore a equipe de suporte de TI e de assistência técnica na fase de teste para que a documentação de suporte seja criada e a equipe de suporte de TI e de assistência técnica fique satisfeita de dar suporte ao produto. Se um componente ou cenário não funcionar de acordo com os casos de uso, lembre-se de documentar as alterações necessárias e incluir o motivo da alteração.

## <a name="before-you-begin"></a>Antes de começar

Recomendamos que você documente o seguinte:

- **Critérios de teste:** identifique os parâmetros de comparação para a medição.

- **Componentes de design:** deve haver pelo menos um critério de teste.

Se não houver nenhum componente de design em pelo menos um critério de teste alinhado a um requisito ou cenário, considere se o componente de design é necessário ou não. Além disso, garanta que você tem os seguintes itens:

- **Contas:** as contas de teste licenciadas para o EMS e o Office 365 para testar todos os cenários de caso de uso.

- **Dispositivos:** dispositivos que podem ser apagados ou redefinidos para as configurações padrão de fábrica.

- **Componentes de integração:** Todos os componentes de integração (conectores de certificado e o conector local do Intune Exchange) devem ser instalados e configurados se necessário.

Alterações de design podem ser necessárias para a adequação a problemas imprevistos. Além disso, todas as alterações de design devem ser totalmente documentadas com o motivo de cada alteração. Aqui temos um exemplo para ilustrar o que uma alteração poderia ser:

<blockquote>Você percebe que não atende aos requisitos do NDES (Serviço de Registro de Dispositivo de Rede) e também descobre que os perfis de VPN e Wi-Fi podem ser configurados com uma AC raiz, atendendo aos mesmos requisitos sem uma implementação de NDES.</blockquote>

Você pode enfrentar desafios ou problemas que exigem diretrizes técnicas ou uma solução de problemas especializada durante o processo de teste e validação. Recomendamos que você busque assistência por meio dos canais de Suporte da Microsoft.

- [Saiba como obter suporte do Intune](get-support.md)

- [Contatar o suporte telefônico assistido do Microsoft Intune](get-support.md)

## <a name="functional-validation-testing"></a>Teste de validação funcional

A validação funcional consiste em testar cada componente e configuração para determinar se estão funcionando corretamente. Veja um exemplo de teste de validação na tabela abaixo.

![Seção 9 tabela 1](./media/section-9-image-1-table.PNG)

## <a name="use-case-validation-testing"></a>Teste de validação de caso de uso

Realize o teste de validação de caso de uso para verificar se os cenários estão completos e funcionais. Há dois tipos de cenários de caso de uso: administrador de TI e usuário final.

### <a name="it-admin"></a>Administrador de TI

Realize o teste de validação do administrador de TI para validar se ações administrativas executadas em um dispositivo ou usuário funcionam corretamente. Abaixo temos um exemplo de cenário de validação de ponta a ponta do administrador de TI.

![Seção 9 tabela 2](./media/section-9-image-2-table.PNG)

### <a name="end-user"></a>Usuário final

Realize o teste de validação do usuário final para validar se a experiência do usuário final ocorre como esperado e é apresentada corretamente em todas as comunicações com o usuário. É importante validar que a experiência do usuário final está correta. Se você não conseguir validar, isso poderá resultar em reduzir as taxas de adoção e volumes maiores de chamadas de assistência técnica.

![Seção 9 tabela 3](./media/section-9-image-3-table.PNG)

## <a name="next-steps"></a>Próximas etapas

Agora que você testou e validou os cenários de caso de uso e funcionais do Intune, você está pronto para a [distribuição de produção do Intune](planning-guide-rollout-plan.md).

Consulte [recursos adicionais](planning-guide-resources.md) para obter mais informações e modelos de planejamento.
