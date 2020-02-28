---
title: Dicas de solução de problemas para políticas do BitLocker no Microsoft Intune
titleSuffix: Microsoft Intune
description: Descreve como habilitar a criptografia do BitLocker em um dispositivo usando a política do Intune e como verificar se a política foi implantada com êxito em um dispositivo.
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/29/2020
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f3b32268d0b04dee84a737b9a1c768bc4fab7202
ms.sourcegitcommit: 3964e6697b4d43e2c69a15e97c8d16f8c838645b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "77556492"
---
# <a name="troubleshoot-bitlocker-policies-in-microsoft-intune"></a>Solucionar problemas com políticas do BitLocker no Microsoft Intune

Este artigo pode ajudar administradores do Intune a entender como dispositivos Windows 10 configuram o BitLocker com base na política do Intune. Ele também fornece orientações sobre como solucionar problemas com as configurações do BitLocker em dispositivos gerenciados com o Intune.  

## <a name="understanding-bitlocker"></a>Noções básicas sobre o BitLocker

A criptografia de unidade de disco BitLocker é um serviço oferecido pelos sistemas operacionais Microsoft Windows que permite que os usuários criptografem dados em seus discos rígidos. O BitLocker dá suporte à criptografia para unidades do sistema operacional, unidades de mídia removível e unidades de dados fixas. O BitLocker também dá suporte ao uso de criptografia de 256 bits para melhor proteção de dados confidenciais.  

Com o Microsoft Intune, você conta com os seguintes métodos para gerenciar o BitLocker em dispositivos Windows 10:

