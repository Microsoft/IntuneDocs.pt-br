---
title: Usar dispositivos do Windows Holographic com o Microsoft Intune – Azure | Microsoft Docs
description: Usando o Microsoft Intune, é possível gerenciar e concluir diferentes tarefas em dispositivos que executam o Windows Holographic for Business e HoloLens, incluindo configurar o Portal da Empresa, crie uma política de conformidade, personalizar as configurações do OMA-URI, implantar aplicativos, categorizar dispositivos em grupos, criar perfis, restringir dispositivos, habilitar atualizações de software, definir termos e condições, definir configurações de VPN e Wi-Fi e usar o Hello para Empresas.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: fd99a168747bd4a0f5852404e767d658b8400ba2
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52180826"
---
# <a name="manage-and-use-windows-holographic-and-hololens-devices-with-intune"></a>Gerenciar e usar os dispositivos Windows Holographic e HoloLens com o Intune

O Microsoft Intune inclui muitos recursos para ajudar a gerenciar dispositivos que executam o Windows Holographic for Business, como o [Microsoft HoloLens](https://docs.microsoft.com/hololens/). Usando o Intune, é possível confirmar se os dispositivos estão em conformidade com as regras da sua organização, e é possível personalizar o dispositivo adicionando um perfil de VPN ou WiFi. Outro recurso importante é usar o dispositivo como um quiosque e executar um aplicativo específico ou um conjunto de aplicativos específico.

As tarefas neste artigo ajudam a gerenciar, personalizar e proteger seus dispositivos que executam o Windows Holographic for Business, incluindo atualizações de software, e que usam o Hello para Empresas.

Para usar dispositivos Windows Holographic com o Intune, crie um perfil de atualização de edição. Este perfil de atualização realiza o upgrade de dispositivos do Windows Holographic para o Windows Holographic for Business. Para o Microsoft HoloLens, você pode comprar o Commercial Suite para obter a licença necessária para a atualização. Para obter mais informações, consulte [Atualizar dispositivos que executam o Windows Holographic para o Windows Holographic for Business](holographic-upgrade.md).

## <a name="azure-active-directory"></a>Active Directory do Azure

O Azure AD (Active Directory) é um ótimo recurso para ajudar a gerenciar e controlar dispositivos que executam o Windows Holographic for Business. Com o Intune e o Azure AD, é possível: 

- **[Configurar dispositivos ingressados no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-setup)**: no Azure AD (Active Directory), é possível adicionar seus dispositivos Windows 10 do trabalho, incluindo dispositivos em execução no Windows Holographic for Business. Esse recurso permite que o Azure AD controle o dispositivo. Ele ajuda a confirmar se os usuários estão acessando os recursos da empresa em dispositivos que atendem aos padrões de segurança e conformidade.

  A [Introdução ao gerenciamento de dispositivos no Azure AD](https://docs.microsoft.com/azure/active-directory/device-management-introduction) fornece mais detalhes.

- **[Registro em massa de dispositivos Windows](windows-bulk-enroll.md)**: é possível ingressar grandes números de novos dispositivos Windows no Azure AD (Active Directory) e no Intune. Esse recurso é chamado de registro em massa e usa pacotes de provisionamento. Esses pacotes ingressam os dispositivos que executam o Windows Holographic for Business no seu locatário do Azure AD e os registra no Intune.

## <a name="company-portal"></a>Portal da Empresa
**[Configurar o aplicativo do Portal da Empresa](company-portal-app.md)**

O Intune fornece o aplicativo Portal da Empresa para que os usuários acessem dados da empresa, registrem dispositivos, instalem aplicativos, contatem o departamento de TI e muito mais. Você pode personalizar o aplicativo Portal da Empresa para seus dispositivos que executam o Windows Holographic for Business.

Usando o aplicativo Portal da Empresa, você também pode executar as seguintes ações:

- [Remover um dispositivo do Intune](/intune-user-help/unenroll-your-device-from-intune-windows) usando o aplicativo Configurações ou o aplicativo Portal da Empresa
- [Renomear um dispositivo](/intune-user-help/rename-your-device-cpapp)
- [Instalar aplicativos](/intune-user-help/install-apps-cpapp-windows) em um dispositivo
- [Sincronizar dispositivos manualmente](/intune-user-help/sync-your-device-manually-windows) usando o aplicativo Configurações ou o aplicativo Portal da Empresa


## <a name="compliance-policy"></a>Política de conformidade
**[Criar uma política de conformidade do dispositivo](compliance-policy-create-windows.md)**

Políticas de conformidade são regras e configurações que os dispositivos devem cumprir para serem compatíveis. Use essas políticas com acesso condicional para bloquear o acesso aos recursos da empresa em dispositivos que não estejam em conformidade. No Intune, crie políticas de conformidade para permitir ou bloquear o acesso de dispositivos que executam o Windows Holographic for Business. Por exemplo, você pode criar uma política que exige que o BitLocker seja habilitado.

Consulte também **[Introdução às políticas de conformidade](device-compliance-get-started.md)**.

## <a name="deploy-and-manage-apps"></a>Implantar e gerenciar aplicativos
**[Adicionar aplicativos ao Intune](apps-add.md)**

Usando o Intune, você pode adicionar aplicativos a dispositivos que executam o Windows Holographic for Business. Há várias maneiras de implantar aplicativos, incluindo:

- [Adicionar aplicativos da Microsoft Store](store-apps-windows.md)
- [Adicionar aplicativos que você criar](lob-apps-windows.md)
- [Atribuir aplicativos a grupos](apps-deploy.md)

O Microsoft Intune pode implantar os aplicativos Universal Windows nos dispositivos do Microsoft HoloLens que executam o Windows Holographic for Business. Você pode carregar diretamente seus pacotes do aplicativo no portal do Azure do Intune ou implantá-los pela Microsoft Store para Empresas. Para obter mais informações sobre áreas relacionadas, confira os seguintes artigos:
- Para implantar aplicativos de linha de negócios (LOB) usando o Portal do Azure no Intune, veja [Como adicionar aplicativos de linha de negócios do Windows para o Microsoft Intune](lob-apps-windows.md).

    > [!NOTE]
    > O Intune permite um tamanho máximo de pacote de 8 GB. Esse tamanho de pacote só está disponível para aplicativos LOB carregados no Intune.

- Para implantar aplicativos usando o Microsoft Store for Business, veja [Como gerenciar aplicativos adquiridos na Microsoft Store para Empresas com o Microsoft Intune](windows-store-for-business.md). 
- Para saber mais sobre o gerenciamento de aplicativos com o Microsoft Intune, veja [O que é o gerenciamento de aplicativos no Microsoft Intune](app-management.md).
- Para saber mais sobre o desenvolvimento de aplicativos para o Microsoft HoloLens, veja [Aplicativos de realidade mista para o Microsoft HoloLens](https://www.microsoft.com/hololens/apps). 

> [!NOTE]
> Os dispositivos do HoloLens que executam o Windows 10 Holographic for Business 1607 não oferecem suporte a aplicativos licenciados online da Microsoft Store para Empresas. Para saber mais, veja [Instalar aplicativos no HoloLens](https://docs.microsoft.com/hololens/hololens-install-apps).

## <a name="device-actions"></a>Ações de dispositivo
O Intune tem algumas ações internas que permitem que os administradores de TI realizem tarefas diferentes, localmente no dispositivo, ou remotamente usando o Intune no portal do Azure. Os usuários também podem emitir um comando remoto do Portal da Empresa do Intune para dispositivos de propriedade pessoal registrados no Intune.

Ao usar os dispositivos que executam o Windows Holographic for Business, as seguintes ações podem ser usadas: 

- **[Apagar](devices-wipe.md#wipe)**: a ação **Apagar** remove o dispositivo do Intune e restaura-o para as configurações padrão de fábrica. Use essa ação antes de dar o dispositivo a um novo usuário ou quando ele for extraviado ou roubado.

- **[Desativar](devices-wipe.md#retire)**: a ação **desativar** remove o dispositivo do Intune. Ela também remove do aplicativo gerenciado os dados, as configurações e os perfis de email atribuídos pelo Intune. Os dados pessoais do usuário permanecem no dispositivo.

- **[Sincronizar dispositivos para obter as políticas e ações mais recentes](device-sync.md)**: a ação **Sincronizar** força o dispositivo a fazer check-in imediatamente com o Intune. Quando um dispositivo faz check-in, ele recebe imediatamente ações pendentes ou políticas atribuídas a ele. Esse recurso ajuda-o a validar e a solucionar problemas das políticas que você atribuiu, sem precisar esperar o próximo check-in agendado.

**[O que é o gerenciamento de dispositivos do Microsoft Intune?](device-management.md)** é um bom recurso para aprender a gerenciar dispositivos usando o Portal do Azure. 

## <a name="device-categories-and-groups"></a>Grupos e categorias de dispositivo
**[Categorizar os dispositivos em grupos](device-group-mapping.md)**

Usando o Intune, você pode criar categorias de dispositivo para adicionar automaticamente os dispositivos a grupos com base em categorias que você criar, como Vendas, Contabilidade, Recursos Humanos e assim por diante. A ideia é tornar mais fácil gerenciar seus dispositivos que executam o Windows Holographic for Business.

## <a name="device-configuration-profiles"></a>Perfis de configuração do dispositivo 
**[Introdução aos perfis de configuração](device-profiles.md), e [criar seu próprio perfil](device-profile-create.md)**

O Intune inclui configurações e recursos que você pode habilitar ou desabilitar em diferentes dispositivos na sua organização. Essas configurações e recursos são gerenciados com o uso de perfis. Por exemplo, você pode criar um perfil que habilite a Cortana, ou usar a Tela Inteligente do Windows Defender em seus dispositivos que executam o Windows Holographic for Business.

Em seus perfis, você pode usar o OMA-URI para personalizar algumas configurações, criar restrições de dispositivo e configurar uma VPN (rede virtual privada) e Wi-Fi.

#### <a name="custom-device-settingscustom-settings-windows-holographicmd"></a>[Configurações de dispositivo personalizadas](custom-settings-windows-holographic.md)

Para definir configurações do OMA-URI (Open Mobile Alliance Uniform Resource Identifier), você pode criar um perfil personalizado do Intune. Use as configurações de OMA-URI para controlar recursos diferentes em seus dispositivos Windows Holographic for Business, como habilitação de VPN ou verificar se há atualizações no Microsoft Update.

#### <a name="configure-kiosk-modekiosk-settingsmdwindows-holographic-for-business"></a>[Configurar o modo de quiosque](kiosk-settings.md#windows-holographic-for-business)

Usando os recursos de computador compartilhados ou convidados disponíveis no Intune, você pode configurar dispositivos do Windows Holographic for Business para serem executados como um quiosque. Esses dispositivos podem executar um aplicativo (modo de quiosque de aplicativo único) ou vários aplicativos (modo de quiosque de vários aplicativos).

#### <a name="device-restrictionsdevice-restrictions-windows-holographicmd"></a>[Restrições de dispositivo](device-restrictions-windows-holographic.md)

Restrições de dispositivo permitem controlar diferentes configurações e recursos em seus dispositivos, incluindo exigir uma senha, instalar aplicativos da [Microsoft Store](https://www.microsoft.com/store/apps/windows?icid=CNavAppsWindowsApps), habilitar Bluetooth e muito mais. Essas restrições são criadas em um perfil do Intune. Esse perfil pode ser aplicado a vários dispositivos que executam o Windows Holographic for Business.

#### <a name="configure-vpnvpn-settings-configuremd"></a>[Configurar VPN](vpn-settings-configure.md)

Redes virtuais privadas (VPN) oferecem aos usuários acesso remoto seguro à rede da empresa. No Intune, é possível criar um perfil de VPN que inclua configurações específicas para seus dispositivos que executam o Windows Holographic for Business. Por exemplo, você pode criar um perfil VPN para que todos os dispositivos do Windows Holographic for Business usem o Citrix VPN como o tipo de conexão.

#### <a name="configure-wi-fiwi-fi-settings-configuremd"></a>[Configurar Wi-Fi](wi-fi-settings-configure.md)

Você também pode criar um perfil do Wi-Fi no Intune para atribuir configurações de rede sem fio aos seus dispositivos do Windows Holographic for Business. Quando você atribui um perfil de Wi-Fi, seus usuários finais obtêm acesso à rede corporativa sem qualquer configuração de rede. Por exemplo, você pode criar uma rede Wi-Fi dedicada apenas aos seus dispositivos do Windows Holographic for Business.

## <a name="software-updates"></a>Atualizações de software
**[Gerenciar atualizações de software](windows-update-for-business-configure.md)**

O Intune inclui um recurso chamado anéis de atualização para dispositivos Windows 10. Esses anéis de atualização incluem um grupo de configurações que determinam como as atualizações são instaladas. Por exemplo, você pode criar uma janela de manutenção para instalar as atualizações ou optar por reiniciar depois que as atualizações forem instaladas. Um anel de atualização pode ser aplicado a vários dispositivos que executam o Windows Holographic for Business.

## <a name="terms-and-conditions"></a>Termos e condições
**[Gerenciar os termos e condições da sua empresa para acesso do usuário](terms-and-conditions-create.md)**

Para que os usuários possam registrar dispositivos e acessar os aplicativos da empresa, incluindo email, você pode exigir que eles aceitem os termos e condições da empresa. No Intune, defina como os termos e condições são mostrados no Portal da Empresa. Além disso, atribua estes termos e condições aos dispositivos que executam o Windows Holographic for Business.

## <a name="windows-hello-for-business"></a>Windows Hello para Empresas
**[Usar o Windows Hello para Empresas](windows-hello.md)**

O Hello para Empresas é um método de conexão alternativo que usa uma conta do Azure Active Directory para substituir uma senha, um cartão inteligente ou um cartão inteligente virtual. Com o Hello para Empresas, os dispositivos Windows Holographic for Business podem entrar com um PIN com um tamanho mínimo definido por você.
