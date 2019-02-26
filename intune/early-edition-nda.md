---
title: Edição antecipada - Microsoft Intune
titlesuffix: ''
description: Edição antecipada do Microsoft Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/04/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: b1ff65e1b48815cd5964aa7498fa6ba54df50e09
ms.sourcegitcommit: e5f501b396cb8743a8a9dea33381a16caadc51a9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/23/2019
ms.locfileid: "56742288"
---
# <a name="the-early-edition-for-microsoft-intune---february-2019"></a>A edição antecipada do Microsoft Intune – fevereiro de 2019

> [!Note]
> Notificação de NDA: As seguintes alterações estão em desenvolvimento para o Intune. Essas informações são compartilhadas nos termos do NDA de forma muito limitada. Não poste nenhuma dessas informações em mídia social nem em sites públicos, como Twitter, UserVoice, Reddit e assim por diante. 

A **edição antecipada** fornece uma lista de recursos, compartilhados nos termos do NDA, que estarão disponíveis em versões futuras do Microsoft Intune. Essas informações são fornecidas de forma limitada e estão sujeitas a alterações. Não tweet, poste no UserVoice nem compartilhe de nenhuma outra forma essas informações fora de sua empresa. Alguns recursos listados aqui correm o risco de não estarem prontos na data de fechamento e serem atrasados até uma versão futura. Outros recursos estão sendo testados em um piloto (liberação de versões de pré-lançamento) para garantir que fiquem prontos para o cliente. Fale com seu contato do grupo de produtos da Microsoft em caso de perguntas ou dúvidas.

Esta página é atualizada periodicamente. Volte a ela para verificar se há atualizações adicionais.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune no portal do Azure
<!-- 1902 start-->


<!-- 1901 start -->

### <a name="deployment-of-online-licensed-microsoft-store-for-business-apps----1672660----"></a>Implantação de aplicativos online licenciados da Microsoft Store para Empresas <!-- 1672660  -->
Você poderá atribuir aplicativos online licenciados obrigatórios da Microsoft Store para Empresas no contexto de dispositivo. A implantação de um aplicativo da Microsoft Store para Empresas dessa maneira permitirá que o aplicativo seja instalado para todos os usuários no dispositivo. Isso é aplicável somente a dispositivos Windows 10 RS4+ desktop. A opção de instalação no contexto de dispositivo está disponível na página Atribuição de aplicativo do Cliente para aplicativos Online Licenciados da MSFB.

<!-- 1812 start -->

### <a name="android-enterprise-app-we-app-deployment----1171203---"></a>Implantação do aplicativo APP-WE do Android Enterprise <!-- 1171203 -->
Para dispositivos Android em um cenário de implantação APP-WE (Política de proteção de aplicativo sem registro), é possível usar o Google Play gerenciado para implantar aplicativos da loja e aplicativos de LOB para os usuários. Especificamente, o departamento de TI pode fornecer uma experiência de catálogo e instalação de aplicativos que não exige mais dos usuários finais a negligência com relação à postura de segurança de seus dispositivos ao permitir instalações de fontes desconhecidas. Além disso, esse cenário de implantação fornece uma experiência aprimorada ao usuário final.

### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation-----1927359---"></a>Método de autenticação de atualização das políticas do Intune e instalação do aplicativo Portal da Empresa <!-- 1927359 -->
Em dispositivos já registrados por meio do Assistente de Instalação com um dos métodos de registro de dispositivo corporativo da Apple, o Intune não oferecerá mais o suporte do Portal da Empresa quando for instalado manualmente pelos usuários finais da loja de aplicativos. Essa alteração só é relevante quando você autentica com o Assistente de Configuração da Apple durante o registro. Além disso, essa alteração afeta apenas dispositivos iOS registrados via:  
* Apple Configurator
* Apple Business Manager
* Apple School Manager
* Programa de registro de dispositivos (DEP) da Apple

Se os usuários instalarem o aplicativo Portal da Empresa pela loja de aplicativos e tentarem registrar esses dispositivos por meio do aplicativo, receberão um erro. Esses dispositivos só devem usar o Portal da Empresa quando ele for enviado por push, automaticamente, pelo Intune durante o registro. Os perfis de registro no Intune, no portal do Azure, serão atualizados para que você possa especificar como os dispositivos são autenticados, e se o usuário recebe o aplicativo Portal da Empresa. Se você quiser que os usuários de dispositivos DEP tenham o Portal da Empresa, especifique suas preferências em um perfil de registro. Além disso, a tela **Identifique o dispositivo** no aplicativo Portal da Empresa logo se tornará obsoleta.  
Para instalar o Portal da Empresa em dispositivos DEP já registrados, acesse Intune > Aplicativos cliente, e envie-o como um aplicativo gerenciado com políticas de configuração de aplicativo. Os detalhes sobre como executar essas etapas serão descritos em documentos futuros.

### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Os modelos administrativos estão em versão prévia pública e mudaram para o perfil de configuração próprio <!-- 3322847 -->
Os modelos administrativos no Intune (**Configuração do dispositivo** > **Modelos administrativos**) estão em versão prévia privada. Com esta atualização: Modelos administrativos incluem aproximadamente 300 configurações que podem ser gerenciadas no Intune. Anteriormente, essas configurações só existiam no editor de política de grupo.
Os modelos administrativos estão disponíveis na versão prévia pública. Os modelos administrativos estão mudando de **Configuração do dispositivo** > **Modelos administrativos** para **Configuração do dispositivo** > **Perfis** >**Criar perfil** > em **Plataforma**, escolha **Windows 10 e posterior**, em **Tipo de perfil**, escolha **Modelos administrativos**.
A criação de relatórios está habilitada. Aplica-se a: Windows 10 e posterior

### <a name="intune-macos-company-portal-dark-mode----3300524---"></a>Modo Escuro do Portal da Empresa do Intune no macOS <!-- 3300524 -->
O Portal da Empresa do Intune no macOS agora dá suporte ao Modo Escuro para macOS. Quando você habilitar o Modo Escuro em um dispositivo macOS 10.14 ou superior, o Portal da Empresa ajustará sua aparência de acordo com as cores para refletir o modo.

<!-- 1809 start -->  

### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>Configurações de APP (Política de Proteção de Aplicativo) do aplicativo para dados Web <!-- 2662995 -->
Configurações de política de aplicativo para conteúdo Web em dispositivos Android e iOS serão atualizadas para lidar melhor com links Web http e https, bem como transferência de dados por meio de Links Universais do iOS e Links de Aplicativo do Android.  

<!-- 1808 start -->

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Token de VPP da Apple usado por outro MDM <!-- 1488946 -->
O Intune detectará e mostrará detalhes se um token do VPP (Apple Volume Purchase Program) estiver sendo usado tanto pelo Intune quanto por outro MDM.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Dispositivos desativados no painel de conformidade de dispositivos <!-- 1981119 -->
Em uma atualização futura, os dispositivos desativados serão removidos do painel de conformidade de dispositivos. Com isso, seus números de conformidade serão alterados.

## <a name="notices"></a>Avisos

Não há nenhum avisos ativo no momento.

### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new.md) para saber detalhes sobre os desenvolvimentos mais recentes.