- **Políticas de configuração de dispositivo** – algumas opções de políticas internas estão disponíveis no Intune quando você cria um perfil de configuração de dispositivo para gerenciar a proteção do ponto de extremidade. Para encontrar essas opções, [crie um perfil de dispositivo para proteção do ponto de extremidade](endpoint-protection-configure.md#create-a-device-profile-containing-endpoint-protection-settings), selecione **Windows 10 e posterior** como *Plataforma* e, em seguida, selecione a categoria **Criptografia do Windows** para *Configurações*. 

   Leia sobre as opções e recursos disponíveis aqui: [Criptografia do Windows](https://docs.microsoft.com/intune/endpoint-protection-windows-10#windows-encryption).

- **Linhas de base de segurança** - [Linhas de base de segurança](security-baselines.md) são grupos conhecidos de configurações e valores padrão que são recomendados pela equipe de segurança relevante para ajudar a proteger dispositivos Windows. Fontes de linhas de base diferentes, como a *Linha de Base de Segurança do MDM* ou a *Linha de Base do Microsoft Defender ATP*, podem gerenciar as mesmas configurações, bem como configurações diferentes umas das outras. Elas também podem gerenciar as mesmas configurações que você gerencia usando as políticas de configuração de dispositivo. 

Além do Intune, para hardwares compatíveis com o Modo de Espera Moderno e o HSTI, ao usar qualquer um desses recursos, a Criptografia de Dispositivo do BitLocker é ativada automaticamente sempre que o usuário ingressa um dispositivo no Azure AD. O Azure AD fornece um portal em que também é feito backup das chaves de recuperação, para que os usuários possam recuperar sua própria chave de recuperação para autoatendimento, se necessário.

Também é possível gerenciar as configurações do BitLocker de outras formas, como com a Política de Grupo ou com a definição manual por um usuário do dispositivo.

Qualquer que seja a maneira como as configurações são aplicadas a um dispositivo, as políticas do BitLocker usam o [CSP do BitLocker](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) para configurar a criptografia no dispositivo. O CSP do BitLocker é integrado ao Windows e, quando o Intune implanta uma política do BitLocker em um dispositivo atribuído, é o CSP do BitLocker no dispositivo que grava os valores adequados no Registro do Windows para que as configurações da política possam entrar em vigor.

Se quiser saber mais sobre o BitLocker, consulte estes recursos:

- [BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)
- [Visão geral e perguntas frequentes sobre os requisitos do BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview-and-requirements-faq)

Agora que tem uma compreensão geral do que essas políticas fazem e de como funcionam, veja como você pode verificar se as configurações do BitLocker se aplicam com êxito a um cliente do Windows.

## <a name="verify-the-source-of-bitlocker-settings"></a>Verificar a origem das configurações do BitLocker

Ao investigar um problema com o BitLocker em um dispositivo Windows 10, é importante determinar primeiro se o problema está relacionado ao Intune ou ao Windows. Depois que a origem provável da falha for conhecida, você poderá concentrar seus esforços de solução de problemas no lugar certo e, se necessário, obter suporte da equipe correta.  

Como uma primeira etapa, determine se a política do Intune foi implantada com êxito no dispositivo de destino. No exemplo a seguir, você tem uma política de configuração de dispositivo que implanta as configurações de Criptografia do Windows (BitLocker), conforme mostrado:

![Política de configuração de dispositivo da Criptografia do Windows com as configurações](./media/troubleshooting-bitlocker-policies/settings.png)

Como você confirma que as configurações foram aplicadas ao dispositivo de destino? Veja a seguir algumas maneiras de fazer isso.

### <a name="device-configuration-policy-device-status"></a>Status do dispositivo com a política de configuração de dispositivo  

Ao usar a política de Configuração de Dispositivo para configurar o BitLocker, você pode verificar o status da política no portal do Intune.

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecione **Dispositivos** > **Perfis de configuração** e, em seguida, selecione o perfil que contém as configurações do BitLocker.

3. Depois de selecionar o perfil que deseja exibir, selecione **Status do Dispositivo**. Os dispositivos atribuídos ao perfil são listados e a coluna *Status do dispositivo* indica se um dispositivo implantou o perfil com êxito.

Lembre-se de que pode haver um atraso entre o recebimento da política do BitLocker pelo dispositivo e a criptografia completa da unidade.  

### <a name="use-control-panel-on-the-client"></a>Usar o Painel de Controle no cliente  

Em um dispositivo que habilitou o BitLocker e criptografou uma unidade, você pode exibir o status do BitLocker no Painel de Controle de dispositivos. No dispositivo, abra **Painel de Controle** > **Sistema e Segurança** > **Criptografia de Unidade de Disco BitLocker**. A confirmação aparece conforme mostrado na imagem a seguir.  

![O BitLocker está ativado no Painel de Controle](./media/troubleshooting-bitlocker-policies/control-panel.png)

### <a name="use-a-command-prompt"></a>Usar um prompt de comando  

Em um dispositivo que habilitou o BitLocker e criptografou uma unidade, inicie o Prompt de Comando com credenciais de administrador e, em seguida, execute `manage-bde -status`. Os resultados devem se parecer com o exemplo a seguir:  
![Resultado do comando de status](./media/troubleshooting-bitlocker-policies/command.png)

No exemplo:

- A **Proteção do BitLocker** está **Ativada**
- O **Percentual Criptografado** é **100%**
- O **Método de Criptografia** é **XTS-AES 256**

Você também pode verificar os **Protetores de Chave** executando o seguinte comando:

```cmd
Manage-bde -protectors -get c:
```

Ou com o PowerShell:

```powershell
Confirm-SecureBootUEFI
```

### <a name="review-the-devices-registry-key-configuration"></a>Examinar a configuração da chave do Registro do dispositivo

Após a política do BitLocker ser implantada com êxito em um dispositivo, veja a seguinte chave do Registro no dispositivo, em que é possível examinar as configurações do BitLocker:  *HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PolicyManager\current\device\BitLocker*. Aqui está um exemplo:

![Chave do Registro do BitLocker](./media/troubleshooting-bitlocker-policies/registry.png)

Esses valores são configurados pelo CSP do BitLocker. Verifique se os valores das chaves correspondem às configurações especificadas na origem de sua política de Criptografia do Windows do Intune. Para saber mais sobre cada uma dessas configurações, confira [CSP do BitLocker](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp).

> [!NOTE]
> O Visualizador de Eventos do Windows também contém várias informações relacionadas ao BitLocker. Há muitas para listar aqui, mas pesquisar por **API do BitLocker** levará a muitas informações úteis.

### <a name="check-the-mdm-diagnostics-report"></a>Verificar o relatório de diagnóstico do MDM

Em um dispositivo com o BitLocker habilitado, você pode gerar e exibir um relatório de diagnóstico do MDM usando o dispositivo de destino para confirmar se a política do BitLocker está presente. Quando você vê as configurações de política no relatório, essa é outra indicação de que a política foi implantada com êxito. O vídeo *Ajudas da Microsoft* no seguinte link explica como capturar um relatório de diagnóstico do MDM em um dispositivo Windows.

> [!VIDEO https://www.youtube.com/embed/WKxlcjV4TNE]

Quando você analisa o relatório de diagnóstico do MDM, o conteúdo pode parecer um pouco confuso em princípio. Veja a seguir um exemplo de como correlacionar o que está no relatório com as configurações de uma política:

![Exemplo de relatório de diagnóstico do MDM](./media/troubleshooting-bitlocker-policies/report.png)

O resultado da saída mostra os valores correspondentes aos valores de sua política do BitLocker:

![O resultado de saída mostra os valores ](./media/troubleshooting-bitlocker-policies/output.png)

Resultados de saída do diagnóstico do MDM:

```asciidoc
EncryptionMethodWithXtsOsDropDown: 7 (The value 7 refers to the 256 bit encryption)
EncryptionMethodWithXtsFdvDropDown: 6 (The value 6 refers to the 128 bit encryption)
EncryptionMethodWithXtsRdvDropDown: 6 (The value 6 refers to the 128 bit encryption)
```

Confira a [Documentação do CSP do BitLocker](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) para ver o que cada valor significa. Para este exemplo, um trecho de conteúdo é compartilhado na imagem a seguir.

![Finalidades dos valores](./media/troubleshooting-bitlocker-policies/shared-example.png)

Da mesma forma, você pode ver todos os valores e verificá-los no link do CSP do BitLocker.

> [!TIP]
> A principal finalidade do relatório de diagnóstico do MDM é ajudar a Suporte da Microsoft no processo de solução de problemas. Se você abrir um caso de suporte referente ao Intune e o problema envolver clientes Windows, sempre será uma boa ideia coletar esse relatório e incluí-lo na solicitação de suporte.

## <a name="troubleshooting-bitlocker-policy"></a>Solução de problemas com a política do BitLocker

Agora, você deve ter uma boa ideia de como confirmar se a política do BitLocker foi implantada com êxito pelo Intune, que transfere a configuração do BitLocker para o CSP do BitLocker no Windows.

**A política não chega ao dispositivo** – quando sua política do Intune não está presente em nenhuma capacidade:

- **O dispositivo foi registrado corretamente no Microsoft Intune?** Se não tiver sido, você precisará cuidar disso antes de solucionar qualquer problema específico da política. É possível encontrar ajuda para solucionar problemas de registro do Windows [aqui](../enrollment/troubleshoot-windows-enrollment-errors.md).

- **Há uma conexão de rede ativa no dispositivo?** Se o dispositivo estiver no modo avião ou estiver desligado ou se o usuário estiver com o dispositivo em um local sem serviço, a política não será entregue nem aplicada até que a conectividade com a rede seja restaurada.

- **A política do BitLocker foi implantada no usuário ou grupo de dispositivos correto?** Verifique se o usuário ou o dispositivo correto é membro dos grupos que você tem como destino.

**A política está presente, mas nem todas as configurações foram definidas com êxito** – quando a política do Intune chega ao dispositivo, mas nem todas as configurações são definidas:

- **A implantação de toda a política falhou ou somente algumas configurações não se aplicam?** Se estiver lidando com um cenário em que apenas algumas configurações da política não se aplicam, verifique o seguinte:

  1. **Nem todas as configurações do BitLocker têm suporte em todas as versões do Windows**.
     A política chega ao dispositivo como uma unidade, portanto, se algumas configurações foram aplicadas e outras não, saiba que a política foi recebida. Nesse cenário, é possível que a versão do Windows no dispositivo não dê suporte às configurações problemáticas. Confira [CSP do BitLocker](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) na documentação do Windows para obter detalhes sobre os requisitos de versão de cada configuração.

  2. **O BitLocker não tem suporte em todos os hardwares**.
     Mesmo que você tenha a versão correta do Windows, é possível que o hardware do dispositivo subjacente não atenda aos requisitos de criptografia do BitLocker. Você pode encontrar os [requisitos de sistema do BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview#system-requirements) na documentação do Windows, mas o principal a verificar é se o dispositivo tem um chip TPM compatível (1.2 ou posterior) e um BIOS compatível com TCG (Trusted Computing Group) ou um firmware UEFI.
     
A **Criptografia do BitLocker não é executada silenciosamente** – você configurou uma política do Endpoint Protection com a configuração "Aviso para outra criptografia de disco" definida para bloquear e o assistente de criptografia ainda aparece:

- **Confirme se a versão do Windows dá suporte à criptografia silenciosa** Isso requer, no mínimo, a versão 1803. Se o usuário não é um administrador do dispositivo, isso requer uma versão mínima de 1809. Além disso, a versão 1809 adicionou suporte para dispositivos que não dão suporte à Espera Moderna

O **Dispositivo criptografado pelo BitLocker aparece como Não compatível com as políticas de conformidade do Intune** – o problema ocorre quando a criptografia do BitLocker não é concluída. Com base em fatores como o tamanho do disco, o número de arquivos e as configurações do BitLocker, a criptografia do BitLocker pode levar muito tempo. Após a conclusão da criptografia, o dispositivo aparecerá como compatível. Os dispositivos também podem ficar temporariamente fora de conformidade imediatamente após uma instalação recente das atualizações do Windows.

Os **dispositivos são criptografados usando o algoritmo de 128 bits quando a política especifica o de 256 bits** – por padrão, o Windows 10 criptografa as unidades com a criptografia XTS-AES de 128 bits. Consulte este guia para [Definir a criptografia de 256 bits para o BitLocker durante o Autopilot](https://techcommunity.microsoft.com/t5/intune-customer-success/setting-256-bit-encryption-for-bitlocker-during-autopilot-with/ba-p/323791#).


**Exemplo de investigação**

- Você implanta uma política do BitLocker em um dispositivo Windows 10 e a configuração **Criptografar dispositivos** mostra um status de **Erro** no portal.

- Como o nome sugere, essa configuração permite que o administrador exija a ativação da criptografia usando *BitLocker > Criptografia de Dispositivo*. Usando as dicas de solução de problemas mencionadas anteriormente, primeiro você verifica o relatório de Diagnóstico do MDM. O relatório confirma se a política correta foi implantada no dispositivo:

  ![O relatório confirma se a política correta está implantada no dispositivo](./media/troubleshooting-bitlocker-policies/mdm-report.png)

- Também é possível verificar o sucesso no registro:

  ![O valor de registro RequiredDeviceEncryption mostra 1](./media/troubleshooting-bitlocker-policies/registry-confirm.png)

- Em seguida, você verifica o status do TPM usando o PowerShell e descobre que ele não está disponível no dispositivo:

  ![Status do TPM verificado usando o PowerShell](./media/troubleshooting-bitlocker-policies/tpm-command.png)

- Como o BitLocker depende do TPM, você pode concluir que o BitLocker não falhou devido a um problema com o Intune ou com a política, mas porque o dispositivo não tem um chip TPM ou o TPM está desabilitado no BIOS.

  Outra dica é que você pode confirmar o mesmo no Visualizador de Eventos do Windows em **Log de Aplicativos e Serviços** > **Microsoft** > **Windows** > **API do BitLocker**. No log de eventos da **API do BitLocker**, você encontrará a ID de Evento 853, que significa que o TPM não está disponível:

  ![ID do evento 853](./media/troubleshooting-bitlocker-policies/event-error.png)

  > [!NOTE]
  > Você também pode verificar o status do TPM executando **tpm.msc** no dispositivo.

## <a name="summary"></a>Resumo

Quando você soluciona problemas com a política do BitLocker usando o Intune e confirma que a política atingiu o dispositivo pretendido, é seguro supor que o problema não está diretamente relacionado ao Intune. É mais provável que se trate de um problema com o sistema operacional Windows ou com o hardware. Nesse caso, comece a examinar outras áreas, como a configuração do TPM, a UEFI e a inicialização segura.

## <a name="next-steps"></a>Próximas etapas  

Veja a seguir mais recursos que podem ajudar quando você trabalha com o BitLocker:

- [Documentação de produto do BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)
- [Requisitos de sistema do BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview#system-requirements)
- [Perguntas frequentes sobre o BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions)
- [Documentação do CSP do BitLocker](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp)
- [Configurações de política de Criptografia do Windows do Intune](https://docs.microsoft.com/intune/endpoint-protection-windows-10#windows-encryption)
- [Criptografia automática independente de hardware do BitLocker usando AAD/MDM](https://blogs.technet.microsoft.com/home_is_where_i_lay_my_head/2017/06/07/hardware-independent-automatic-bitlocker-encryption-using-aadmdm/)
- [Política do CSP para Criptografia do BitLocker em dispositivos com AutoPilot](https://techcommunity.microsoft.com/t5/Windows-10-security/CSP-policy-for-bitLocker-encryption-on-autopilot-devices/m-p/284537)
- [Passo a passo da criação e implantação da política do BitLocker com o Intune](https://blogs.technet.microsoft.com/cbernier/2017/07/11/windows-10-intune-windows-bitlocker-management-yes/)
