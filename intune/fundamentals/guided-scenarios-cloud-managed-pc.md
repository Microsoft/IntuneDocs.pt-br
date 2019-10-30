---
title: Cenário guiado – Área de Trabalho Moderna gerenciada em nuvem
titleSuffix: Microsoft Intune
description: Saiba mais sobre o cenário guiado para configurar uma Área de Trabalho Moderna no portal de Gerenciamento de Dispositivo do Microsoft 365.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b3372fc83e467b08b479490b3707f2be03409156
ms.sourcegitcommit: c2e62f1ebdf75599c8e544287123c602f0f15f2b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72749327"
---
# <a name="guided-scenario---cloud-managed-modern-desktop"></a>Cenário guiado – Área de Trabalho Moderna gerenciada em nuvem

A área de trabalho moderna é a plataforma de produtividade de ponta do Operador de Informações. O Office 365 ProPlus e o Windows 10 são os principais componentes da área de trabalho moderna, juntamente com as linhas de base de segurança mais recentes para Windows 10 e para a Proteção Avançada contra Ameaças do Windows Defender. 

O gerenciamento da área de trabalho moderna da nuvem traz o benefício adicional de ações remotas de toda a Internet. O gerenciamento de nuvem utiliza as políticas internas do Gerenciamento de Dispositivo Móvel do Windows e remove as dependências na política de grupo local do Active Directory. 

Se desejar avaliar uma área de trabalho moderna gerenciada pela nuvem em sua própria organização, esse cenário guiado predefinirá todas as configurações necessárias para uma implantação básica. Neste cenário guiado, você criará um ambiente seguro no qual poderá experimentar as funcionalidades de gerenciamento de dispositivos do Intune. 

