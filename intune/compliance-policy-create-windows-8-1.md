---
title: Configurações de educação do Windows 8.1 no Microsoft Intune – Azure | Microsoft Docs
description: Ver uma lista de todas as configurações que você pode usar ao definir a conformidade de seus dispositivos Windows 8.1 e Windows Phone 8.1 no Microsoft Intune. Verificar a conformidade no sistema de operacional mínimo e máximo, definir restrições de senha e o comprimento, habilite a criptografia no armazenamento de dados e muito mais.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/04/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4ed863378616f8001beab89177c642404287e7d3
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59424926"
---
# <a name="windows-81-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Configurações do Windows 8.1 para marcar dispositivos como em conformidade ou não conformidade usando o Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Este artigo lista e descreve as configurações de conformidade diferentes que você pode definir em dispositivos Windows 8.1 no Intune. Como parte de sua solução MDM (gerenciamento) do dispositivo móvel, use essas configurações para bloquear senhas simples, defina um mínimo e a versão máxima do SO e muito mais.

Esse recurso aplica-se a:

- Windows Phone 8.1
- Windows 8.1 e posterior

Como um administrador do Intune, use essas configurações de conformidade para ajudar a proteger seus recursos organizacionais. Para saber mais sobre as políticas de conformidade e qualquer pré-requisito, veja a [Introdução às políticas de conformidade do dispositivo](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Antes de começar

[Criar uma política de conformidade](create-compliance-policy.md#create-the-policy). Para **plataforma**, selecione **Windows Phone 8.1** ou **Windows 8.1 e posterior**.

## <a name="device-properties"></a>Propriedades do dispositivo

- **Sistema operacional mínimo exigido**: insira a versão mínima permitida. Quando um dispositivo não atende ao requisito mínimo de versão do sistema operacional, ele será relatado como não compatível. É exibido um link com informações sobre como atualizar. O usuário final pode optar por atualizar seu dispositivo e, depois disso, poderá ter acesso aos recursos da empresa.
- **Versão do sistema operacional máxima permitida**: insira a versão máxima permitida. Quando um dispositivo estiver usando uma versão de sistema operacional inserida na regra, o acesso aos recursos da empresa será bloqueado. O usuário deverá contatar seu administrador de TI. Até que você altere a regra para permitir a versão do SO, este dispositivo não pode ser usado para acessar recursos da empresa.

Computadores com Windows 8.1 retornam a versão **3**. Se a regra de versão do sistema operacional for definida como Windows 8.1 para Windows, então o dispositivo será relatado como não compatível mesmo que o dispositivo tenha o Windows 8.1.

## <a name="system-security"></a>Segurança do sistema

### <a name="password"></a>Senha

- **Exigir uma senha para desbloquear dispositivos móveis**: **exija** que os usuários insiram uma senha antes de acessar o dispositivo.
- **Senhas simples**: defina como **Bloquear** para que os usuários não possam criar uma senha simples como **1234** ou **1111**. Definido como **Não configurado** para permitir que os usuários criem senhas como **1234** ou **1111**.
- **Tamanho mínimo da senha**: insira o número mínimo de dígitos ou de caracteres que a senha deve ter.

  Para dispositivos que executam o Windows e são acessados com uma conta da Microsoft, a política de conformidade não consegue avaliar corretamente:
  - Se o comprimento mínimo da senha tiver mais de oito caracteres
  - Ou se o número mínimo de conjunto de caracteres for maior que dois

- **Tipo de senha**: escolha se uma senha deve ter apenas caracteres **numéricos** ou se deve haver uma combinação de números e outros caracteres (**alfanuméricos**).
  
  - **Número de caracteres não alfanuméricos na senha:** se o **Tipo de senha necessário** for definido como **Alfanumérico**, essa configuração especificará o número mínimo de conjuntos de caracteres que a senha deve conter. Os quatro conjuntos de caracteres são:
    - Letras minúsculas
    - Letras maiúsculas
    - Símbolos
    - Números

    Definir um número mais alto exige que o usuário crie uma senha mais complexa. Para dispositivos que são acessados com uma conta da Microsoft, a política de conformidade não consegue avaliar corretamente:

    - Se o comprimento mínimo da senha tiver mais de oito caracteres
    - Ou se o número mínimo de conjuntos de caracteres for maior que dois

- **Máximo de minutos de inatividade antes que a senha seja exigida**: insira o tempo ocioso antes que o usuário precise digitar novamente a senha.
- **Expiração da senha (dias)**: selecione o número de dias antes que a senha expire e seja preciso criar uma nova.
- **Número de senhas anteriores para evitar a reutilização**: insira o número de senhas usadas anteriormente que não podem ser utilizadas.

### <a name="encryption"></a>Criptografia

- **Exigir criptografia no dispositivo móvel**: **exigir** que o dispositivo seja criptografado para se conectar aos recursos de armazenamento de dados.

Selecione **OK** > **Criar** para salvar suas alterações.

## <a name="next-steps"></a>Próximas etapas

- [Adicionar ações para dispositivos não compatíveis](actions-for-noncompliance.md) e [usar marcas de escopo para políticas de filtro](scope-tags.md).
- [Monitorar suas políticas de conformidade](compliance-policy-monitor.md).
- Consulte a [as configurações de política de conformidade para Windows 10 e posterior](compliance-policy-create-windows.md) dispositivos.