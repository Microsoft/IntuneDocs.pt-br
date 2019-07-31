---
title: Definir configurações de proteção de ponto de extremidade no Microsoft Intune – Azure | Microsoft Docs
description: Crie configurações de proteção de ponto de extremidade ao criar um perfil do dispositivo Windows 10 ou macOS no Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/18/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
mr.reviewer: karthib
ms.openlocfilehash: 13e8c7fd0c822a2bdfbf7c183ea6752f99cf7991
ms.sourcegitcommit: d2ac912b834c4840de9cc92ba1815b6ecfbfb52b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/25/2019
ms.locfileid: "68482780"
---
# <a name="add-endpoint-protection-settings-in-intune"></a>Adicionar configurações de proteção de ponto de extremidade no Intune  

Com o Intune, é possível usar perfis de configuração de dispositivo para gerenciar recursos comuns de proteção de ponto de extremidade nos dispositivos, incluindo:  
- Firewall   
- BitLocker  
- Permitir ou bloquear aplicativos  
- Criptografia e Windows Defender  

Por exemplo, você pode criar um perfil de proteção de ponto de extremidade que permita apenas a usuários do macOS instalar aplicativos da Mac App Store. Ou habilite a Windows SmartScreen durante a execução de aplicativos em dispositivos Windows 10.  

Antes de criar um perfil, consulte os seguintes artigos que detalham as configurações de proteção de ponto de extremidade que o Intune pode gerenciar para cada plataforma compatível:  
   - [Configurações do macOS](endpoint-protection-macos.md)  
   - [Configurações do Windows 10](endpoint-protection-windows-10.md)  

## <a name="create-a-device-profile-containing-endpoint-protection-settings"></a>Criar um perfil de dispositivo contendo configurações de proteção de ponto de extremidade  

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).  
3. Selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**.  
4. Insira um **Nome** e uma **Descrição** para o perfil de proteção de ponto de extremidade.  
5. Na lista suspensa **Plataforma**, selecione a plataforma do dispositivo ao qual você deseja aplicar as configurações personalizadas. No momento, é possível escolher uma das seguintes plataformas para as configurações de restrição de dispositivo:  
   - **macOS**  
   - **Windows 10 e posterior**  
6. Na lista suspensa de tipos de **Tipo de perfil**, escolha **Endpoint Protection**.  
7. Dependendo da plataforma escolhida, as configurações que podem ser definidas são diferentes. Consulte:  
   - [Configurações do macOS](endpoint-protection-macos.md)  
   - [Configurações do Windows 10](endpoint-protection-windows-10.md)  

8. Depois de definir as configurações aplicáveis, selecione **Criar** na página **Criar perfil**.  

   O perfil é criado e exibido na página da lista de perfis. Para atribuir esse perfil a grupos, consulte [atribuir perfis de dispositivo](device-profile-assign.md).  

## <a name="add-custom-firewall-rules-for-windows-10-devices"></a>Adicionar regras de firewall personalizadas para dispositivos Windows 10  
***As regras de firewall personalizadas estão em Versão Prévia Pública.***  

Ao configurar o Windows Defender Firewall como parte de um perfil que inclui regras da proteção de ponto de extremidade para o Windows 10, você pode configurar regras personalizadas para firewalls. As regras personalizadas permitem que você expanda o conjunto predefinido de regras do firewall compatíveis com o Windows 10.  

Ao planejar perfis com regras de firewall personalizadas, considere as seguintes informações, que podem afetar a maneira como você escolherá agrupar as regras de firewall em seus perfis:  
- Cada perfil dá suporte a até 150 regras de firewall. Quando você usar mais de 150 regras, crie perfis adicionais, cada um limitado a 150 regras.  
- Para cada perfil, se uma única regra não for aplicada, todas as regras nesse perfil falharão e nenhuma delas será aplicada ao dispositivo.  
- Quando uma regra não for aplicada, todas as regras no perfil serão relatadas como regras com falha. O Intune não pode identificar qual regra individual falhou.  

As regras de firewall que o Intune pode gerenciar são detalhadas no CSP [(provedor de serviços de configuração) do Firewall]( https://docs.microsoft.com/windows/client-management/mdm/firewall-csp) do Windows. Para examinar a lista de configurações de firewall personalizadas para dispositivos Windows 10 compatíveis com o Intune, confira [Regras de firewall personalizadas](endpoint-protection-windows-10.md#firewall-rules).  

### <a name="to-add-custom-firewall-rules-to-an-endpoint-protection-profile"></a>Para adicionar regras de firewall personalizadas a um perfil da proteção de ponto de extremidade  

1. No Intune, acesse **Configuração do dispositivo** > **Perfis** > **Criar Perfil**.  

2. Para *Plataforma*, selecione **Windows 10 e posterior** e, em seguida, para *Tipo de perfil*, selecione **Endpoint Protection**.  

3. Selecione **Windows Defender Firewall** para abrir a página de configuração e, em seguida, em *Regras de firewall*, selecione **Adicionar** para abrir a página **Criar Regra**.  

4. Especifique as configurações para a regra de firewall e, em seguida, selecione **OK** para salvá-la. Para examinar as opções de regra de firewall personalizadas disponíveis na documentação, confira [Regras de firewall personalizadas](endpoint-protection-windows-10.md#firewall-rules).  

5. Depois que você salvar a regra, ela será exibida na página do *Windows Defender Firewall* na lista de regras.  

6. Para modificar uma regra, selecione-a na lista para abrir a página **Editar Regra**.  

7. Para excluir uma regra de um perfil, selecione as reticências **(...)** dela e, em seguida, selecione **Excluir**.  

8. Para alterar a ordem na qual as regras são exibidas, selecione o ícone de *seta para cima, seta para baixo* na parte superior da lista de regras.  


## <a name="next-steps"></a>Próximas etapas  

Para atribuir um perfil a grupos, consulte [atribuir perfis de dispositivo](device-profile-assign.md).  
