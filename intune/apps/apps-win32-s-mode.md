---
title: Habilitar aplicativos Win32 em dispositivos de modo S
titleSuffix: Microsoft Intune
description: Saiba como habilitar aplicativos Win32 em dispositivos de modo S usando o Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/13/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d2ab21321b171c8fe8f5f9dab3032507c0e740cf
ms.sourcegitcommit: 78cebd3571fed72a3a99e9d33770ef3d932ae8ca
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74059765"
---
# <a name="enable-win32-apps-on-s-mode-devices"></a>Habilitar aplicativos Win32 em dispositivos de modo S

[O modo S do Windows 10](https://docs.microsoft.com/windows/deployment/s-mode) é um sistema operacional bloqueado que só executa aplicativos da Store. Por padrão, os dispositivos de modo S do Windows não permitem a instalação e a execução de aplicativos Win32. Esses dispositivos incluem uma única *política de base do Win 10S*, que bloqueia a execução de qualquer aplicativo Win32 no dispositivo de modo S. No entanto, ao criar e usar uma **política complementar do modo S** no Intune, você pode instalar e executar aplicativos Win32 em dispositivos gerenciados de modo S do Windows 10. Com as ferramentas do PowerShell de [WDAC (Controle de Aplicativos do Microsoft Defender)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control), é possível criar uma ou mais políticas complementares para o modo S do Windows. Você deve assinar as políticas complementares com o [DGSS (Serviço de Autenticação do Device Guard)](https://go.microsoft.com/fwlink/?linkid=2095629) ou com [SignTool.exe](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/signing-policies-with-signtool) e, em seguida, carregar e distribuir as políticas por meio do Intune. Como alternativa, você pode assinar as políticas complementares com um certificado de assinatura de código da sua organização, no entanto, o método preferencial é usar DGSS. Na instância em que você usa o certificado de assinatura de código da sua organização, o certificado raiz ao qual o certificado de assinatura de código se encadeia deve estar presente no dispositivo.

Ao atribuir a política complementar do modo S no Intune, você permite que o dispositivo faça uma exceção à política de modo S existente no dispositivo, autorizando o catálogo de aplicativos assinados correspondente carregado. A política define uma lista de permissões de aplicativos (o catálogo de aplicativos) que podem ser usados no dispositivo de modo S.

> [!NOTE]
> Os aplicativos Win32 em dispositivos de modo S têm suporte apenas na atualização de novembro de 2019 do Windows 10 (build 18363) ou em versões posteriores.

<!-- Add WDAC tooling diagram  -->

As etapas para permitir que os aplicativos Win32 sejam executados em um dispositivo Windows 10 no modo S são as seguintes:

1. Habilite dispositivos de modo S por meio do Intune como parte do processo de registro do Windows 10 S.
2. Crie uma política complementar para permitir aplicativos Win32:
   - Você pode usar ferramentas de [WDAC (Controle de Aplicativos do Microsoft Defender)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control) para criar uma política complementar. A ID da política de base na política deve corresponder à ID da política de base do modo S (que é embutida em código no cliente). Além disso, garanta que a versão da política seja posterior à versão anterior.
   - Use DGSS para assinar a política complementar. Para obter mais informações, confira [Assinar política de integridade de código com assinatura do Device Guard](https://docs.microsoft.com/microsoft-store/sign-code-integrity-policy-with-device-guard-signing).
   - Carregue a política complementar assinada no Intune criando uma política complementar do modo S do Windows 10 (veja abaixo).
3. Permita os catálogos de aplicativos Win32 por meio do Intune:
   - Crie os arquivos de catálogo (1 para cada aplicativo) e os assine usando DGSS ou outra infraestrutura de certificado.
   - Empacote o catálogo assinado no arquivo *.intunewin* usando a [Ferramenta de Preparação de Conteúdo do Microsoft Win32](https://go.microsoft.com/fwlink/?linkid=2065730). Para obter mais informações, confira [Gerenciamento de aplicativo Win32 – preparar o conteúdo do aplicativo Win32 para carregar](~/apps/apps-win32-app-management.md#prepare-the-win32-app-content-for-upload).
   - O Intune aplica o catálogo de aplicativos assinado para instalar o aplicativo Win32 no dispositivo de modo S usando a [Extensão de Gerenciamento do Intune](~/apps/intune-management-extension.md).

> [!NOTE]
> Os pacotes de LOB (linhas de negócios) `.appx` e `.appx` no modo S do Windows 10 terão suporte por meio da assinatura do MSFB (Microsoft Store para Empresas).
>
> **A política complementar do modo S** para aplicativos deve ser fornecida por meio da Extensão de Gerenciamento do Intune.
>
> As políticas de modo S são impostas no nível do dispositivo. Várias políticas de destino serão mescladas no dispositivo. A política mesclada será imposta no dispositivo.

Para criar uma política complementar do modo S do Windows 10, use as seguintes etapas:

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. No painel do **Intune**, selecione **Aplicativos cliente** > **Políticas complementares do modo S** > **Criar política**.
3. Antes de adicionar o **Arquivo de política**, você deve criá-lo e assiná-lo. Para obter mais informações, consulte:
    - [Criar uma política de WDAC usando as ferramentas do PowerShell e convertê-la em um formato binário](https://go.microsoft.com/fwlink/?linkid=2095387)
    - [Assinar usando o Serviço de Autenticação do Device Guard](https://go.microsoft.com/fwlink/?linkid=2095629) **(recomendado)**

4. Na página **Conceitos Básicos**, adicione os seguintes valores:

    | Valor | Descrição |
    |--------------|------------------------------------------------|
    | Arquivo de política | O arquivo que contém a política de WDAC. |
    | Nome | O nome da política. |
    | Descrição | [Opcional] A descrição da política. |

5. Clique em **Avançar: Marcas de escopo**.<br>
   Na página **Marcas de escopo**, você pode configurar opcionalmente marcas de escopo para determinar quem pode ver a política de aplicativo no Intune. Saiba mais sobre marcas de escopo em [Usar controle de acesso baseado em função e marcas de escopo para TI distribuída](~/fundamentals/scope-tags.md).

6. Clique em **Avançar: Atribuições**.<br>
   A página **Atribuições** permite que você atribua a política aos usuários e dispositivos. É importante observar que você pode atribuir uma política a um dispositivo, seja ou não gerenciado pelo Intune.
7. Clique em **Avançar: Examinar + criar** para examinar os valores que você inseriu para o perfil.
8. Quando terminar, clique em **Criar** para criar a política complementar do modo S no Intune. 

Depois que a política for criada, você a verá adicionada à lista de políticas complementares do modo S no Intune. Assim que a política é atribuída, ela é implantada nos dispositivos. Você deve implantar o aplicativo no mesmo grupo de segurança da política complementar. Você pode começar a direcionar e atribuir aplicativos a esses dispositivos. Isso permitirá que os usuários finais instalem e executem os aplicativos nos dispositivos de modo S.

## <a name="removal-of-s-mode-policy"></a>Remoção da política de modo S

No momento, para remover a política suplementar do modo S do dispositivo, você deve atribuir e implantar uma política vazia para substituir a política complementar existente.

## <a name="policy-reporting"></a>Relatório de política

A política complementar do modo S, que é imposta no nível do dispositivo, tem apenas relatórios no nível do dispositivo. Os relatórios no nível do dispositivo estão disponíveis para condições de erro e sucesso. 

Valores de relatório que são mostrados no console do Intune para as políticas de relatórios do modo S:
- **Êxito**: a política complementar do modo S está em vigor.
- **Desconhecido**: o status da política complementar do modo S não é conhecido.
- **TokenError**: a política complementar do modo S está estruturalmente correta, mas há um erro na autorização do token.
- **NotAuthorizedByToken**: o token não autoriza essa política complementar do modo S.
- **PolicyNotFound**: a política complementar do modo S não foi encontrada.

## <a name="next-steps"></a>Próximas etapas

- Para obter mais informações, confira [Aplicativos Win32 no modo S](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/lob-win32-apps-on-s).
- Para obter mais informações sobre como adicionar aplicativos ao Intune, confira [Adicionar aplicativos ao Microsoft Intune](apps-add.md).
- Para obter mais informações sobre aplicativos Win32, confira [Gerenciamento de aplicativos Win32 do Intune](~/apps/apps-win32-app-management.md).
