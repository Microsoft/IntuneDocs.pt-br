---
title: Criptografar dispositivos no Microsoft Intune usando os métodos de criptografia compatíveis com as plataformas
titleSuffix: Microsoft Intune
description: Criptografe dispositivos com métodos de criptografia internos, como BitLocker ou FileVault, e gerencie as chaves de recuperação desses dispositivos criptografados no portal do Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 08/02/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: annovich
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 09b5e59f4af534d4919574631568a7581bb3fba9
ms.sourcegitcommit: 73fbecf7cee4fdfc37d3c30ea2007d2a9a6d2d12
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/03/2019
ms.locfileid: "68756536"
---
# <a name="use-device-encryption-with-intune"></a>Usar a Criptografia do Dispositivo com o Intune  

Use o Intune para gerenciar um disco interno de dispositivos ou a criptografia de unidade para proteger os dados em seus dispositivos.  

Configure a criptografia de disco como parte de um perfil de configuração do dispositivo para a proteção de ponto de extremidade. As seguintes plataformas e tecnologias de criptografia são compatíveis com o Intune:  
- macOS: FileVault   
- Windows 10 e posterior: BitLocker  

O Intune também fornece um [relatório de criptografia](encryption-monitor.md) interno que apresenta detalhes sobre o status de criptografia dos dispositivos em todos os dispositivos gerenciados.  

## <a name="filevault-encryption-for-macos"></a>Criptografia FileVault para macOS  

Use o Intune para configurar a criptografia de disco do FileVault em dispositivos que executam o macOS. Em seguida, use o relatório de criptografia do Intune para exibir os detalhes de criptografia desses dispositivos e gerenciar as chaves de recuperação dos dispositivos criptografados pelo FileVault.  

O FileVault é um programa de criptografia de disco completo incluído no macOS. Você pode usar o Intune para configurar o FileVault em dispositivos que executam o **macOS 10.13 ou posterior**.  

Para configurar o FileVault, crie um [perfil de configuração do dispositivo](device-profile-create.md) para proteção de ponto de extremidade na plataforma macOS. As configurações do FileVault são uma das categorias de configurações disponíveis para a proteção de ponto de extremidade do macOS.  

Depois que você criar uma política para criptografar dispositivos com o FileVault, a política será aplicada aos dispositivos em dois estágios. Primeiro, o dispositivo é preparado para habilitar o Intune, a fim de recuperar e fazer backup da chave de recuperação. Isso é chamado de caução. Depois que a chave for habilitada para caução, a criptografia de disco poderá ser iniciada.

![Configurações do FileVault](./media/encrypt-devices/filevault-settings.png)

