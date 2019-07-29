---
title: Relatório de criptografia para dispositivos criptografados no Microsoft Intune
titleSuffix: Microsoft Intune
description: Veja um relatório no status de criptografia de seu dispositivo iOS ou Windows e acesse as chaves de recuperação do FileVault e do BitLocker no portal do Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: shpate
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: a04a8b9f1973479fd0695ad0e782488fdef43d10
ms.sourcegitcommit: c3a4fefbac8ff7badc42b1711b7ed2da81d1ad67
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2019
ms.locfileid: "68375155"
---
# <a name="monitor-device-encryption"></a>Monitorar a criptografia do dispositivo  

O relatório de criptografia do Microsoft Intune é uma localização centralizada para exibir detalhes sobre o status de criptografia dos dispositivos gerenciados. Veja detalhes sobre o status de criptografia de um dispositivo e encontre opções para gerenciar as chaves de recuperação do dispositivo. As opções de chave de recuperação disponíveis dependem do tipo de dispositivo que está sendo exibido.  

Para localizar o relatório, entre no [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) e acesse a **Configuração do Dispositivo** e, em *Monitorar*, selecione **Relatório de criptografia**.  

## <a name="view-encryption-details"></a>Exibir detalhes de criptografia  

O relatório de criptografia mostra detalhes comuns nos dispositivos compatíveis gerenciados. As seções a seguir fornecem detalhes sobre as informações apresentadas pelo Intune no relatório.  
 
### <a name="prerequisites"></a>Pré-requisitos:  

O relatório de criptografia dá suporte a relatórios em dispositivos que executam as seguintes versões do sistema operacional:  
- macOS 10.13 ou posterior  
- Windows versão 1607 ou posterior  

### <a name="report-details"></a>Detalhes do relatório  

