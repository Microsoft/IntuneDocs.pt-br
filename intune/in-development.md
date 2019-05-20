---
title: Em desenvolvimento – Microsoft Intune
titleSuffix: ''
description: Recursos do Microsoft Intune em desenvolvimento
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/29/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7bba992c79f69a126f0199d9cdac52779910ff38
ms.sourcegitcommit: 068c4e4bc6e6d778ece4a83d000128c4d2b732db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2019
ms.locfileid: "64910320"
---
# <a name="in-development-for-microsoft-intune---may-2019"></a>Em desenvolvimento para o Microsoft Intune – maio de 2019

Para ajudá-lo em sua preparação e planejamento, esta página listas atualizações e recursos da interface do usuário do Intune que estão em desenvolvimento, mas ainda não foram liberados. Além disso:

- Se prevermos que você precisará agir antes de uma alteração, publicaremos uma postagem complementar do Centro de Mensagens do Office.
- Quando um recurso é lançado em produção, seja como versão prévia ou em disponibilidade geral, a descrição do recurso sairá dessa página, indo para a [página Novidades](whats-new.md).
- Esta página e a [página Novidades](whats-new.md) são atualizadas periodicamente. Volte a ela para verificar se há atualizações adicionais.
- Consulte o [Roteiro M365](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) para entregas estratégicas e linhas do tempo.

> [!Note]
> Esses itens refletem a expectativas atuais da Microsoft sobre as funcionalidades do Intune que estarão presentes em uma versão futura. As datas e os recursos individuais podem mudar. Nem todos os itens em desenvolvimento têm uma descrição de recurso nesta página.

**RSS feed**: receba uma notificação quando esta página for atualizada copiando e colando a seguinte URL em seu leitor de feed: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune no portal do Azure


<!-- 1905 start-->


### <a name="deleting-a-device-in-the-apple-portal-will-be-reflected-in-the-intune-portal---2489996---"></a>Excluir um dispositivo no portal da Apple será refletido no portal do Intune <!--2489996 -->
Se um dispositivo for excluído do Programa de registro de dispositivos da Apple ou dos portais do Apple Business Manager, o dispositivo será excluído automaticamente do Intune durante a próxima sincronização.

### <a name="baseline-support-for-keyword-search-----3082036-----------"></a>Suporte de linha de base para pesquisa de palavra-chave  <!-- 3082036         -->
Em breve, ao criar ou editar um perfil de linha de base de segurança, você poderá usar a *pesquisa* para filtrar as configurações exibidas no console.   

### <a name="reset-and-wipe-devices-in-bulk-by-using-the-graph-api----3295288---"></a>Redefinir e apagar dispositivos em massa usando a API do Graph <!-- 3295288 -->
Você poderá redefinir e apagar até 100 dispositivos em massa, usando a API do Graph.

### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---"></a>Verificar se há um chipset TPM em uma política de conformidade do dispositivo Windows 10 <!-- 3617671 -->
Muitos dispositivos Windows 10 e posteriores têm chipsets TPM (Trusted Platform Module). Esta atualização inclui uma nova configuração de conformidade que verifica a versão do chip TPM no dispositivo. 

O artigo [Configurações de política de conformidade do Windows 10 e posteriores](compliance-policy-create-windows.md#device-security) descreve esta configuração.

Aplica-se ao Windows 10 e posteriores

### <a name="intune-management-extension-powershell-scripts-----3734186------"></a>Scripts do PowerShell da extensão de gerenciamento do Intune  <!-- 3734186    -->
Você poderá configurar scripts do PowerShell para execução com privilégios de administrador do usuário no dispositivo. Confira mais informações em [Usar scripts do PowerShell em dispositivos Windows 10 no Intune](intune-management-extension.md).

### <a name="prevent-end-users-from-modifying-their-personal-hotspot-and-disable-siri-server-logging-on-ios-supervised-devices----4097904----"></a>Impedir que usuários finais modifiquem o ponto de acesso pessoal e desabilitar o registro em log do servidor Siri em dispositivos iOS supervisionados <!-- 4097904  --> 
Crie um perfil de restrições de dispositivo no dispositivo iOS (**Configuração do Dispositivo** > **Perfis** > **Criar perfil** > **iOS** para a plataforma > **Restrições de dispositivo** para o tipo de perfil). Esta atualização inclui novas configurações que você poderá configurar:

- Ponto de acesso pessoal
- Registro em log do servidor Siri

Para ver as configurações atuais, vá para [Configurações do dispositivo iOS para permitir ou restringir recursos](device-restrictions-ios.md). 

Aplica-se a: iOS 12.2 e posteriores

### <a name="new-classroom-app-device-restriction-settings-for-dep-enrolled-macos-devices----4097905----"></a>Novas configurações de restrição de dispositivo do aplicativo Classroom para dispositivos macOS registrados pelo DEP <!-- 4097905  --> 
Crie perfis de configuração de dispositivo para dispositivos macOS (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **macOS** para a plataforma > **Restrições de dispositivo** para o tipo de perfil). Esta atualização inclui novas configurações do aplicativo Sala de Aula para dispositivos registrados pelo DEP e a opção de desabilitar a Biblioteca de Fotos do iCloud.

Para ver as configurações atuais, vá para [Configurações do dispositivo macOS para permitir ou restringir recursos usando o Intune](device-restrictions-macos.md).

Aplica-se a: macOS 10.14.4 e posteriores

### <a name="android-enterprise-app-management----4459905-idready---"></a>Gerenciamento de aplicativos do Android Enterprise <!-- 4459905 idready -->
Para facilitar a configuração e o uso do gerenciamento de Android Enterprise pelos administradores de TI, o Intune adicionará automaticamente quatro aplicativos comuns relacionados ao Android Enterprise ao console do administrador do Intune. Os quatro aplicativos do Android Enterprise são os seguintes:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)**  – usado para cenários totalmente gerenciados pelo Android Enterprise.
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)** – ajuda a entrar em suas contas se usar a verificação de dois fatores.
- **[Portal da Empresa do Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)** – usado para cenários de perfil de trabalho das Políticas de Proteção do Aplicativo (APP) e do Android Enterprise.
- [Tela inicial gerenciada](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise) – usado para cenários dedicados/quiosques do Android Enterprise.