## <a name="prerequisites"></a>Pré-requisitos
- [Definir a autoridade MDM como Intune](~/fundamentals/mdm-authority-set.md#set-mdm-authority-to-intune) – A configuração de autoridade MDM (gerenciamento de dispositivo móvel) determina como você gerencia seus dispositivos. Como administrador de TI, você deverá definir uma autoridade MDM antes que os usuários possam registrar dispositivos para gerenciamento.
- M356 E3 mínimo (ou M365 E5 para ter a melhor segurança)
- Dispositivo Windows 10 1903 (registrado com o Windows Autopilot para obter a melhor experiência do usuário final)
- Permissões de administrador do Intune necessárias para concluir este cenário guiado:
  - Configuração do dispositivo Leitura, Criação, Exclusão, Atribuição e Atualização
  - Programas de Registro Leitura de dispositivo, Leitura de perfil, Criação de perfil, Atribuição de perfil e Exclusão de perfil
  - Aplicativos móveis Leitura, Criação, Exclusão, Atribuição e Atualização
  - Organização Leitura e Atualização
  - Linhas de Base de Segurança Leitura, Criação, Exclusão, Atribuição e Atualização
  - Conjuntos de Políticas Leitura, Criação, Exclusão, Atribuição e Atualização

## <a name="step-1---introduction"></a>Etapa 1 – Introdução

Usando esse cenário guiado, você configurará um usuário de teste, registrará um dispositivo no Intune e implantará o dispositivo com configurações recomendadas pelo Intune, assim como Windows 10 e Office ProPlus. Seu dispositivo também será configurado para a Proteção Avançada contra Ameaças do Microsoft Defender se você optar por [habilitar essa proteção no Intune](~/protect/advanced-threat-protection.md#enable-microsoft-defender-atp-in-intune). O usuário que você configurar e o dispositivo que você registrar serão adicionados a novos grupos de segurança e definidos com as configurações recomendadas para segurança e produtividade. 

### <a name="what-you-will-need-to-continue"></a>Do que você precisará para continuar

Você deve fornecer o dispositivo e o usuário de teste neste cenário guiado. Conclua as seguintes tarefas:
- Configurar uma conta de usuário de teste no Azure Active Directory.
- Criar um dispositivo de teste que executa Windows 10, versão 1903 ou posteriores.
- (Opcional) [Registrar o dispositivo de teste no Windows Autopilot](~/enrollment/enrollment-autopilot.md#add-devices).
- (Opcional) Habilitar a [identidade visual para a página de entrada do Azure Active Directory de sua organização](https://go.microsoft.com/fwlink/?linkid=2102455).

## <a name="step-2---user"></a>Etapa 2 – Usuário

Escolha um usuário para configurar no dispositivo. A pessoa será o usuário primário do dispositivo.

Se desejar adicionar mais usuários ou dispositivos a essa configuração, adicione os usuários e dispositivos aos grupos de segurança do AAD gerados pelo assistente. Diferentemente de outros Cenários Guiados, você não precisa executar o assistente mais de uma vez, pois a configuração não é personalizável. Basta adicionar mais usuários e dispositivos aos grupos do AAD criados. Após concluir o assistente, você poderá exibir o grupo gerado com as políticas recomendadas implantadas. 

## <a name="step-3---device"></a>Etapa 3 – Dispositivo

Verifique se seu dispositivo está executando o Windows 10, versão 1903 ou posteriores.  O usuário primário precisará configurar o dispositivo quando o receber. Há duas opções de configuração disponíveis para o usuário. 

### <a name="option-a--windows-autopilot"></a>Opção A – Windows Autopilot
O Windows Autopilot automatiza a configuração de novos dispositivos para que os usuários possam configurá-los para uso imediato, sem assistência de TI. Se o dispositivo já estiver registrado no Windows Autopilot, selecione-o por seu número de série. Para obter mais informações sobre como usar o Windows Autopilot, confira [Registrar dispositivo no Windows Autopilot (Opcional)](~/fundamentals/guided-scenarios-cloud-managed-pc.md#register-device-with-windows-autopilot-optional).

### <a name="option-b--manual-device-enrollment"></a>Opção B – Registro manual do dispositivo
Os usuários configurarão e registrarão manualmente seus novos dispositivos no gerenciamento de dispositivo móvel. Após concluir este cenário, redefina o dispositivo e forneça ao usuário primário as instruções de registro para dispositivos Windows. Para obter mais informações, confira [Ingressar um dispositivo Windows 10 no Azure AD durante a experiência de primeira execução](https://docs.microsoft.com/azure/active-directory/devices/azuread-joined-devices-frx#joining-a-device).

## <a name="step-4---review--create"></a>Etapa 4 – Examinar + criar

A etapa final permite que você examine um resumo das configurações que você definiu. Após examinar suas escolhas, clique em **Implantar** para concluir o cenário guiado. Depois que o cenário guiado estiver concluído, uma tabela de recursos será exibida. Você pode editar esses recursos posteriormente. No entanto, depois que você sair da exibição de resumo, a tabela não será salva.

> [!IMPORTANT]
> Depois que o cenário guiado estiver concluído, ele exibirá um resumo. Você pode modificar os recursos listados no resumo posteriormente. No entanto, a tabela que exibe esses recursos não será salva.

### <a name="verification"></a>Verificação
1. Verificar se o que foi selecionado é o escopo de usuário MDM atribuído
    - Verifique se o [Escopo de Usuário MDM](~/enrollment/windows-enroll.md#enable-windows-10-automatic-enrollment) está:
        - Definido como **Todos** para o aplicativo do **Microsoft Intune** ou,
        - Definido como **Alguns**. Além disso, adicione o grupo de usuários criado por este cenário guiado.
2. Verifique se o usuário selecionado pode ingressar dispositivos no Azure Active Directory.
    - Verifique se o ingresso no AAD está:
        - Definido como **Todos** ou,
        - Definido como **Alguns**. Além disso, adicione o grupo de usuários criado por este cenário guiado.
3. Siga as etapas apropriadas no dispositivo para ingressá-lo no Azure AD com base no seguinte:
    - Com Autopilot. Para obter mais informações, confira [Modo controlado pelo usuário do Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/user-driven).
    - Sem Autopilot: Para obter mais informações, confira [Ingressar um dispositivo Windows 10 no Azure AD durante a experiência de primeira execução](https://docs.microsoft.com/azure/active-directory/devices/azuread-joined-devices-frx#joining-a-device).

### <a name="what-happens-when-i-click-deploy"></a>O que acontecerá se eu clicar em Implantar?
O usuário e o dispositivo serão adicionados a novos grupos de segurança. Eles também serão definidos com as configurações recomendadas do Intune para segurança e produtividade no trabalho ou na escola. Depois que o usuário ingressar o dispositivo no Azure AD, os aplicativos e configurações adicionais serão adicionados ao dispositivo. Para saber mais sobre essas configurações adicionais, confira [Início Rápido: Registrar seu dispositivo Windows 10](~/enrollment/quickstart-enroll-windows-device.md).

## <a name="additional-information"></a>Informações adicionais

### <a name="register-device-with-windows-autopilot-optional"></a>Registrar o dispositivo no Windows Autopilot (Opcional)

Opcionalmente, você pode optar por usar um dispositivo Autopilot registrado. Para Autopilot, este cenário guiado atribuirá um perfil de implantação e um perfil da página de status de registro do Autopilot. O perfil de implantação do Autopilot será configurado da seguinte maneira:
- Modo controlado pelo usuário – ou seja, exigir que o usuário final insira o nome de usuário e a senha durante a Instalação do Windows.
- Ingresso do Azure AD.
- Personalizar a Instalação do Windows:
  - Ocultar a tela de termos de licenciamento de Software Microsoft
  - Ocultar configurações de Privacidade 
  - Criar o perfil local do usuário sem privilégios de administrador local
  - Ocultar as opções Alterar Conta na página de entrada corporativa

A página Status do registro será configurada para ser habilitada apenas para dispositivos Autopilot e não bloqueará a espera até que todos os aplicativos estejam instalados.

O cenário guiado também atribuirá o usuário ao dispositivo Autopilot selecionado para uma experiência de instalação personalizada.

#### <a name="post-requisites"></a>Pós-requisitos
Depois que o usuário ingressar o dispositivo no Azure Active Directory, as seguintes configurações serão aplicadas ao dispositivo:
1. O Office 365 ProPlus será instalado automaticamente no PC gerenciado por nuvem. Ele inclui os aplicativos com os quais você está familiarizado, incluindo Access, Excel, OneNote, Outlook, PowerPoint, Publisher, Skype for Business e Word. Você pode usar esses aplicativos para se conectar a serviços do Office 365, como o SharePoint Online, Exchange Online e Skype for Business Online. O Office 365 ProPlus é atualizado regularmente com novos recursos, ao contrário de versões que não são de assinatura do Office. Para obter uma lista de novos recursos, veja Novidades no Office 365.
2. As linhas de base de segurança do Windows serão instaladas no PC gerenciado por nuvem. Se você tiver configurado a Proteção Avançada contra Ameaças do Microsoft Defender, o cenário guiado também configurará as linhas de base do Defender. A Proteção Avançada contra Ameaças do Defender oferece uma nova camada de proteção pós-violação para a pilha de segurança do Windows 10. Com uma combinação de tecnologia de cliente incorporada ao Windows 10 e um serviço de nuvem robusto, ela ajudará a detectar ameaças que passaram por outras defesas. 

## <a name="next-steps"></a>Próximas etapas

- Se você estiver usando a Detecção Avançada contra Ameaças do Windows Defender, crie uma [Política de conformidade do Intune](~/protect/advanced-threat-protection.md#create-and-assign-the-compliance-policy) para exigir que uma análise de ameaças do Defender atenda à conformidade.
- Crie uma [Política de Acesso Condicional baseada em Dispositivo](~/protect/advanced-threat-protection.md#create-a-conditional-access-policy) para bloquear o acesso se o dispositivo não atender à conformidade do Intune.
