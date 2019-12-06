---
title: Habilitar o conector do Defesa contra Ameaças Móveis no Microsoft Intune
titleSuffix: Microsoft Intune
description: Habilite o conector entre o parceiro de MTD (Defesa contra Ameaças Móveis) e o Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/19/2019
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
ms.openlocfilehash: b8243ae4014660a76c6327afd9c970ce8a9eae58
ms.sourcegitcommit: 960ffb2214c35d75ad219fa2571a999529a0abd4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2019
ms.locfileid: "74478842"
---
# <a name="enable-the-mobile-threat-defense-connector-in-intune"></a>Habilitar o conector do Defesa contra Ameaças Móveis no Intune

Durante a instalação da MTD (Defesa contra Ameaças Móveis), foi configurada uma política para classificar ameaças em seu console do parceiro de Defesa contra Ameaças Móveis e criada a política de conformidade com o dispositivo no Intune. Se já tiver configurado o conector do Intune no console do parceiro MTD, agora você poderá habilitar a conexão do MTD para aplicativos de parceiro MTD.

> [!NOTE]
> Este tópico se aplica a todos os parceiros de Defesa contra Ameaças Móveis.

## <a name="classic-conditional-access-policies-for-mtd-apps"></a>As políticas de acesso condicional clássicas para aplicativos MTD

Quando você integra um novo aplicativo à Defesa contra Ameaças Móveis do Intune e habilita a conexão a essa plataforma, o Intune cria uma política de acesso condicional clássica no Azure Active Directory. Cada aplicativo MTD integrado, como o [Defender ATP](advanced-threat-protection.md) ou um de nossos [parceiros de MTD](mobile-threat-defense.md#mobile-threat-defense-partners) adicionais, cria uma nova política de acesso condicional clássica. Essas políticas podem ser ignoradas, mas não devem ser editadas, excluídas nem desabilitadas.

Se a política clássica for excluída, será necessário excluir a conexão com o Intune responsável por sua criação e configurá-la novamente. Esse processo recria a política clássica. Não há suporte para a migração de políticas clássicas para aplicativos MTD para o novo tipo de política de acesso condicional.

As políticas de acesso condicional clássicas para aplicativos MTD:

- São usadas pelo Intune MTD para exigir que os dispositivos sejam registrados no Azure AD, de modo que tenham uma ID de dispositivo, antes de se comunicarem com os parceiros de MTD. A ID é necessária para que os dispositivos possam relatar com êxito seu status ao Intune.

- Não afeta outros recursos ou aplicativos de nuvem.

- São diferentes das políticas de acesso condicional que você pode criar para ajudar a gerenciar o MTD.

- Por padrão, não interagem com outras políticas de acesso condicional usadas para avaliação.

Para exibir as políticas de acesso condicional clássicas, no [Azure](https://portal.azure.com/#home), acesse **Azure Active Directory** > **Acesso Condicional** > **Políticas clássicas**.

## <a name="to-enable-the-mobile-threat-defense-connector"></a>Para habilitar o conector de Defesa contra Ameaças Móveis

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecione **Administração de locatários** > **Conectores e tokens** > **Defesa contra Ameaças Móveis**.

3. No painel **Defesa contra Ameaças Móveis**, selecione **Adicionar**.

4. Para **configurar o conector de Defesa contra Ameaças Móveis**, selecione a solução MTD na lista suspensa.

5. Habilite as opções de alternância de acordo com os requisitos de sua organização. A alternância da visibilidade das opções varia dependendo do parceiro de MTD.  Por exemplo, a imagem a seguir mostra as opções disponíveis para o Symantec Endpoint Protection:

   ![Configuração do MTD no Portal do Azure no Intune](./media/mtd-connector-enable/enable-mtd-connector-1.png)

## <a name="mobile-threat-defense-toggle-options"></a>Opções de alternância de Defesa contra Ameaças Móveis

Decida quais opções de alternância do MTD você precisa habilitar de acordo com os requisitos da sua organização. Nem todas as opções a seguir têm suporte de todos os parceiros da Defesa contra Ameaças Móveis:

**Configurações de política de conformidade de MDM**

- **Conecte dispositivos Android da versão _\<versões compatíveis>_ ao _\<nome do parceiro MTD>_** : Ao habilitar essa opção, você poderá fazer com que os dispositivos Android 4.1 e posterior relatem os riscos de segurança novamente ao Intune.

- **Conecte dispositivos iOS da versão _\<versões compatíveis>_ ao _\<nome do parceiro MTD>_** : Ao habilitar essa opção, você poderá fazer com que dispositivos iOS 8.0 e posterior relatem os riscos de segurança novamente ao Intune.

- **Habilitar a Sincronização de Aplicativos para Dispositivos iOS**: Permite que esse parceiro de Defesa Contra Ameaças Móveis solicite metadados de aplicativos do iOS do Intune para uso para fins de análise de ameaças.

- **Bloquear versões de sistema operacional sem suporte**: Bloqueie se o dispositivo estiver executando um sistema operacional inferior à versão mínima com suporte.

**Configurações de política de proteção de aplicativo**

- **Conecte dispositivos Android da versão *\<versões compatíveis>*  ao *\<nome do parceiro MTD>* para avaliação da política de proteção de aplicativos**: Ao habilitar essa opção, as políticas de proteção do aplicativo que usam a regra de Nível de Ameaça do Dispositivo avaliarão os dispositivos, incluindo os dados desse conector.

- **Conecte dispositivos iOS da versão *\<versões compatíveis>*  ao *\<nome do parceiro MTD>* para avaliação da política de proteção de aplicativos**: Ao habilitar essa opção, as políticas de proteção do aplicativo que usam a regra de Nível de Ameaça do Dispositivo avaliarão os dispositivos, incluindo os dados desse conector.

Para saber mais sobre como usar conectores de Defesa Contra Ameaças Móveis para avaliação da Política de Proteção de Aplicativo do Intune, confira [Configurar a Defesa Contra Ameaças Móveis para dispositivos não registrados](~/protect/mtd-enable-unenrolled-devices.md).

**Configurações compartilhadas comuns**

- **Número de dias até que o parceiro seja considerado sem resposta**: Número de dias de inatividade antes que o Intune considere o parceiro sem resposta devido à perda da conexão. O Intune ignora o estado de conformidade de parceiros de MTD sem resposta.

> [!IMPORTANT]
> Quando possível, recomendamos que você adicione e atribua os aplicativos MTD antes de criar a conformidade do dispositivo e as regras de política de acesso condicional. Isso ajuda a garantir que o aplicativo MTD esteja pronto e disponível para os usuários finais instalarem antes que possam ter acesso a emails ou outros recursos da empresa.

> [!TIP]
> Veja o **Status da conexão** e o tempo da **Última sincronização** entre o Intune e o parceiro de MTD no painel de Defesa contra Ameaças Móveis.

## <a name="next-steps"></a>Próximas etapas

- [Criar uma política de proteção de aplicativo com MTD (Defesa contra Ameaças Móveis) com o Intune](~/protect/mtd-app-protection-policy.md).