Para obter detalhes sobre a configuração do FileVault que pode ser gerenciada com o Intune, confira [FileVault](endpoint-protection-macos.md#filevault) no artigo sobre o Intune para obter as configurações de proteção de ponto de extremidade do macOS.  

### <a name="how-to-configure-macos-filevault"></a>Como configurar o FileVault do macOS 

1. Entre no [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) e acesse **Configuração do dispositivo** > **Perfis** > **Criar perfil**.  

2. Defina as seguintes opções:  

   - Plataforma: macOS  
   - Tipo de perfil: Endpoint Protection  

3. Selecione **Configurações** > **FileVault**.  

4. Para *FileVault*, selecione **Habilitar**.  

5. Para *Tipo de chave de recuperação*, só há suporte para **Chave pessoal**.  

   Considere a adição de uma mensagem para ajudar a orientar os usuários finais sobre como recuperar a chave de recuperação para seus dispositivos. Essas informações poderão ser úteis para os usuários finais quando você usar a configuração para rotação de chave de recuperação pessoal, que pode gerar automaticamente uma nova chave de recuperação para um dispositivo periodicamente.  

   Por exemplo: Para recuperar uma chave de recuperação perdida ou recentemente girada, entre no site do Portal da Empresa do Intune em qualquer dispositivo. No portal, acesse *Dispositivos* e selecione o dispositivo que tem o FileVault habilitado e, em seguida, selecione *Obter chave de recuperação*. A chave de recuperação atual será exibida.  

6. Defina as configurações restantes do [FileVault](endpoint-protection-macos.md#filevault) de acordo com suas necessidades de negócios e, em seguida, escolha **OK**.  

   > [!IMPORTANT]  
   > Há um problema conhecido quando a configuração **Desabilitar prompt na saída** está definida como *Habilitar*. Quando definida como *Habilitar*, a configuração **Número de vezes permitido para bypass** deve ter um valor e não deve estar definida como *Não configurado*. Se estiver definida como *Não configurado*, o perfil falhará no dispositivo. Nesse cenário, o dispositivo informa que é um **Resumo de estado de perfil** como **Erro** sem mais detalhes.
   > 
   > Quando **Desabilitar prompt na saída** estiver definida como *Não configurado*, o **Número de vezes permitido para bypass** pode ser *Não configurado* ou ter um valor.  
   > 
   > Esse problema será resolvido em uma atualização futura. 

7. Conclua a definição de configurações adicionais e, em seguida, salve o perfil.  

### <a name="manage-filevault"></a>Gerenciar o FileVault  

Depois que o Intune criptografar um dispositivo macOS com o FileVault, você poderá exibir e gerenciar as chaves de recuperação do FileVault ao exibir o [relatório de criptografia](encryption-monitor.md) do Intune.  

## <a name="bitlocker-encryption-for-windows-10"></a>Criptografia BitLocker para o Windows 10  

Use o Intune para configurar a Criptografia de Unidade de Disco BitLocker em dispositivos que executam o Windows 10. Em seguida, use o relatório de criptografia do Intune para exibir detalhes de criptografia desses dispositivos. Acesse também informações importantes do BitLocker em seus dispositivos, conforme encontrado no Azure AD (Azure Active Directory).  

O BitLocker está disponível em dispositivos que executam o **Windows 10 ou posterior**.  

Configure o BitLocker ao criar um [perfil de configuração de dispositivo](device-profile-create.md) para proteção de ponto de extremidade na plataforma Windows 10 ou posterior. As configurações do BitLocker estão na categoria de configurações da Criptografia do Windows para a proteção de ponto de extremidade do Windows 10.    

![Configurações do BitLocker](./media/encrypt-devices/bitlocker-settings.png) 

### <a name="how-to-configure-windows-10-bitlocker"></a>Como configurar o BitLocker do Windows 10  

1. Entre no [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) e acesse Configuração do dispositivo > Perfis > Criar perfil.  

2. Defina as seguintes opções:  
   - Plataforma: Windows 10 e posterior  
   - Tipo de perfil: Endpoint Protection  

3. Selecione **Configurações** > **Criptografia do Windows**.

4. Defina as configurações do BitLocker de acordo com suas necessidades de negócios e, em seguida, selecione **OK**.  

5. Conclua a definição de configurações adicionais e, em seguida, salve o perfil.  

### <a name="manage-bitlocker"></a>Gerenciar o BitLocker  

Depois que o Intune criptografar um dispositivo Windows 10 com o BitLocker, você poderá exibir e recuperar as chaves de recuperação do BitLocker ao exibir o [relatório de criptografia](encryption-monitor.md) do Intune.  

## <a name="next-steps"></a>Próximas etapas  

Criar uma política de [conformidade do dispositivo](compliance-policy-create-windows.md)  

Use o relatório de criptografia para gerenciar:  
- [Chaves de recuperação do BitLocker](encryption-monitor.md#bitlocker-recovery-keys)
- [Chaves de recuperação do FileVault](encryption-monitor.md#filevault-recovery-keys)

Examine as configurações de criptografia que você pode configurar com o Intune para o:  
- [BitLocker](endpoint-protection-windows-10.md#windows-encryption)  
- [FileVault](endpoint-protection-macos.md#filevault)  
 
 
