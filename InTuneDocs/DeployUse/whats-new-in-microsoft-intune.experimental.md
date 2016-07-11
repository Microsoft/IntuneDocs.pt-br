---
experiment_id: lindavr-abtest-20160527
title: Novidades | Microsoft Intune
description: "Descubra as novidades deste mês e os lançamentos anteriores do Microsoft Intune"
keywords: 
author: Lindavr
manager: jeffgilb
ms.date: 06/16/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
ms.sourcegitcommit: d1fb04dbb8746637bf72c1e227f36fe589594ca0
ms.openlocfilehash: ae524a989e236e84a6ce9d8266fc648dd683a825


---

# Novidades do Microsoft Intune
Conheça as novidades nesta versão do Microsoft Intune. Você também pode descobrir sobre alterações futuras que você deve estar planejando, bem como informações sobre versões anteriores.

Veja a seguir as novidades nesta versão. Exceto para a atualização de configuração de política do Windows Defender, todos esses recursos também têm suporte para implantações híbridas de clientes (Configuration Manager com o Intune). Para obter mais informações sobre os novos recursos híbridos, confira a [página Hybrid What’s New](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx) (Novidades do Híbrido).

## Junho de 2016
### Integridade do serviço do Intune
As informações de integridade do serviço do Intune foram movidas para uma localização central com outros serviços da Microsoft. Agora, você encontrará essas informações no Portal de gerenciamento do Office 365 em Integridade do Serviço. Para obter mais informações, consulte [esta postagem do blog](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

## Gerenciamento de aplicativos
- **Experiência aprimorada configuração de política de dados empresariais do Windows 10.** Fizemos aprimoramentos para a configuração de política de proteção de dados empresariais do Windows 10 em torno da criação de regras de aplicativo, especificando a definição de limites de rede e outras configurações de proteção de dados empresariais. Para saber mais, veja [Create an enterprise data protection (EDP) policy using Microsoft Intune](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) (Criar uma política de EDP (proteção de dados empresariais) usando o Microsoft Intune).


## Gerenciamento de dispositivos
- **A configuração de política do Windows Defender para proteger contra aplicativos potencialmente indesejados.** Uma nova configuração do Windows Defender chamada **Detecção de Aplicativos Potencialmente Indesejados** foi adicionada à política de configuração geral para Windows 10 Desktop e Mobile. Você pode usar essa configuração para proteger os computadores Windows Desktop registrados contra a execução de software classificado pelo Windows Defender como potencialmente indesejado. Você pode se proteger esses aplicativos executando ou usando o modo de auditoria para relatar quando um aplicativo potencialmente indesejado é instalado. Veja [Windows 10 policy settings in Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune) (Configurações de política do Windows 10 no Microsoft Intune) para saber mais.
<!---TFS 1244478--->

## Acesso condicional
- **Política de controle de acesso de rede do Cisco ISE para o Intune.**  Os clientes que usam o Cisco ISE (Identity Service Engine) 2.1 e também usam o Microsoft Intune podem definir uma política de controle de acesso de rede no ISE.

    Usando essa política, os dispositivos que precisam se conectar à rede usando Wi-Fi ou VPN devem atender às seguintes condições antes de terem permissão de acesso:

    * Deve ser gerenciado pelo Intune
    * Deve ser compatível com qualquer política de conformidade do Intune implantada

 Os usuários finais de dispositivos não compatíveis serão solicitados a registrar e corrigir quaisquer problemas de conformidade para obter acesso.
- **Acesso condicional para navegador.** Você pode definir uma política de acesso condicional para o [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md) e o [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md) para que eles somente possam ser acessados por navegadores da Web com suporte em dispositivos Android e iOS gerenciados e compatíveis. Os usuários finais que tentarem entrar nos sites OWA (Outlook Web Access) e SharePoint com dispositivos iOS e Android deverão registrar o dispositivo no Intune e corrigir quaisquer problemas de não conformidade para que possam entrar.
<!---TFS 1175844--->

- **O Dynamics CRM Online dá suporte ao acesso condicional.** Você pode definir uma política de acesso condicional para o [Dynamics CRM Online](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md) para que ele somente possa ser acessado por dispositivos iOS e Android gerenciados e compatíveis. Os usuários finais que tentarem entrar no aplicativo móvel Dynamics CRM no iOS e no Android deverão se registrar no Intune e corrigir quaisquer problemas de não conformidade para poder entrar.
<!---TFS1295358--->


## Atualizações do Portal da Empresa

### Aplicativo Android do Portal da Empresa

- Quando os administradores aplicarem a nova política "Exigir que dispositivos não permitam a instalação de aplicativos de fontes desconhecidas (Android 4.0 +)”, os usuários finais com dispositivos Android 4.0 ou posteriores verão a mensagem "A instalação de fontes desconhecidas deve ser desabilitada." Os usuários precisam ir para **Configurações** > **Segurança** e desativar **Fontes desconhecidas**. Um link na mensagem de conformidade permite aos usuários obter mais [informações](/Intune/EndUser/you-are-asked-to-turn-off-unknown-sources-android) sobre a mensagem e porque eles estão sendo solicitados a desativar a configuração.

- Quando os administradores de TI aplicarem a nova política "Exigir que dispositivos tenham habilitado a verificação de aplicativos contra ameaças à segurança (Android 4.0 +)", os usuários finais com dispositivos Android 4.0 ou posteriores verão a mensagem "Verificar dispositivo contra ameaças à segurança". Os usuários precisam ir para **Configurações** > **Google** > **Segurança** e ativar **Verificar dispositivo contra ameaças à segurança**. Um link na mensagem de conformidade permite aos usuários obter mais [informações](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) sobre a mensagem e porque eles estão sendo solicitados a ativar a configuração.

- Quando os administradores aplicarem a nova política "Exigir que a depuração de USB esteja desabilitada (Android 4.2 +)", os usuários finais com dispositivos Android 4.2 ou posteriores verão a mensagem "A depuração de USB deve ser desabilitada". Os usuários precisam ir para **Configurações** > **Opções do desenvolvedor** e desativar **Depuração de USB**." Um link na mensagem de conformidade permite aos usuários obter mais [informações](/Intune/EndUser/you-are-asked-to-turn-off-usb-debugging-android) sobre a mensagem e porque eles estão sendo solicitados a desativar a configuração.

- Quando os administradores aplicarem a nova política "Nível mínimo de patch de segurança Android (Android 6.0 +)", os usuários finais com dispositivos Android 6.0 ou posteriores verão a mensagem "Este dispositivo não atende ao nível mínimo de patch de segurança Android". Os usuários precisarão instalar o patch de segurança necessário. Um link na mensagem de conformidade permite aos usuários obter [informações](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) sobre como instalar o patch de segurança necessário e ver qual patch de segurança eles já têm instalado atualmente.

### Aplicativo Portal da Empresa para iOS

- Agora, quando os usuários finais instalarem aplicativos de linha de negócios, eles terão uma experiência de instalação de aplicativo melhor. Se a instalação do aplicativo estiver demorando muito, os usuários poderão sincronizar o dispositivo manualmente para forçar o processo de sincronização a continuar. Para examinar as instruções do usuário final, consulte [Sync your iOS device manually](/Intune/EndUser/sync-your-device-manually-ios.md) (Sincronizar o dispositivo iOS manualmente).

- O aplicativo de Portal da Empresa do Microsoft Intune para iOS foi atualizado para oferecer suporte à versão 8.0 e posteriores do iOS. Essa atualização significa que os usuários finais podem instalar o aplicativo do Portal da Empresa e registrar novos dispositivos no Intune somente se o dispositivo estiver executando o iOS versão 8.0 ou posterior. Usuários que já registraram dispositivos que estão executando uma versão sem suporte do iOS podem continuar usando o aplicativo de Portal da Empresa que está no dispositivo.


## O que está por vir

### Roteiro de nuvem
Mantenha-se informado sobre futuros desenvolvimentos do Intune com a [Estratégia de plataforma em nuvem](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).

### Serviço preterido
- **Aplicativos do visualizador do Intune.** Com o lançamento do novo aplicativo RMS sharing, estamos removendo os seguintes aplicativos do visualizador do Intune a partir de agosto de 2016:
    - Visualizador de AV do Intune
    - Visualizador de PDF do Intune
    - Visualizador de imagem do Intune para Android no Google Play

  Em vez de usar os aplicativos do visualizador do Intune, é recomendável usar o novo aplicativo do Rights Management (RMS sharing) para o Android, que permite implantar um aplicativo em vez de três aplicativos separados para exibir com segurança arquivos corporativos em dispositivos Android. Saiba mais sobre o aplicativo RMS sharing (com links para documentação).

- **Remoção de aplicação de regras de notificação em grupo personalizado.**
Regras de notificação do Intune definem para quem um alerta de email será enviado do Intune. No momento, você pode configurar as regras de notificação para enviarem emails para todos os usuários de dispositivos em um grupo de dispositivos do Intune que você criou. A partir de 1º de junho de 2016, direcionar grupos criados pelo usuário não terá mais suporte.

    Hoje, para direcionar uma regra de notificação a um grupo criado no console de administração do Microsoft Intune, você realizaria as seguintes etapas:

    No espaço de trabalho **Administrador**, clique em **Regras de Notificação** > **Criar Nova Regra**

    Na etapa dois do assistente Criar Regra de Notificação, selecione os grupos de dispositivos nos quais a regra será aplicada. Nesta etapa, “selecionar grupos de dispositivos”, está sendo removido do Console do Intune.

    A linha do tempo preliminar para essa alteração é a seguinte:
    - Em agosto de 2016, novos locatários não verão a etapa dois do Assistente para Criar Regra de Notificação. Os locatários existentes não são afetados.
    - Em torno de setembro de 2016, alguns locatários existentes não verão "selecione grupos de dispositivos" no assistente.
    - Em torno de novembro de 2016, esperamos que todos os locatários não vejam "selecione grupos de dispositivos" no assistente.


- **Alterações no suporte para o aplicativo do Portal da Empresa do iOS**. Em julho, todos os usuários do aplicativo do Portal da Empresa Microsoft Intune para iOS deverão usar a versão mais recente. Novos usuários só poderão baixar a versão mais recente e os usuários atuais precisarão atualizar para ela. A versão mais recente requer iOS 8.0 ou posterior, por isso dispositivos que executam versões anteriores do iOS não conseguirão usar o Portal da Empresa ou registrar-se até atualizar seu dispositivo para o iOS 8.0 ou posterior, para então atualizar o aplicativo de Portal da Empresa para a versão mais recente. Os dispositivos que executam versões abaixo do iOS 8.0 continuarão a ser gerenciados e listados no Console de Administração do Intune.





## Versões anteriores do Intune
Se você quiser ver o que foi lançado no Intune durante os últimos seis meses, consulte a lista no artigo [Previous Intune releases](previous-intune-releases.md) (Versões anteriores do Intune).
> [!div class="op_single_selector"]
- [Abril de 2016](previous-intune-releases.md)
- [Março de 2016](previous-intune-releases.md)
- [Fevereiro de 2016](previous-intune-releases.md)
- [Janeiro de 2016](previous-intune-releases.md)
- [Dezembro de 2015](previous-intune-releases.md)
- [Novembro de 2015](previous-intune-releases.md)




### Consulte também
* [Blog do Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Roteiro da Plataforma de Nuvem](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)



<!--HONumber=Jun16_HO4-->