O painel Relatório de criptografia exibe uma lista dos dispositivos gerenciados com detalhes de alto nível sobre esses dispositivos. Você pode selecionar um dispositivo na lista para analisar e exibir detalhes adicionais no painel [Status de criptografia do dispositivo](#device-encryption-status) dos dispositivos.  

- **Nome do dispositivo** – o nome do dispositivo.  
- **Sistema operacional** – a plataforma do dispositivo, como Windows ou macOS.  
- **Versão do sistema operacional** – a versão do Windows ou do macOS no dispositivo.  
- **Versão do TPM** *(aplica-se somente ao Windows 10)* – a versão do chip TPM (Trusted Platform Module) no dispositivo Windows 10.  
- **Preparação de criptografia** – uma avaliação da preparação dos dispositivos para dar suporte a uma tecnologia de criptografia aplicável, como a criptografia BitLocker ou FileVault. Os dispositivos são identificados como:  
  - **Pronto**: O dispositivo pode ser criptografado usando a política de MDM, o que exige que o dispositivo atenda aos seguintes requisitos:  
    
    **Para dispositivos macOS**:  
    - macOS versão 10.13 ou posterior  
    
    **Para dispositivos Windows 10**:  
    - Versão 1703 ou posterior do *Business*, *Enterprise* ou *Education*; ou versão 1809 ou posterior do *Pro*  
    - O dispositivo precisa ter um chip TPM  
    
    Para saber mais, confira o [CSP (provedor de serviço de configuração) do BitLocker](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) na documentação do Windows.  

  - **Não está pronto**: o dispositivo não tem funcionalidades de criptografia completas, mas ainda dá suporte à criptografia. Por exemplo, um dispositivo Windows pode ser criptografado manualmente por um usuário ou por meio da Política de Grupo que pode ser definida para permitir a criptografia sem um TMP.
  - **Não aplicável**: Não há informações suficientes para classificar esse dispositivo.  

- **Status da criptografia** – indica se a unidade do sistema operacional é criptografada.  

- **Nome UPN** – o usuário primário do dispositivo.  

### <a name="device-encryption-status"></a>Status da criptografia do dispositivo  

Quando você seleciona um dispositivo no Relatório de criptografia, o Intune exibe o painel **Status de criptografia do dispositivo**. O painel fornece os seguintes detalhes:  

- **Nome do dispositivo** – o nome do dispositivo que você está exibindo.  

- **Preparação de criptografia** – uma avaliação de preparação dos dispositivos para dar suporte à criptografia por meio da política de MDM.  
  
  Por exemplo: Quando um dispositivo Windows 10 tem uma preparação igual a *Não pronto*, ele ainda pode dar suporte à criptografia. Para ter a designação *Pronto*, o dispositivo Windows 10 precisa ter um chip TPM. Os chips TPM não são necessários para dar suporte à criptografia. (Confira a preparação da criptografia na seção anterior para obter mais detalhes.)  

- **Status da criptografia** – Se a unidade do sistema operacional é criptografada. Podem ser necessárias até 24 horas para que o Intune relate um status de criptografia de um dispositivo ou uma alteração nesse status.  

- **Perfis** – uma lista dos perfis de *Configuração do dispositivo* que se aplicam a esse dispositivo e são configurados com os seguintes valores:  

  - macOS:
    - Tipo de perfil = *Endpoint Protection*  
    - Configurações > FileVault > FileVault = *Habilitar*

  - Windows 10:
    - Tipo de perfil = *Endpoint Protection*  
    - Configurações > Criptografia do Windows > Criptografar dispositivos = *Necessário*  

  Use a lista de perfis para identificar políticas individuais para análise caso o *Resumo do estado de perfil* indique problemas.  

- **Resumo do estado de perfil** – Um resumo dos perfis que se aplicam a esse dispositivo. O resumo representa a condição menos favorável nos perfis aplicáveis. Por exemplo, se apenas um dos vários perfis aplicáveis resultar em um erro, o *Resumo do estado de perfil* exibirá um *Erro*.  

- **Detalhes de status** – Detalhes avançados sobre o estado de criptografia do dispositivo.  
  > [!NOTE]
  > O suporte para o FileVault é limitado até a conclusão da distribuição da versão de julho em alguns dias. Até que a distribuição seja concluída, os detalhes de status do dispositivo e os detalhes de criptografia do dispositivo para o macOS podem não ser exibidos com precisão no relatório de criptografia.

  > [!IMPORTANT]  
  > Para dispositivos Windows 10, o Intune só mostra os *Detalhes de status* para dispositivos que executam a *Atualização de 10 de abril de 2019 do Windows* ou posterior.  
  
  Esse campo exibe informações para cada erro aplicável que possa ser detectado. É possível usar essas informações para entender por que um dispositivo talvez não esteja pronto para a criptografia.  

  Veja a seguir exemplos dos detalhes do status que o Intune pode relatar:  
  
  **macOS**:
  - O perfil não pode ser instalado no momento, pois estamos aguardando um pré-requisito.  
 
    *Considere: Esse resultado não representa necessariamente uma condição de erro, mas um estado temporário que pode ocorrer devido ao tempo no dispositivo durante o qual a caução para as chaves de recuperação precisa ser configurada antes que a solicitação de criptografia seja enviada ao dispositivo. Isso também pode indicar que o dispositivo permanece bloqueado ou não fez check-in no Intune recentemente. Por fim, como a criptografia FileVault não será iniciada enquanto um dispositivo não for conectado (carregando), é possível que um usuário receba uma chave de recuperação para um dispositivo que ainda não está criptografado*.  

  - O perfil do FileVault está instalado, mas o FileVault não está habilitado no dispositivo.  
 
    *Considere: O usuário ainda não fez logoff depois de receber a solicitação de criptografia, o que é necessário antes que o FileVault possa criptografar o dispositivo, ou o usuário descriptografou o dispositivo manualmente. O Intune não pode impedir que um usuário descriptografe seu dispositivo.*  

  - O FileVault já está habilitado pelo usuário e, portanto, o Intune não pode gerenciar sua recuperação.  
 
    *Considere: O Intune não pode configurar o FileVault em um dispositivo que já está criptografado. Em vez disso, o usuário precisa descriptografar seu dispositivo manualmente antes que ele possa ser gerenciado por uma política de configuração de dispositivos e pelo Intune*. 
 
  - O FileVault precisa que o usuário aprove seu perfil de gerenciamento no macOS Catalina e posterior.  
 
    *Considere: No macOS versão 10.15 (Catalina) em diante, as configurações de Registro aprovadas pelo usuário podem exigir que os usuários aprovem manualmente a criptografia FileVault. Para obter mais informações, confira [Registro aprovado pelo usuário](macos-enroll.md) na documentação do Intune*.  

  - O dispositivo iOS retornou um NotNow (ele está bloqueado).  

    *Considere: O dispositivo está bloqueado no momento, e o Intune não pode iniciar o processo de caução nem de criptografia. Depois que o dispositivo for desbloqueado, o progresso poderá continuar*.  

  **Windows 10**:  
  - A política do BitLocker requer o consentimento do usuário para iniciar o Assistente de Criptografia de Unidade de Disco BitLocker para iniciar a criptografia do volume do sistema operacional, mas o usuário não consentiu.  
  
  - O método de criptografia do volume do sistema operacional não coincide com a política do BitLocker.  
  
  - A política do BitLocker exige um protetor de TPM para proteger o volume do sistema operacional, mas um TPM não é usado.  
  
  - A política do BitLocker exige um protetor somente de TPM para o volume do sistema operacional, mas a proteção do TPM não é usada.  
  
  - A política do BitLocker exige uma proteção TPM+PIN para o volume do sistema operacional, mas um protetor TPM+PIN não é usado.  
  
  - A política do BitLocker exige uma proteção de chave de inicialização+TPM para o volume do sistema operacional, mas um protetor de chave de inicialização+TPM não é usado.  
  
  - A política do BitLocker exige uma proteção de chave de inicializaçãoTPM+PIN para o volume do sistema operacional, mas um protetor de chave de inicializaçãoTPM+PIN não é usado.  
  
  - O volume do sistema operacional está desprotegido.  
  
  - Falha no backup da chave de recuperação.  
  
  - Uma unidade fixa está desprotegida.  
  
  - O método de criptografia da unidade fixa não coincide com a política do BitLocker.  
  
  - Para criptografar unidades, a política do BitLocker exige que o usuário entre como um Administrador ou, se o dispositivo for ingressado no Azure AD, a política AllowStandardUserEncryption deverá ser definida como 1.  
  
  - O WinRE (Ambiente de Recuperação do Windows) não está configurado.  
  
  - Não há um TPM disponível para o BitLocker, porque ele não está presente, ficou indisponível no Registro ou o sistema operacional está em uma unidade de disco removível.  
  
  - O TPM não está pronto para o BitLocker.  
  
  - A rede não estiver disponível, o que é necessário para o backup da chave de recuperação.  

## <a name="export-report-details"></a>Exportar detalhes do relatório 
Ao exibir o painel Relatório de criptografia, você pode selecionar **Exportar** para criar um download de arquivo *.csv* dos detalhes do relatório.  Esse relatório inclui os detalhes de alto nível do painel *Relatório de criptografia* e os detalhes do *Status de criptografia do dispositivo* para cada dispositivo gerenciado.   
 
  
![Exportar detalhes](./media/encryption-monitor/export.png) 
 
Esse relatório pode ser usado para identificar problemas de grupos de dispositivos. Por exemplo, você pode usar o relatório para identificar uma lista de todos os dispositivos macOS que relatam a mensagem *O FileVault já foi habilitado pelo usuário*, o que indica os dispositivos que precisam ser descriptografados manualmente antes que o Intune possa começar a gerenciar suas configurações do FileVault.  
 
## <a name="filevault-recovery-keys"></a>Chaves de recuperação do FileVault   
Quando o Intune criptografa um dispositivo macOS com o FileVault pela primeira vez, uma chave de recuperação pessoal é criada. Após a criptografia, o dispositivo exibe a chave pessoal uma única vez para o usuário final.  
 
Para os dispositivos gerenciados, o Intune pode habilitar a caução de uma cópia da chave de recuperação pessoal. A caução de chaves permite que os administradores do Intune girem as chaves para ajudar a proteger os dispositivos e que os usuários recuperem uma chave de recuperação pessoal perdida ou girada.  
 
O Intune dá suporte a várias opções para girar e recuperar chaves de recuperação pessoal. Um motivo para girar uma chave é se a chave pessoal atual foi perdida e considerada em risco.  
 
> [!IMPORTANT]  
>  Os dispositivos criptografados por usuários e não pelo Intune não podem ser gerenciados pelo Intune. Isso significa que o Intune não pode habilitar a caução da recuperação pessoal desses dispositivos nem gerenciar a rotação da chave de recuperação.  Para que o Intune gerencie o FileVault e as chaves de recuperação do dispositivo, o usuário precisará descriptografar seu dispositivo e, em seguida, permitir que o Intune criptografe o dispositivo.  

### <a name="rotate-recovery-keys"></a>Girar as chaves de recuperação  

- **Rotação automática**: Como administrador, você pode configurar o FileVault definindo a rotação de chave de recuperação pessoal para gerar de forma automática novas chaves de recuperação periodicamente.  Quando uma nova chave é gerada para um dispositivo, a chave não é exibida para o usuário. Em vez disso, o usuário precisa obter a chave de um administrador ou usando o aplicativo Portal da Empresa.  

- **Rotação manual**: Como administrador, você pode exibir informações de um dispositivo gerenciado com o Intune, e isso é criptografado com o FileVault. Você pode optar por girar manualmente a chave de recuperação para dispositivos corporativos. Não é possível girar as chaves de recuperação para dispositivos pessoais.  

  Para girar uma chave de recuperação: 
  1. Entre no [Intune](https://go.microsoft.com/fwlink/?linkid=2090973), acesse **Dispositivos** e, em seguida, em Gerenciar, selecione  **Todos os dispositivos**.  
  2. Na lista de dispositivos, selecione o dispositivo que está criptografado e para o qual você deseja girar sua chave. Em seguida, em Monitor, selecione **Chaves de recuperação**.  
  3. No painel Chaves de recuperação, selecione **Girar chave de recuperação do FileVault**.  
  
     Na próxima vez que o dispositivo fizer check-in no Intune, a chave pessoal será girada. Quando necessário, a nova chave pode ser obtida pelo usuário final por meio do Portal da Empresa. 


### <a name="recover-recovery-keys"></a>Recuperar chaves de recuperação  
- **Administrador**: Os administradores não podem exibir chaves de recuperação pessoal de dispositivos que são criptografados com o FileVault.  

- **Usuário final**: Os usuários finais usam o site do Portal da Empresa em qualquer dispositivo para exibir a chave de recuperação pessoal atual de um de seus dispositivos gerenciados. Não é possível exibir as chaves de recuperação no aplicativo Portal da Empresa.  

 
  Para exibir uma chave de recuperação:  
  1. Entre no site do *Portal da Empresa do Intune* em qualquer dispositivo.  
  2. No portal, acesse **Dispositivos** e selecione o dispositivo macOS que está criptografado com o FileVault.  
  3. Selecione **Obter chave de recuperação**. A chave de recuperação atual será exibida.  
  
     Em um iPhone, você precisa selecionar os *três* pontos antes que a opção *Obter chave de recuperação* seja exibida.  

## <a name="bitlocker-recovery-keys"></a>Chaves de recuperação do BitLocker  

O Intune fornece acesso à folha do Azure AD para o BitLocker. Assim, é possível exibir as IDs de chave do BitLocker e as chaves de recuperação para seus dispositivos Windows 10 de dentro do portal do Intune.  Para ser acessível, o dispositivo deve ter suas chaves mantidas sob a custódia do Azure AD. 
1. Entre no [Intune](https://go.microsoft.com/fwlink/?linkid=2090973), acesse **Dispositivos** e, em seguida, em *Gerenciar*, selecione **Todos os dispositivos**.  

2. Selecione um dispositivo na lista e em *Monitorar*, selecione **Chaves de recuperação**.  
  
Quando as chaves estiverem disponíveis no Azure AD, as seguintes informações ficarão disponíveis:
- ID de chave do BitLocker  
- Chave de recuperação do BitLocker  
- Tipo de Unidade  

Quando as chaves não estiverem no Azure AD, o Intune exibirá *Nenhuma chave do BitLocker encontrada para este dispositivo*.  

As informações do BitLocker são obtidas usando o [CSP (provedor de serviço de configuração) do BitLocker](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp). O CSP do BitLocker é compatível com o Windows 10 versão 1703 e posterior e com o Windows 10 Pro versão 1809 e posterior.  

## <a name="next-steps"></a>Próximas etapas  

Crie uma política de [conformidade do dispositivo](compliance-policy-create-windows.md).