Antes, os administradores de TI precisavam encontrar e aprovar manualmente esses aplicativos na [Google Play Store gerenciada](https://play.google.com/store/apps) como parte da configuração. Essa alteração remove essas etapas que eram manuais para tornar mais fácil e rápido para os clientes usarem o gerenciamento do Android Enterprise.

Os administradores verão esses quatro aplicativos adicionados automaticamente à lista de aplicativos do Intune no momento em que conectarem pela primeira vez o locatário do Intune ao Google Play gerenciado. Confira mais informações em [Conectar sua conta do Intune à sua conta gerenciada do Google Play](connect-intune-android-enterprise.md). Para locatários que já conectaram o próprio locatário ou que já usam o Android Enterprise, não há nada que os administradores precisem fazer. Esses quatro aplicativos aparecerão automaticamente dentro de sete dias após a conclusão da implantação do serviço em maio de 2019.

<!-- 1904 start-->

### <a name="advanced-settings-for-windows-defender-firewall----1311949---"></a>Configurações avançadas para o Windows Defender Firewall <!-- 1311949 -->
Em breve, você poderá usar o Intune para gerenciar as regras de firewall personalizadas em clientes do Windows Defender. As regras poderão especificar o comportamento de entrada e saída para aplicativos, endereços de rede e portas. 


### <a name="device-users-can-view-all-managed-apps-theyve-installed-or-tried-to-install----2352913---"></a>Os usuários de dispositivos podem exibir todos os aplicativos gerenciados que você instalou ou tentou instalar <!-- 2352913 -->
O Portal da Empresa para Windows listará todos os aplicativos gerenciados&ndash; necessários e disponíveis&ndash; instalados em um dispositivo do usuário. Os usuários poderão exibir tentativas e instalações de aplicativos pendentes e o status atual. Se a sua organização não torna aplicativos obrigatórios ou disponíveis, os usuários veem uma mensagem explicando que nenhum aplicativo da empresa foi instalado. Os usuários também poderão classificar ou filtrar seus aplicativos por status de instalação.

### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>Usar "regras de aplicabilidade" ao criar perfis de configuração de dispositivo do Windows 10 <!-- 2549910 -->
Você cria perfis de configuração de dispositivo do Windows 10 (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10** para plataforma). Você poderá criar uma **regra de aplicabilidade** para que o perfil apenas se aplique a uma edição ou versão específica. Por exemplo, você pode criar um perfil que permita algumas configurações do BitLocker. Depois de adicionar o perfil, use uma regra de aplicabilidade para que o perfil só se aplique a dispositivos que executem o Windows 10 Enterprise.

Aplica-se a: 
- Windows 10 e posterior

###  <a name="intune-security-tasks-for-defender-atp-in-public-preview----3208597---"></a>Tarefas de segurança do Intune para Defender ATP (em versão prévia pública) <!-- 3208597 -->
Disponível como versão prévia pública, o Intune logo adicionará tarefas de segurança para o recém-anunciado Gerenciamento de Vulnerabilidade e Ameaças do Microsoft Defender.  Com essa integração, os administradores de operações de segurança no WDATP (Windows Defender ATP) poderão comunicar com mais eficiência aos administradores do Intune as correções recomendadas para ameaças emergentes. A adição de tarefas de segurança adiciona uma abordagem baseada em riscos para descobrir, priorizar e corrigir vulnerabilidades de ponto de extremidade e configurações incorretas.

Para saber mais sobre tarefas de segurança no Intune, veja a postagem no blog sobre [como usar tarefas de segurança do Intune para estender o Gerenciamento de Vulnerabilidade e Ameaças do Microsoft Defender ATP](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/Microsoft-Intune-security-tasks-extend-Microsoft-Defender-ATP-s/ba-p/369857). 

### <a name="windows-defender-advanced-threat-protection-baseline----3754134---"></a>Linha de base da Proteção Avançada contra Ameaças do Windows Defender <!-- 3754134 -->
Vamos adicionar a nova linha de base para ajudá-lo a definir as configurações de Proteção Avançada contra Ameaças do Windows Defender.



## <a name="notices"></a>Avisos

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new.md) para saber detalhes sobre os desenvolvimentos mais recentes.


