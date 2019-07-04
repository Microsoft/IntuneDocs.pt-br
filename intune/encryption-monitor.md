---
title: Relatório de criptografia e chaves BitLocker no Microsoft Intune
titleSuffix: Microsoft Intune
description: Exiba um relatório em seu status de criptografia do dispositivo e acesse as chaves de recuperação do BitLocker de dentro do portal do Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: shpate
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: bccfc952202ed9db5bdc5f68bbbba57c61b37b13
ms.sourcegitcommit: b3a1c5b0b24f0e52cf318defe10f3d27a2770009
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/21/2019
ms.locfileid: "67316943"
---
# <a name="monitor-bitlocker-and-device-encryption"></a>Monitorar a criptografia BitLocker e do dispositivo  
O Intune oferece um local centralizado para identificar o status de criptografia dos seus dispositivos Windows 10 e ajuda você a acessar informações importantes para o BitLocker nos seus dispositivos, conforme encontrado no Azure AD (Azure Active Directory).  

- O [Relatório de criptografia](#encryption-report) fornece detalhes sobre a preparação e o status de criptografia de um dispositivo. Os detalhes do relatório podem ajudá-lo a identificar problemas que impedem a criptografia bem-sucedida de dispositivos que você deseja proteger.  
- [Exiba detalhes do BitLocker](#bitlocker-recovery-keys) como as chaves de recuperação e a ID da chave do seu dispositivo de dentro do portal do Intune.  

## <a name="encryption-report"></a>Relatório de criptografia
É possível usar o relatório de criptografia para exibir detalhes sobre o status da criptografia de seus dispositivos Windows 10.  

Para localizar o relatório, entre no [Intune](https://aka.ms/intuneportal) e acesse a **Configuração do Dispositivo** e, em *Monitorar*, selecione **Relatório de criptografia**.  

### <a name="prerequisites"></a>Pré-requisitos:
para aparecer no relatório de criptografia, um dispositivo deve executar o Windows versão 1607 ou posterior.  

### <a name="report-details"></a>Detalhes do relatório
O relatório exibe o **Nome do dispositivo** para seus dispositivos Windows 10 e os detalhes de alto nível sobre cada um, incluindo:  
- **Versão do sistema operacional** – A versão do Windows.  
- **Versão do TPM** – a versão do chip do TPM (Trusted Platform Module) no dispositivo.  
- **Preparação para a criptografia** – uma avaliação de preparação dos dispositivos para dar suporte à criptografia BitLocker. Os dispositivos podem ser identificados como:
  - **Pronto**: o dispositivo pode ser criptografado usando a política MDM, que exige que o dispositivo tenha um TPM e que atenda aos seguintes requisitos de SKU e de versão do Windows 10:
    - versão 1703 ou posterior, do Business, Enterprise e Educação
    - versão 1809 ou posterior, do Pro  
  
    Para saber mais, confira o [CSP (provedor de serviço de configuração) do BitLocker](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) na documentação do Windows.  

  - **Não está pronto**: o dispositivo não tem funcionalidades de criptografia completas, mas ainda dá suporte à criptografia. Por exemplo, o dispositivo pode ser criptografado manualmente por um usuário ou pela Política de Grupo que pode ser definida para permitir a criptografia sem um TMP.
  - **Não aplicável**: não há informações suficientes para classificar este dispositivo.  

- **Status da criptografia** – indica se a unidade do sistema operacional é criptografada. 


### <a name="device-encryption-status"></a>Status da criptografia do dispositivo
Quando você seleciona um dispositivo, o Intune exibe o painel **Status de criptografia do dispositivo**.

O painel fornece os seguintes detalhes:  
- **Nome do dispositivo** – o nome do dispositivo que você está exibindo.  
- **Preparação para a criptografia** – uma avaliação de preparação dos dispositivos para dar suporte à criptografia BitLocker. Um dispositivo pode ter um Status de criptografia de *Criptografado* mesmo que seja a preparação para a criptografia *Não esteja pronta*, porque ela não tem um TPM. (Confira a preparação da criptografia na seção anterior para obter mais detalhes.)
- **Status da criptografia** – Se a unidade do sistema operacional é criptografada. Pode levar até 24 horas para o Intune começar a relatar sobre um status de criptografia de dispositivos ou uma alteração nesse status.  
- **Perfis** – Uma lista dos perfis *Configuração do dispositivo* que se aplicam a este dispositivo e incluem o tipo e as configurações do perfil a seguir:  
  - Tipo de perfil = *Endpoint Protection*  
  - Configurações > Criptografia do Windows > Criptografar dispositivos = *Necessário*  

  Essa lista pode ser útil para localizar políticas individuais para revisão caso o resumo do estado do perfil indique problemas.  

- **Resumo do estado de perfil** – Um resumo dos perfis que se aplicam a esse dispositivo. O resumo representa a condição menos favorável em todos os perfis aplicáveis. Por exemplo, se um perfil resultar em um erro, o resumo do estado do perfil exibirá *Erro*.  
- **Detalhes de status** – Detalhes avançados sobre o estado de criptografia do dispositivo. 
  > [!NOTE]  
  > O Intune só mostra os *Detalhes de status* para dispositivos que executam a *Atualização de 10 de abril de 2019 do Windows* ou posterior.
  
  Esse campo exibe informações para cada erro aplicável que possa ser detectado. É possível usar essas informações para entender por que um dispositivo talvez não esteja pronto para a criptografia.  

  Veja a seguir exemplos dos detalhes do status que o Intune pode relatar:  

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
   - Não há um TPM disponível para o BitLocker, porque ele não está presente, ficou indisponível no Registro ou o sistema operacional está em uma unidade removível.  
   - O TPM não está pronto para o BitLocker.  
   - A rede não estiver disponível, o que é necessário para o backup da chave de recuperação.  

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
Criar uma política de [conformidade do dispositivo](compliance-policy-create-windows.md) para dispositivos Windows 10 para configurar o BitLocker e a criptografia.
