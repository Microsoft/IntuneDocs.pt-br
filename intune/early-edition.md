---
title: Edição antecipada
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d6a06326fbb60d910aef0411fc666b82a5f22078
ms.sourcegitcommit: 401cedcd7acc6cb3a6f18d4679bdadb0e0cdf443
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2018
---
# <a name="the-early-edition-for-microsoft-intune---april-2018"></a>A Edição Antecipada do Microsoft Intune – abril de 2018

A **edição antecipada** fornece uma lista de recursos que estarão disponíveis em versões futuras do Microsoft Intune. Essas informações são fornecidas de forma limitada e estão sujeitas a alterações. Não compartilhe essas informações fora da empresa. Alguns recursos listados aqui correm o risco de não estarem prontos na data de fechamento e serem atrasados até uma versão futura. Outros recursos estão sendo testados em um piloto (liberação de versões de pré-lançamento) para garantir que fiquem prontos para o cliente. Fale com seu contato do grupo de produtos da Microsoft em caso de perguntas ou dúvidas.

Esta página é atualizada periodicamente. Volte a ela para verificar se há atualizações adicionais.

> [!Note]
>As seguintes alterações estão em desenvolvimento para o Intune. Para obter mais informações sobre os novos recursos híbridos, confira a [página Novidades sobre híbridos](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune no portal do Azure

<!-- 1804 start -->




### <a name="additions-to-local-device-security-options-settings----1403702---"></a>Adições às configurações das opções de segurança do dispositivo local <!-- 1403702 -->
Você poderá definir as configurações adicionais de Opções de Segurança de Dispositivo Local para dispositivos Windows 10. Configurações adicionais estarão disponíveis nas áreas de Cliente de Rede da Microsoft, Servidor de Rede Microsoft, Acesso e segurança de rede e Logon interativo. Encontre essas configurações na categoria Endpoint Protection quando você cria uma política de configuração de dispositivo com Windows 10.

### <a name="require-installation-of-policies-apps-certificate-and-network-profiles----1553555---"></a>Requer a instalação de perfis de políticas, aplicativos, certificado e rede <!-- 1553555 -->
Os administradores poderão impedir que usuários finais acessem a área de trabalho do Windows 10 RS4 até que o Intune instale políticas, aplicativos e perfis de certificado e de rede durante o provisionamento de dispositivos AutoPilot.

### <a name="rules-for-removing-devices----1609459---"></a>Regras para remover dispositivos <!-- 1609459 -->
Estarão disponíveis novas regras que permitem remover automaticamente dispositivos que não fizeram check-in por um número de dias que você definir. Para ver a nova regra, vá para o painel **Intune**, selecione **Dispositivos** e selecione **Regras de remoção de dispositivo**.

### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>Impedir aplicativos e experiências de consumidor em dispositivos Windows 10 Enterprise RS4 AutoPilot<!-- 1621980 -->
Você poderá impedir a instalação de aplicativos e experiências de consumidor nos seus dispositivos Windows 10 Enterprise RS4 AutoPilot. Para ver esse recurso, vá para **Intune** > **Registro de dispositivo** > **Registro do Windows** > **Perfis do Windows AutoPilot** > **Criar Novo** > **Configurações de registro**. 


<!-- 1803 start -->

#### <a name="multiple-exchange-connector-support----2070451---"></a>Suporte ao Multiple Exchange Connector <!-- 2070451 -->

Você não fica mais limitado a um Microsoft Intune Exchange Connector por locatário. O Intune dá suporte a vários Exchange Connectors para que você possa configurar o acesso condicional do Intune com diversas organizações do Exchange local.

Com um conector do Exchange local do Intune, você pode gerenciar o acesso ao dispositivo para suas caixas de entrada do Exchange local com base em se um dispositivo é registrado no Intune e está em conformidade com as políticas de conformidade de dispositivo do Intune. Para configurar um conector, baixe o conector do Exchange local do Portal do Azure no Intune e instale-o em um servidor na sua organização do Exchange. No painel do Microsoft Intune, escolha **Acesso local** e, em **Configuração**, selecione **Conector do Exchange ActiveSync**. Baixe o conector local do Exchange local e instale-o em um servidor na sua organização do Exchange. Agora que não há mais o limite de um conector do Exchange por locatário, se você tiver organizações do Exchange adicionais, siga este mesmo processo para baixar e instalar um conector para cada organização do Exchange adicional.

### <a name="support-coming-for-new-cisco-anyconnect-client-for-ios----1333708---"></a>Suporte futuro para novo cliente Cisco AnyConnect para iOS <!-- 1333708 -->

Os novos perfis de VPN criados para Cisco AnyConnect para iOS funcionam com o Cisco AnyConnect 4.0.7x e superior. Perfis existentes de VPN do Cisco AnyConnect do iOS serão rotulado como **Cisco Legacy AnyConnect** e continuarão a funcionar com o Cisco AnyConnect 4.0.5x como fazem atualmente.

> [!NOTE]
> Essa mudança afeta apenas o iOS. Continuará existindo apenas uma opção de Cisco AnyConnect para Android, Android for Work e macOS.

#### <a name="more-information"></a>Mais informações

Você precisa criar um novo perfil de VPN do Cisco AnyConnect do iOS para dar suporte ao novo aplicativo, pois o novo aplicativo Cisco AnyConnect e o aplicativo Cisco Legacy AnyConnect são aplicativos separados. Se você estiver gerenciando o cliente AnyConnect em seu ambiente, também será necessário implantar o aplicativo Cisco AnyConnect. Para concluir uma atualização, você também precisa excluir o perfil de VPN do Cisco Legacy AnyConnect e remover o aplicativo Cisco Legacy AnyConnect.

Integração de NAC (Controle de Acesso à Rede) não funcionará para o novo cliente AnyConnect na versão inicial. Estamos trabalhando com a Cisco para fornecer integração a NAC em uma futura versão do Intune.

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Capacidade de implantar aplicativos LOB (aplicativo de linha de negócios) necessários para Todos os usuários em dispositivos do Windows 10 Desktop <!-- 1627835 RS4 -->
Os clientes poderão implantar os aplicativos de linha de negócios do Windows 10 necessários que deverão ser instalados em contextos de dispositivo. Isso permitirá que esses aplicativos estejam disponíveis para todos os usuários no dispositivo. Isso se aplica somente a dispositivos Windows 10 Desktop.

### <a name="company-portal-enrollment-improved----1874230--"></a>Registro do Portal da Empresa melhorado <!-- 1874230-->
Os usuários que registrarem um dispositivo usando o Portal da Empresa no Windows 10 build 1703 e superior poderão concluir a primeira etapa de registro sem sair do aplicativo.

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>Atualizando a experiência de Ajuda e Comentários no aplicativo Portal da Empresa para Android <!--1631531 -->

Atualizaremos a experiência de Ajuda e de Comentários no aplicativo Portal da Empresa para Android a fim de alinhá-lo com as práticas recomendadas para aplicativos Android. Estaremos atualizando o aplicativo Portal da Empresa para Android nos próximos meses para dividir o item de menu **Ajuda e Comentários** nos itens **Ajuda** e **Enviar comentários** separados. A página **Ajuda** conterá com uma seção de **Perguntas Frequentes** e um botão **Suporte por Email** para instruir os usuários finais a carregar logs para a Microsoft e enviar email para o suporte da empresa descrevendo o problema. **Enviar Comentários** guiará o usuário por um envio de comentários padrão da Microsoft, que solicitará ao usuário escolher entre “Gosto de algo”, “ Não gosto de algo” ou “Tenho uma ideia”.


<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Políticas de Proteção de Aplicativo <!-- 679615 -->
As Políticas de Proteção de Aplicativo do Intune oferecem a capacidade de criar políticas globais e padrão para habilitar rapidamente a proteção em todos os usuários no locatário inteiro.

<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Os sites da Web do Azure Active Directory podem exibir o Aplicativo Intune Managed Browser e oferecer suporte ao Logon Único para o Managed Browser (Visualização Pública) <!-- 710595 -->   
Usando o Azure Active Directory (Azure AD), você poderá restringir o acesso a sites da Web em dispositivos móveis para o aplicativo Intune Managed Browser. No Managed Browser, os dados do site da Web permanecerão seguros e separados dos dados pessoais do usuário final. Além disso, o Managed Browser oferecerá suporte a recursos de Logon Único para sites protegidos pelo Azure AD. Entrar no Managed Browser ou usar o Managed Browser em um dispositivo com outro aplicativo gerenciado pelo Intune, permite que o Managed Browser acesse sites corporativos protegidos pelo Azure AD sem que o usuário precise inserir suas credenciais. Essa funcionalidade se aplica a sites como o Outlook Web Access (OWA) e o SharePoint Online, bem como a outros sites corporativos, como os recursos da intranet acessados por meio do Proxy do Aplicativo Azure.




## <a name="notices"></a>Avisos

Não há nenhum avisos ativo no momento.


### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new.md) para saber detalhes sobre os desenvolvimentos mais recentes.


