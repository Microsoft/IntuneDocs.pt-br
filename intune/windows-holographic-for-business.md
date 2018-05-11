---
title: Gerenciar dispositivos do Windows Holographic com o Microsoft Intune – Azure | Microsoft Docs
description: Usando o Microsoft Intune, você pode concluir diferentes tarefas em dispositivos que executam o Windows Holographic for Business, incluindo configurar o Portal da Empresa, crie uma política de conformidade, personalizar as configurações do OMA-URI, implantar aplicativos, categorizar dispositivos em grupos, criar perfis, restringir dispositivos, habilitar atualizações de software, definir termos e condições, definir configurações de VPN e Wi-Fi e usar o Hello para Empresas.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 5/1/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 18f86580fc4c80fade7aeaa9678e9d8edac9a53e
ms.sourcegitcommit: b57be56524ddb5026fab94f7638dc516ed118325
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="customize-devices-running-windows-holographic-with-intune"></a>Personalizar os dispositivos que executam o Windows Holographic com o Intune

O Microsoft Intune é compatível com dispositivos que executam o Windows Holographic for Business, como o [Microsoft HoloLens](https://docs.microsoft.com/en-us/hololens/).

Para gerenciar dispositivos que executam o Windows Holographic com o Microsoft Intune, você deve criar um perfil de Atualização da Edição. Este perfil de atualização realiza o upgrade de dispositivos do Windows Holographic para o Windows Holographic for Business. Para o Microsoft HoloLens, você pode adquirir o Commercial Suite para obter a licença necessária para a atualização. Para obter mais informações, consulte [Atualizar dispositivos que executam o Windows Holographic para o Windows Holographic for Business](holographic-upgrade.md).

Para ajudar a gerenciar e personalizar seus dispositivos que executam o Windows Holographic for Business, você pode usar as tarefas neste artigo. Por exemplo, você pode gerenciar atualizações de software, definir as configurações de VPN e muito mais.

## <a name="azure-active-directory"></a>Active Directory do Azure

O Azure AD (Active Directory) é um ótimo recurso para ajudar a gerenciar e controlar dispositivos que executam o Windows Holographic for Business. Com o Intune e o Azure AD, é possível: 

- **[Configurar dispositivos ingressados no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-setup)**: no Azure AD (Active Directory), é possível adicionar seus dispositivos Windows 10 do trabalho, incluindo dispositivos em execução no Windows Holographic for Business. Esse recurso permite que o Azure AD controle o dispositivo. Ele ajuda a garantir que seus usuários acessem os recursos da empresa em dispositivos que atendem aos padrões de segurança e de conformidade.

  A [Introdução ao gerenciamento de dispositivos no Azure AD](https://docs.microsoft.com/azure/active-directory/device-management-introduction) fornece mais detalhes.

- **[Registro em massa de dispositivos Windows](windows-bulk-enroll.md)**: é possível ingressar grandes números de novos dispositivos Windows no Azure AD (Active Directory) e no Intune. Esse recurso é chamado de registro em massa e usa pacotes de provisionamento. Esses pacotes ingressam os dispositivos que executam o Windows Holographic for Business no seu locatário do Azure AD e os registra no Intune.

## <a name="company-portal"></a>Portal da Empresa
**[Configurar o aplicativo do Portal da Empresa](company-portal-app.md)**

O Intune inclui o Portal da Empresa, que é o ponto do qual os usuários acessam dados da empresa, registram dispositivos, instalam aplicativos, entram em contato com o departamento de TI e muito mais. Você pode personalizar o aplicativo Portal da Empresa para seus dispositivos que executam o Windows Holographic for Business.

## <a name="compliance-policy"></a>Política de conformidade
**[Criar uma política de conformidade do dispositivo](compliance-policy-create-windows.md)**

Políticas de conformidade são regras e configurações que os dispositivos devem cumprir para serem compatíveis. Você pode usar essas políticas com acesso condicional para bloquear o acesso aos recursos da empresa para dispositivos não em conformidade. No Intune, você pode criar políticas de conformidade para permitir ou bloquear o acesso para dispositivos que executam o Windows Holographic for Business. Por exemplo, você pode criar uma política que exige que o BitLocker seja habilitado.

Consulte também **[Introdução às políticas de conformidade](device-compliance-get-started.md)**.

## <a name="deploy-and-manage-apps"></a>Implantar e gerenciar aplicativos
**[Adicionar aplicativos ao Intune](apps-add.md)**

Usando o Intune, você pode adicionar aplicativos a dispositivos que executam o Windows Holographic for Business. Há várias maneiras de implantar aplicativos, incluindo:

- [Adicionar aplicativos da Microsoft Store](store-apps-windows.md)
- [Adicionar aplicativos que você criar](lob-apps-windows.md)
- [Atribuir aplicativos a grupos](apps-deploy.md)

O Microsoft Intune pode implantar os aplicativos Universal Windows nos dispositivos do Microsoft HoloLens que executam o Windows Holographic for Business. Você pode carregar diretamente seus pacotes de aplicativo no Portal do Azure no Intune ou implantá-los pelo Microsoft Store para Empresas. Para saber mais sobre as áreas relacionadas, veja o seguinte:
- Para implantar aplicativos de linha de negócios (LOB) usando o Portal do Azure no Intune, veja [Como adicionar aplicativos de linha de negócios do Windows para o Microsoft Intune](lob-apps-windows.md).
- Para implantar aplicativos usando o Microsoft Store for Business, veja [Como gerenciar aplicativos adquiridos na Microsoft Store para Empresas com o Microsoft Intune](windows-store-for-business.md). 
- Para saber mais sobre o gerenciamento de aplicativos com o Microsoft Intune, veja [O que é o gerenciamento de aplicativos no Microsoft Intune](app-management.md).
- Para saber mais sobre o desenvolvimento de aplicativos para o Microsoft HoloLens, veja [Aplicativos de realidade mista para o Microsoft HoloLens](https://www.microsoft.com/hololens/apps). 

> [!NOTE]
> Os dispositivos do HoloLens que executam o Windows 10 Holographic for Business 1607 não oferecem suporte a aplicativos licenciados online da Microsoft Store para Empresas. Para saber mais, veja [Instalar aplicativos no HoloLens](https://docs.microsoft.com/en-us/hololens/hololens-install-apps).

## <a name="device-actions"></a>Ações de dispositivo
O Intune tem algumas ações internas que permitem que os administradores de TI realizem tarefas diferentes, localmente no dispositivo, ou remotamente usando o Intune no portal do Azure. Os usuários também podem emitir um comando remoto do Portal da Empresa do Intune para dispositivos de propriedade pessoal registrados no Intune.

Ao usar os dispositivos que executam o Windows Holographic for Business, as seguintes ações podem ser usadas: 

- **[Redefinição de fábrica](devices-wipe.md#factory-reset)**: a ação de **redefinição de fábrica** remove o dispositivo do Intune e o restaura para as configurações de fábrica padrão. Use essa ação antes de dar o dispositivo a um novo usuário ou quando ele for extraviado ou roubado.

- **[Remover dados da empresa](devices-wipe.md#remove-company-data)**: a ação **Remover dados da empresa** remove o dispositivo do Intune e os dados de aplicativo, configurações e perfis de email gerenciados atribuídos pelo Intune. Os dados pessoais do usuário permanecem no dispositivo.

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

Antes de os usuários poderem registrar dispositivos e acessar os aplicativos da empresa, incluindo email, você pode exigir que eles aceitem os termos e condições da sua empresa. No Intune, você pode definir como os termos e condições são mostrados no Portal da Empresa e também atribuir estes termos e condições a dispositivos que executam o Windows Holographic for Business.

## <a name="windows-hello-for-business"></a>Windows Hello para Empresas
**[Usar o Windows Hello para Empresas](windows-hello.md)**

O Hello para Empresas é um método de conexão alternativo que usa uma conta do Azure Active Directory para substituir uma senha, um cartão inteligente ou um cartão inteligente virtual. Com o Hello para Empresas, os dispositivos Windows Holographic for Business podem entrar com um PIN com um tamanho mínimo definido por você.
