---
title: Atualizar recursos de BIOS do Windows usando políticas de MDM no Microsoft Intune – Azure | Microsoft Docs
description: Adicione um perfil da DFCI (Interface de Configuração de Firmware de Dispositivo) para gerenciar configurações da UEFI, como a CPU, o hardware interno e as opções de inicialização em dispositivos Windows 10 no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2bfc49f772331113314e45bc49360b8435b88037
ms.sourcegitcommit: 0d6f323152ec62f7d383891cce12ea0a4289cd8f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2019
ms.locfileid: "72889567"
---
# <a name="use-device-firmware-configuration-interface-profiles-on-windows-devices-in-microsoft-intune-public-preview"></a>Usar perfis da Interface de Configuração de Firmware de Dispositivo em dispositivos Windows no Microsoft Intune (visualização pública)

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

> [!Note]
> Cada [atualização mensal](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Service-Updates/ba-p/358728) pode levar vários dias para ser distribuída. Alguns recursos podem ser implantados ao longo de várias semanas e podem não estar disponíveis para todos os clientes imediatamente.

Quando usa o Intune para gerenciar dispositivos com Autopilot, você pode gerenciar as configurações da UEFI (BIOS) após elas serem registradas, usando a DFCI (Interface de Configuração de Firmware de Dispositivo). Para obter uma visão geral dos benefícios, cenários e pré-requisitos, confira [Visão geral da DFCI](https://microsoft.github.io/mu/dyn/mu_plus/DfciPkg/Docs/Dfci_Feature/).

A DFCI [permite que o Windows](https://docs.microsoft.com/windows/client-management/mdm/uefi-csp) transmita comandos de gerenciamento do Intune para a UEFI (Unified Extensible Firmware Interface).

No Intune, use esse recurso para controlar as configurações do BIOS. Normalmente, o firmware é mais resiliente a ataques mal-intencionados. Ele limita o controle dos usuários finais do BIOS, o que é bom em uma situação comprometida.

Por exemplo, você usa dispositivos Windows 10 em um ambiente seguro e deseja desabilitar a câmera. Você pode desabilitar a câmera na camada de firmware, de modo que não importa o que o usuário final faça. Reinstalar o sistema operacional ou apagar o computador não ligará a câmera novamente. Em outro exemplo, bloqueie as opções de inicialização para impedir que os usuários inicializem outro sistema operacional ou uma versão mais antiga do Windows que não tem os mesmos recursos de segurança.

Se reinstalar uma versão mais antiga do Windows, instalar um sistema operacional separado ou formatar o disco rígido, você não poderá substituir o gerenciamento da DFCI. Esse recurso pode impedir que malwares se comuniquem com processos do sistema operacional, incluindo processos elevados do sistema operacional. A cadeia confiável da DFCI usa criptografia de chave pública e não depende da segurança de senha da UEFI (BIOS) local. Essa camada de segurança impede que usuários locais acessem configurações gerenciadas dos menus da UEFI (BIOS) do dispositivo.

Esse recurso aplica-se a:

- Windows 10 RS5 (1809) e posterior na UEFI com suporte

## <a name="before-you-begin"></a>Antes de começar

- O fabricante do dispositivo precisa ter a DFCI adicionada a seu firmware da UEFI no processo de fabricação ou como uma atualização de firmware instalada. Trabalhe com seus fornecedores de dispositivo para determinar os fabricantes que dão suporte à DFCI ou a versão de firmware necessária para usar a DFCI.

- O dispositivo precisa ser registrado para o Windows Autopilot por um [parceiro CSP (Provedor de Soluções na Nuvem) da Microsoft](https://partner.microsoft.com/cloud-solution-provider) ou registrado diretamente pelo OEM. 

  Dispositivos registrados manualmente para o Autopilot, por exemplo, [importados de um arquivo CSV](../enrollment/enrollment-autopilot.md#add-devices), não têm permissão para usar a DFCI. Por design, o gerenciamento da DFCI requer um atestado externo da aquisição comercial do dispositivo por meio de um OEM ou um registro de parceiro CSP da Microsoft para o Windows Autopilot.

  Depois que o dispositivo for registrado, seu número de série será mostrado na lista de dispositivos do Windows Autopilot.

  Para obter mais informações sobre o Autopilot, incluindo os requisitos, confira [Registrar dispositivos Windows no Intune usando o Windows Autopilot](../enrollment/enrollment-autopilot.md).

## <a name="create-your-azure-ad-security-groups"></a>Criar seus grupos de segurança do Azure AD

Os perfis de implantação do Autopilot são atribuídos aos grupos de segurança do Azure AD. Crie grupos que incluam seus dispositivos compatíveis com a DFCI. Para dispositivos DFCI, a maioria das organizações pode criar grupos de dispositivos em vez de grupos de usuários. Considere os seguintes cenários:

- o departamento de RH (recursos humanos) tem diferentes dispositivos Windows. Por motivos de segurança, você não quer que ninguém nesse grupo use a câmera nos dispositivos. Nesse cenário, você pode criar um grupo de usuários de segurança do RH para que a política se aplique aos usuários nesse grupo, seja qual for o tipo de dispositivo.
- No chão de fábrica, você tem 10 dispositivos. Em todos os dispositivos, você deseja impedir a inicialização dos dispositivos usando um dispositivo USB. Nesse cenário, você pode criar um grupo de dispositivos de segurança e adicionar esses 10 dispositivos ao grupo.

Para obter mais informações sobre como criar grupos no Intune, confira [Adicionar grupos para organizar usuários e dispositivos](../fundamentals/groups-add.md).

## <a name="create-the-profiles"></a>Criar os perfis

Para usar a DFCI, crie os seguintes perfis e atribua-os ao seu grupo.

### <a name="create-an-autopilot-deployment-profile"></a>Criar um perfil de implantação do Autopilot

Esse perfil configura e pré-configura novos dispositivos. [Perfil de implantação do Autopilot](../enrollment/enrollment-autopilot.md#create-an-autopilot-deployment-profile) lista as etapas necessárias para criar o perfil.

### <a name="create-an-enrollment-state-page-profile"></a>Criar um perfil de Página de Estado do Registro

Esse perfil garante que os dispositivos sejam verificados e habilitados para a DFCI durante a Instalação do Windows. É altamente recomendável usá-lo para bloquear o uso do dispositivo até que todos os aplicativos e perfis sejam instalados. [Perfil de Página de Estado do Registro](../enrollment/windows-enrollment-status.md) lista as etapas necessárias para criar o perfil.

### <a name="create-the-dfci-profile"></a>Criar o perfil da DFCI

Esse perfil inclui as configurações da DFCI que você define.

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
3. Insira as seguintes propriedades:

    - **Nome**: Insira um nome descritivo para o perfil. Nomeie suas políticas para que você possa identificá-las facilmente mais tarde. Por exemplo, um bom nome de perfil é **Windows: Definir as configurações da DFCI em dispositivos Windows**.
    - **Descrição**: Insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
    - **Plataforma**: escolha **Windows 10 e posterior**.
    - **Tipo de perfil**: Selecione **Interface de Configuração do Firmware do Dispositivo**.

4. Configure as definições:

    - **Permitir que o usuário local altere as configurações da UEFI (BIOS)** : Suas opções:
      - **Somente as configurações não definidas**: o usuário local pode alterar qualquer configuração, *exceto* pelas configurações definidas explicitamente como **Habilitar** ou **Desabilitar** pelo Intune.
      - **Nenhum**: o usuário local não pode alterar nenhuma configuração da UEFI (BIOS), incluindo configurações não mostradas no perfil DFCI.

    - **Virtualização de CPU e E/S**: Suas opções:
        - **Não configurado**: o Intune não altera esse recurso e deixa as configurações no estado em que se encontram.
        - **Habilitado**: o BIOS habilita as funcionalidades de virtualização de CPU e E/S da plataforma para uso pelo sistema operacional. Ele ativa as tecnologias de Segurança com Base em Virtualização e Device Guard do Windows.
        - **Desabilitar**: o BIOS desabilita as funcionalidades de virtualização de CPU e E/S da plataforma e impede que sejam usadas.
    - **Câmeras**: Suas opções:
        - **Não configurado**: o Intune não altera esse recurso e deixa as configurações no estado em que se encontram.
        - **Habilitado**: todas as câmeras internas gerenciadas diretamente pela UEFI (BIOS) são habilitadas. Dispositivos periféricos, como câmeras USB, não são afetados.
        - **Desabilitado**: todas as câmeras internas gerenciadas diretamente pela UEFI (BIOS) são desabilitadas. Dispositivos periféricos, como câmeras USB, não são afetados.
    - **Microfones e alto-falantes**:  Suas opções:
        - **Não configurado**: o Intune não altera esse recurso e deixa as configurações no estado em que se encontram.
        - **Habilitado**: todos os alto-falantes e microfones internos gerenciados diretamente pela UEFI (BIOS) são habilitados. Dispositivos periféricos, como dispositivos USB, não são afetados.
        - **Desabilitado**: todos os alto-falantes e microfones internos gerenciados diretamente pela UEFI (BIOS) são desabilitados. Dispositivos periféricos, como dispositivos USB, não são afetados.
    - **Rádios (Bluetooth, Wi-Fi, NFC etc.)** : Suas opções:
        - **Não configurado**: o Intune não altera esse recurso e deixa as configurações no estado em que se encontram.
        - **Habilitado**: todos os rádios internos gerenciados diretamente pela UEFI (BIOS) são habilitados. Dispositivos periféricos, como dispositivos USB, não são afetados.
        - **Desabilitado**: todos os rádios internos gerenciados diretamente pela UEFI (BIOS) são desabilitados. Dispositivos periféricos, como dispositivos USB, não são afetados.

        > [!WARNING]
        > Se você desabilitar a configuração **Rádios**, o dispositivo exigirá uma conexão de rede com fio. Caso contrário, o dispositivo pode não ser gerenciável.

    - **Inicialize de uma mídia externa (USB, SD)** : Suas opções:
        - **Não configurado**: o Intune não altera esse recurso e deixa as configurações no estado em que se encontram.
        - **Habilitado**: a UEFI (BIOS) permite a inicialização de um armazenamento de disco não rígido.
        - **Desabilitado**: a UEFI (BIOS) não permite a inicialização de um armazenamento de disco não rígido.
    - **Inicialize de adaptadores de rede**:  Suas opções:
        - **Não configurado**: o Intune não altera esse recurso e deixa as configurações no estado em que se encontram.
        - **Habilitado**: a UEFI (BIOS) permite a inicialização de interfaces de rede internas.
        - **Desabilitado**: a UEFI (BIOS) não permite a inicialização de interfaces de rede internas.

5. Quando terminar, selecione **OK** > **Criar** para salvar suas alterações. O perfil é criado e exibido na lista.

## <a name="assign-the-profiles-and-reboot"></a>Atribuir os perfis e reinicializar

Após serem criados, os perfis estão [prontos para serem atribuídos](../configuration/device-profile-assign.md). Atribua os perfis a seus grupos de segurança do Azure AD que incluem seus dispositivos DFCI.

Na próxima vez em que o dispositivo for sincronizado ou reinicializado, as configurações de perfil da DFCI serão aplicadas. Após a política se aplicar, reinicialize o dispositivo.

Quando o dispositivo executa a instalação do dispositivo Windows, a DFCI pode forçar uma reinicialização durante a Página de Status do Registro. Após a conclusão da instalação, você pode confirmar se as configurações da DFCI estão ativas reinicializando o dispositivo. Em seguida, use as instruções do fabricante do dispositivo para abrir o menu da UEFI.

## <a name="update-existing-dfci-settings"></a>Atualizar configurações de DFCI existentes

Se quiser alterar configurações da DFCI existentes em dispositivos que estão em uso, você poderá fazer isso. No perfil da DFCI existente, altere as configurações e salve as alterações. Como o perfil já foi atribuído, as novas configurações da DFCI entrarão em vigor quando:

1. O dispositivo fizer o check-in no serviço do Intune para verificar se há atualizações de perfil. Os check-ins acontecem em vários momentos. Para obter mais informações, confira [quando os dispositivos recebem atualizações de política, perfil ou aplicativo](../configuration/device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

2. Para impor as novas configurações, reinicialize o dispositivo [remotamente](../remote-actions/device-restart.md) ou localmente.

Você também pode [sinalizar os dispositivos para que façam check-in](../remote-actions/device-sync.md). Após uma sincronização bem-sucedida, [sinalize-os para reinicialização](../remote-actions/device-restart.md).

>[!NOTE]
> Excluir o perfil da DFCI ou remover um dispositivo do grupo atribuído ao perfil não remove as configurações da DFCI nem reabilita os menus da UEFI (BIOS). Se quiser parar de usar a DFCI, atualize seu perfil existente da DFCI. Para obter mais informações sobre as etapas, confira [desativar o dispositivo](#retire) neste artigo.

## <a name="reuse-retire-or-recover-the-device"></a>Reutilizar, desativar ou recuperar o dispositivo

### <a name="reuse"></a>Reutilizar

Se planejar redefinir o Windows para realocar o dispositivo, [apague o dispositivo](../remote-actions/devices-wipe.md). **Não** remova o registro do dispositivo do Autopilot.

Depois de apagar o dispositivo, mova-o para o grupo atribuído aos novos perfis da DFCI e do Autopilot. Reinicialize o dispositivo para executar novamente a Instalação do Windows.

### <a name="retire"></a>Desativar

Quando estiver pronto para desativar o dispositivo e liberá-lo do gerenciamento, atualize no perfil da DFCI as configurações da UEFI (BIOS) que você deseja no estado de saída. Normalmente, você deseja que todas as configurações estejam habilitadas. Por exemplo:

1. Abra seu perfil da DFCI (**Configuração do dispositivo** > **Perfis**).
2. Altere **Permitir que o usuário local altere configurações da UEFI (BIOS)** para **Somente as configurações não definidas**.
3. Defina todas as outras configurações como **Não configuradas**.
4. Salve suas configurações.

Estas etapas desbloqueiam os menus da UEFI (BIOS) do dispositivo. Os valores permanecem os mesmos que os do perfil (**Habilitado** ou **Desabilitado**) e não são redefinidos com os valores padrão do sistema operacional.

Agora, você está pronto para apagar o dispositivo. Depois que o dispositivo for apagado, exclua o registro do Autopilot. A exclusão do registro impede que o dispositivo volte a ser registrado automaticamente quando for reinicializado.

### <a name="recover"></a>Recuperar

Se você apagar um dispositivo e excluir o registro do Autopilot antes de desbloquear os menus da UEFI (BIOS), os menus permanecerão bloqueados. O Intune não pode enviar atualizações de perfil para desbloqueá-lo.

Para desbloquear o dispositivo, abra o menu UEFI (BIOS) e atualize o gerenciamento de rede. A recuperação desbloqueia os menus, mas deixa todas as configurações de UEFI (BIOS) definidas para os valores do perfil anterior da DFCI do Intune.

## <a name="end-user-impact"></a>Impacto para o usuário final

Quando a política da DFCI é aplicada, os usuários locais não podem alterar as configurações definidas pela DFCI, mesmo que o menu da UEFI (BIOS) seja protegido por senha. Dependendo das configurações definidas, os usuários finais podem receber erros indicando que componentes de hardware não foram encontrados ou não podem ser diagnosticados. Forneça uma documentação aos usuários finais explicando as opções que você desabilitou.  

## <a name="next-steps"></a>Próximas etapas

Após o perfil ser atribuído, [monitore seu status](../device-profile-monitor.md).
