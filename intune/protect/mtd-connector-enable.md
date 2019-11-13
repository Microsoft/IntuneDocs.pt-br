---
title: Habilitar o conector do Defesa contra Ameaças Móveis no Microsoft Intune
titleSuffix: Microsoft Intune
description: Habilite o conector entre o parceiro de MTD (Defesa contra Ameaças Móveis) e o Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/17/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dbb6a37e-ba47-4b69-922c-d25e66c279f6
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: fae163cbcd97feb4f333d8ddfd44f2202dd343d6
ms.sourcegitcommit: a4c7339ec9ff5b1b846cb3cca887cf91b5cd4baa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627695"
---
# <a name="enable-the-mobile-threat-defense-connector-in-intune"></a>Habilitar o conector do Defesa contra Ameaças Móveis no Intune

> [!NOTE] 
> Este tópico se aplica a todos os parceiros de Defesa contra Ameaças Móveis.

Durante a instalação do MTD (Defesa contra Ameaças Móveis), você configurou uma política para classificar ameaças em seu console de parceiro do MTD e criou a política de conformidade de dispositivo no Intune. Se já tiver configurado o conector do Intune no console do parceiro MTD, agora você poderá habilitar a conexão do MTD para aplicativos de parceiro MTD.

Quando você integra um novo aplicativo à Defesa contra Ameaças Móveis do Intune e habilita a conexão a essa plataforma, o Intune cria uma política de acesso condicional clássica no Azure Active Directory. Cada aplicativo MTD integrado, como o [Defender ATP](advanced-threat-protection.md) ou um de nossos [parceiros de MTD](mobile-threat-defense.md#mobile-threat-defense-partners) adicionais, cria uma nova política de acesso condicional clássica. Essas políticas podem ser ignoradas, mas não devem ser editadas, excluídas ou desabilitadas.

As políticas de acesso condicional clássicas para aplicativos MTD: 

- São usadas pelo Intune MTD para exigir que os dispositivos sejam registrados no Azure AD, de modo que tenham uma ID de dispositivo, antes de se comunicarem com os parceiros de MTD. A ID é necessária para que os dispositivos possam relatar com êxito seu status ao Intune.  
- Não afeta outros recursos ou aplicativos de nuvem.  
- São diferentes das políticas de acesso condicional que você pode criar para ajudar a gerenciar o MTD.
- Por padrão, não interagem com outras políticas de acesso condicional usadas para avaliação.  

Para exibir as políticas de acesso condicional clássicas, no [Azure](https://portal.azure.com/#home), acesse **Azure Active Directory** > **Acesso Condicional** > **Políticas clássicas**.


## <a name="to-enable-the-mobile-threat-defense-connector"></a>Para habilitar o conector de Defesa contra Ameaças Móveis

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).

4. No **Painel do Intune**, escolha **Conformidade do dispositivo** e, depois, **Defesa contra Ameaças Móveis** na seção **Configuração**.

5. No painel **Defesa contra Ameaças Móveis**, escolha **Adicionar**.

6. Escolha sua solução MTD como o **conector de Defesa contra Ameaças Móveis para configuração** na lista suspensa.

    ![Configuração do MTD no Portal do Azure no Intune](./media/mtd-connector-enable/enable-mtd-connector-1.png)

7. Habilite as opções de alternância de acordo com os requisitos de sua organização. A alternância da visibilidade das opções varia dependendo do parceiro de MTD.

## <a name="mobile-threat-defense-toggle-options"></a>Opções de alternância de Defesa contra Ameaças Móveis

Decida quais opções de alternância de Defesa contra Ameaças Móveis você precisa habilitar de acordo com os requisitos da sua organização. Veja mais detalhes abaixo:

**Configurações de política de conformidade de MDM**
- **Conectar dispositivos Android 4.1 e posteriores ao _\<nome do parceiro de MTD>_** : Ao habilitar essa opção, você poderá fazer com que os dispositivos Android 4.1 e posterior relatem os riscos de segurança novamente ao Intune.
- **Conectar dispositivos iOS 8.0 e posteriores ao _\<nome do parceiro de MTD>_** : Ao habilitar essa opção, você poderá fazer com que dispositivos iOS 8.0 e posterior relatem os riscos de segurança novamente ao Intune.
- **Habilitar a Sincronização de Aplicativos para Dispositivos iOS**: Permite que esse parceiro de Defesa Contra Ameaças Móveis solicite metadados de aplicativos do iOS do Intune para uso para fins de análise de ameaças.
- **Bloquear versões de sistema operacional sem suporte**: Bloqueie se o dispositivo estiver executando um sistema operacional inferior à versão mínima com suporte.

**Configurações de política de proteção de aplicativo**
- **Conecte dispositivos Android versão 4.1 e posteriores ao *\<nome do parceiro de MTD>* para avaliar a política de proteção do aplicativo**: Ao habilitar essa opção, as políticas de proteção do aplicativo que usam a regra de Nível de Ameaça do Dispositivo avaliarão os dispositivos, incluindo os dados desse conector.
- **Conecte dispositivos iOS versão 8.0 e posteriores ao *\<nome do parceiro de MTD>* para avaliar a política de proteção do aplicativo**: Ao habilitar essa opção, as políticas de proteção do aplicativo que usam a regra de Nível de Ameaça do Dispositivo avaliarão os dispositivos, incluindo os dados desse conector.

Para saber mais sobre como usar conectores de Defesa Contra Ameaças Móveis para avaliação da Política de Proteção de Aplicativo do Intune, confira [Configurar a Defesa Contra Ameaças Móveis para dispositivos não registrados](~/protect/mtd-enable-unenrolled-devices.md).

**Configurações compartilhadas comuns**
- **Número de dias até que o parceiro seja considerado sem resposta**: Número de dias de inatividade antes que o Intune considere o parceiro sem resposta devido à perda da conexão. O Intune ignora o estado de conformidade de parceiros de MTD sem resposta.

> [!IMPORTANT] 
> Quando possível, recomendamos que você adicione e atribua os aplicativos MTD antes de criar a conformidade do dispositivo e as regras de política de acesso condicional. Isso ajuda a garantir que o aplicativo MTD esteja pronto e disponível para os usuários finais instalarem antes que possam ter acesso a emails ou outros recursos da empresa.

> [!TIP]
> Veja o **Status da conexão** e o tempo da **Última sincronização** entre o Intune e o parceiro de MTD no painel de Defesa contra Ameaças Móveis.
