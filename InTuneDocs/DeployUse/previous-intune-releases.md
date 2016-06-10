---
# required metadata

title: Versões anteriores | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Versões anteriores do Intune

## Abril de 2016
Todos esses recursos também têm suporte para clientes híbridos (Configuration Manager integrado ao Intune).
### Gerenciamento de aplicativos
- **Conformidade de usuário do MAM.**
Agora você pode exibir o [status](monitor-mobile-app-management-policies-with-Microsoft-Intune.md) de suas políticas de gerenciamento de aplicativo para os usuários em seu locatário do AAD (Azure Active Directory). Isso inclui:
   - Dispositivos
   - Aplicativos no dispositivo

   Valores de status:

   **Check in feito**: indica que a política foi implantada para o usuário, e o aplicativo foi usado no contexto de trabalho e recebeu a política com êxito.

    **Check in não feito**: indica que a política foi implantada para o usuário, mas o aplicativo ainda não foi usado no contexto de trabalho.


- **Controles de MAM para impedir a sincronização de contatos do Outlook (Android).**
Uma nova configuração está disponível para o [gerenciamento de aplicativo móvel](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) sem registro de dispositivo. Essa configuração permite impedir que um aplicativo sincronize contatos para o catálogo de endereços nativo em dispositivos Android. Quando essa configuração for habilitada, os aplicativos selecionados não poderão mais salvar contatos no catálogo de endereços nativo. Quando essa configuração for desabilitada, os aplicativos selecionados poderão salvar contatos no catálogo de endereços nativo. Quando você [apagar um dispositivo ou aplicativo remotamente](wipe-managed-company-app-data-with-Microsoft-Intune.md), os contatos que já tiverem sido salvos no catálogo de endereços nativo serão removidos. Essa nova configuração tem suporte desde o início usando o aplicativo Outlook em dispositivos Android.

### Gerenciamento de dispositivos
- **Identificação de número de telefone para dispositivos de propriedade da empresa.** Os telefones categorizadas como "Empresariais" agora são identificados com o número de telefone completo quando, por exemplo, você executa um relatório de inventário de dispositivo móvel. Os números de telefone BYOD (Traga seu próprio dispositivo) continuam a ser mascarados com ****, somente com os quatro últimos dígitos exibidos.


### Atualizações do portal da empresa
**Aplicativo do portal da Empresa do Android** Os usuários que não tiverem registrado seus dispositivos no Intune e que não tenham o certificado correto instalado não conseguirão entrar no aplicativo Portal da Empresa do Android e verão a mensagem, "Você não pode entrar porque o dispositivo não tem um certificado necessário". A mensagem inclui um link de "Como resolver o problema" que os usuários podem tocar para ver instruções de como instalar o certificado. Para ver as etapas que os usuários finais devem seguir para resolver o problema, consulte [Your device is missing a required certificate](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing) (O dispositivo não tem um certificado necessário).

**Aplicativo do portal da Empresa do iOS** Foi adicionado suporte para a ação “puxe para atualizar” para atualizar o conteúdo na tela inicial, que inclui os aplicativos listados, dispositivos listados e informações de contato de TI. A ação “puxe para atualizar” não verifica as informações de conformidade ou política. Para fazer isso, selecione o bloco do dispositivo atual e toque no botão **Sincronizar**.

**Aplicativo do portal da Empresa do Windows 10 Mobile e Windows Phone 8.1** Agora, quando os usuários finais instalarem aplicativos de linha de negócios, eles terão uma experiência de instalação de aplicativo melhor. Se a instalação do aplicativo estiver demorando muito, os usuários poderão sincronizar o dispositivo manualmente para forçar o processo de sincronização a continuar. Para examinar as instruções do usuário final, consulte [Sync your device manually to speed up app installations](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually) (Sincronizar o dispositivo manualmente para acelerar as instalações de aplicativos).

**Site do Portal da Empresa** Quando os usuários do Windows 10 Mobile e do Windows Phone 8.1 estiverem instalando aplicativos de linha de negócios, eles verão os novos status a seguir, que fornecem mais detalhes sobre o status da instalação:

* **Aguardando o dispositivo sincronizar** – o usuário tocou em "Instalar" e agora o dispositivo tenta sincronizar com a infraestrutura do Intune. A sincronização é necessária para que a instalação possa ser concluída. A mensagem "Aguardando o dispositivo sincronizar" também é um link que os usuários podem tocar para ver [instruções](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually) de como sincronizar os dispositivos manualmente com o Intune, quando o processo de sincronização está demorando muito ou fica paralisado.
* **Baixando** – solicitação de download do usuário está sendo processada e o dispositivo está baixando e instalando o aplicativo.

Antes desses status serem adicionados, os usuários ficavam confusos quando a instalação de um aplicativo demorava muito, pois eles viam apenas o status "Instalando", que podia permanecer na tela por horas. A adição dos novos status significa que, em vez de ligar para o suporte, agora os usuários podem tocar no link "Esperando o dispositivo sincronizar" e seguir as instruções para forçar o processo de sincronização a continuar.


## Março de 2016
### O que há de novo a partir de 29 de março de 2016
Com exceção da atualização da política de configuração geral do Windows 10, todas as funcionalidades lançadas em 29 de março de 2016 também têm suporte para clientes híbridos (Configuration Manager integrado com o Intune). O suporte a configurações híbridas para a atualização de política de configuração geral do Windows 10 estará disponível em breve. Observe que alguns dessas funcionalidades podem exigir a versão mais recente do Configuration Manager.

### Gerenciamento de aplicativos
- **Controles de MAM para impedir a sincronização de contatos do Outlook (iOS).** Uma nova configuração está disponível para o gerenciamento de aplicativo móvel sem registro de dispositivo. Essa configuração permite impedir que um aplicativo sincronize contatos para o catálogo de endereços nativo em dispositivos iOS. Quando essa configuração for habilitada, o aplicativo não poderá mais salvar contatos no catálogo de endereços nativo. Quando essa configuração for desabilitada, o aplicativo poderá salvar contatos no catálogo de endereços nativo. Quando você apagar um dispositivo seletivamente, os contatos que já tiverem sido salvos no catálogo de endereços nativo serão removidos. Essa nova configuração tem suporte no aplicativo Outlook em dispositivos iOS. Para obter mais detalhes sobre essa e outras configurações, consulte [Create and deploy MAM policies](https://technet.microsoft.com/en-us/library/dn292747.aspx) (Criar e implantar políticas MAM).

### Controle de acesso
- **O Skype for Business Online dá suporte ao acesso condicional.** Você pode definir uma política de acesso condicional para o Skype for Business Online para que ele somente possa ser acessado por dispositivos iOS e Android gerenciados e compatíveis. Os usuários finais que tentarem entrar no aplicativo móvel Skype for Business no iOS e no Android deverão se registrar no Intune e corrigir quaisquer problemas de não conformidade para poder entrar. Para ver mais detalhes, consulte [Manage access to Skype for Business Online](https://technet.microsoft.com/en-us/library/mt695297.aspx) (Gerenciar o acesso ao Skype for Business Online).

### Gerenciamento de dispositivo
- **Suporte do Intune para iOS 9.3.** Em 21 de março, segunda-feira, a Apple anunciou a disponibilidade do iOS 9.3. Estávamos trabalhando duro para garantir que o Microsoft Intune seja compatível com a versão mais recente do sistema operacional de móvel da Apple e [temos prazer de anunciar que o Intune já dá suporte ao gerenciamento de dispositivos iOS 9.3](https://blogs.technet.microsoft.com/microsoftintune/2016/03/23/microsoft-intune-provides-support-for-ios-9-3/).

  Todas as funcionalidades do Intune existentes atualmente disponíveis para gerenciar dispositivos iOS continuarão a funcionar perfeitamente quando os usuários atualizarem seus dispositivos para o iOS 9.3. Além disso, o iOS 9.3 também têm suporte para clientes híbridos a partir de hoje (Configuration Manager integrado ao Intune).

- **A política de configuração geral do Windows 10 agora contém configurações para gerenciar o Windows Defender em computadores Windows 10 registrados.** Para ver mais detalhes, consulte [Windows 10 configuration policy settings in Microsoft Intune](https://technet.microsoft.com/en-us/library/mt404697.aspx) (Definições de política de configuração do Windows 10 no Microsoft Intune).


### Portal da empresa

- **Pacotes de aplicativos do Windows disponíveis diretamente do site de Portal da Empresa.** Usuários de computadores Windows 8, Windows 8.1 e Windows RT agora podem instalar pacotes de aplicativos do Windows (com a extensão .appx) diretamente do site Portal da Empresa. Anteriormente, você precisava implantar, ou os usuários tinham que instalar, o aplicativo Portal da Empresa em seus dispositivos para instalar aplicativos.

- **Os usuários podem bloquear remotamente seu dispositivo no site do Portal da Empresa.** Uma nova opção de Bloqueio Remoto foi adicionada no site Portal da Empresa para permitir que os usuários bloqueiem seus dispositivos remotamente usando o Portal, em caso de perda ou roubo do dispositivo. Consulte as [instruções do usuário final](https://technet.microsoft.com/library/mt590895.aspx/?wt.mc_id=ui#BKMK_iwp_remote_lock). A tabela a seguir lista o suporte às plataformas para bloqueio remoto do Intune Standalone e do Intune com o Configuration Manager.

|Plataforma | Detalhes do suporte|
|---------|----------------|
|Android |Com suporte|
|iOS |Com suporte|
|Windows 10 Mobile |Com suporte apenas se o telefone tiver uma senha definida|
|Windows 10 Desktop |Sem suporte|
|Windows Phone 8.1 |Com suporte apenas se o telefone tiver uma senha definida|
|Windows Phone 8.0 |Sem suporte|
|Computador (Windows 8.0 e anterior) |Sem suporte|
|Computador (Windows 8.1) |Sem suporte|

### O que há de novo a partir de 10 de março de 2016

### Gerenciamento de aplicativos

- **Tirar proveito do gerenciamento “aberto em” do iOS de dispositivos que são registrados em uma solução de MDM de terceiros** Você pode usar o seu fornecedor MDM (gerenciamento de dispositivo móvel) para tirar proveito do gerenciamento “aberto em” do iOS. Você pode definir as restrições nas definições de perfil da configuração e implantar o aplicativo usando [Manage data transfer between iOS apps](manage-data-transfer-between-ios-apps-with-microsoft-intune.md) (Gerenciar transferência de dados entre aplicativos iOS).

     Essa abordagem tem dois benefícios principais:

     1. Os usuários devem fazer logon com sua conta de trabalho antes de obter acesso a todos os dados corporativos de outros aplicativos ou Serviços de Nuvem. Isso garante que as políticas de MAM (gerenciamento de aplicativo móvel) estejam em vigor quando os dados são acessados.

     2. Perfis de email gerenciado e outros aplicativos gerenciados implantados por meio de uma solução MDM de terceiros podem compartilhar arquivos e dados com os aplicativos que têm políticas de MAM do Intune.

- **Gerencie o aplicativo Microsoft Outlook com políticas MAM para dispositivos não registrados no Intune** Agora você pode gerenciar o aplicativo Microsoft Outlook em dispositivos que não estão registrados no Intune com a política de gerenciamento de aplicativos móveis do Intune. O aplicativo Microsoft Outlook atualizado com as funcionalidades MAM está disponível para ambos os dispositivos [iOS](https://itunes.apple.com/us/app/microsoft-outlook-email-calendar/id951937596?mt=8) e [Android](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook). Use as instruções no tópico [criar e implantar políticas de gerenciamento de aplicativo móvel](https://technet.microsoft.com/library/mt627829.aspx) para criar uma política de MAM.  


- **Políticas de configuração de aplicativo móvel oferecem mais flexibilidade para especificar detalhes do usuário para aplicativos iOS** Você pode fornecer as configurações de usuário que um aplicativo iOS poderá precisar quando for aberto. Por exemplo, você poderia fornecer uma porta de rede ou um nome de usuário. Para ver mais detalhes, consulte [Configure iOS apps with mobile app configuration policies in Microsoft Intune](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md) (Configurar aplicativos iOS com as políticas de configuração de aplicativo móvel no Microsoft Intune).


- **Implantar o Adobe Reader para o Microsoft Intune para dispositivos iOS gerenciados pelo Intune em sua empresa** O aplicativo Adobe Reader para iOS agora pode ser gerenciado em dispositivos registrados com a política de gerenciamento de aplicativos móveis do Intune.

- **Garanta que os clipes da Web implantados sejam abertos em um navegador gerenciado** Você pode implantar clipes da Web direcionados que só podem ser abertos usando o navegador gerenciado em dispositivos iOS e Android. Por exemplo, você implanta links para recursos corporativos por meio do Portal da Empresa, e quando os usuários navegam para os links, eles abrem diretamente no navegador gerenciado em que eles são protegidos pela política de MAM. Para ver mais detalhes, consulte [Implantar aplicativos ](deploy-apps.md).


- **Localizar, gerenciar e distribuir aplicativos da Windows Store para Empresas para dispositivos Windows 10 do console do administrador do Intune** Suporte para a Windows Store para Empresas está disponível no Intune para ajudá-lo a encontrar, gerenciar e distribuir aplicativos para os dispositivos Windows 10 que você está gerenciando. A Windows Store para Empresas permite que você gerencie o processo de implantação e monitoramento desses aplicativos do console do administrador do Intune – o mesmo console que você usa para gerenciar seus outros aplicativos. Especificamente, a Windows Store para Empresas gerencia o conteúdo e licenciamento de "aplicativos licenciados online". Para obter detalhes, consulte [Manage apps you purchased from the Windows Store for Business](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md) (Gerenciar aplicativos adquiridos na Windows Store para Empresas).


### Gerenciamento de dispositivo
- **A distribuição de certificados PFX para dispositivos iOS** Os administradores do Intune podem criar e implantar os certificados PFX do iOS para Wi-Fi, email e autenticação de VPN em dispositivos iOS. Esse recurso já está disponível para dispositivos Android e Windows 10. Para detalhes, consulte [Enable access to company resources using certificate profiles](secure-resource-access-with-certificate-profiles.md) (Habilitar o acesso aos recursos da empresa usando perfis de certificado).


- **Aplicar aplicativos e políticas para grupos de dispositivos diferentes com base na seleção da categoria de usuário** Os administradores do Intune agora podem definir categorias de dispositivo personalizado para os usuários selecionem durante o registro. Por exemplo, os administradores talvez queiram que os usuários especifiquem se eles estão registrando um dispositivo usado para "Caixa Registradora" ou "Caminhão de Entrega" ou "Sala de Estoque". A categoria selecionada fará com que o dispositivo se torne um membro de um grupo de dispositivo do Intune, que pode ser usado para implantar políticas e aplicativos diferentes para o dispositivo registrado. Para detalhes, consulte [Categorize devices with device group mapping](categorize-devices-with-device-group-mapping-in-microsoft-intune.md) (Categorizar os dispositivos com o mapeamento do grupo de dispositivos).

### Alterações e atualizações no Portal da Empresa da Microsoft
As alterações a seguir foram feitas ao Portal da Empresa nesta versão.

**Aplicativo Android do Portal da Empresa**

* Quando os usuários iniciam um aplicativo gerenciado pelo MAM (gerenciamento de aplicativo móvel), eles verão uma mensagem notificando que o aplicativo é gerenciado pela empresa. Os usuários agora podem tocar no link "Saiba Mais" para obter [mais informações](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_use_mgd_apps) aqui sobre o que significa "aplicativos gerenciados". Eles também podem tocar em "Não Mostrar Novamente" para que a mensagem não apareçam quando iniciar o aplicativo.
* Foram adicionadas novas telas para orientar os usuários pelo processo de registro e fornecer mais informações sobre por que os usuários devem registrar e o que os administradores de TI podem e não podem ver em seus dispositivos registrados. Consulte as [instruções de registro](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc) para ver os detalhes.
* As mensagens de erro de registro agora são exibidas no aplicativo Portal da Empresa. Anteriormente, essas mensagens apareceram no site do Portal da Empresa. Fazer essa alteração significa que todas as mensagens de erro agora aparecem em um só lugar, em vez de dois locais diferentes.


**Aplicativo Portal da Empresa para iOS**
* Quando os usuários iniciam um aplicativo gerenciado pelo MAM (gerenciamento de aplicativo móvel), eles verão uma mensagem notificando que o aplicativo é gerenciado pela empresa. Os usuários agora podem tocar no link "Saiba Mais" para obter [mais informações](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_use_mgd_apps) aqui sobre o que significa "aplicativos gerenciados". Eles também podem tocar em "Não Mostrar Novamente" para que a mensagem não apareçam quando iniciar o aplicativo.
* Foram adicionadas novas telas para orientar os usuários pelo processo de registro e fornecer mais informações sobre por que os usuários devem registrar e o que os administradores de TI podem e não podem ver em seus dispositivos registrados. Consulte as [instruções de registro](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device) para ver os detalhes.
* As mensagens de erro de registro agora são exibidas no aplicativo Portal da Empresa. Anteriormente, essas mensagens apareceram no site do Portal da Empresa. Fazer essa alteração significa que todas as mensagens de erro agora aparecem em um só lugar, em vez de dois locais diferentes.




## Fevereiro de 2016
### Alterações e atualizações no Portal da Empresa da Microsoft

As alterações a seguir foram feitas ao Portal da Empresa nesta versão.

#### Aplicativo Android do Portal da Empresa
- Foram adicionadas novas telas para orientar os usuários pelo processo de registro e fornecer mais informações sobre por que os usuários devem registrar e o que os administradores de TI podem e não podem ver em seus dispositivos registrados. Consulte as [instruções de registro](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc) para ver os detalhes.
- As mensagens de erro de registro agora são exibidas no aplicativo Portal da Empresa. Anteriormente, essas mensagens apareceram no site do Portal da Empresa. Fazer essa alteração significa que todas as mensagens de erro agora aparecem em um só lugar, em vez de dois locais diferentes.

#### Aplicativo Portal da Empresa para iOS
 - Foram adicionadas novas telas para orientar os usuários pelo processo de registro e fornecer mais informações sobre por que os usuários devem registrar e o que os administradores de TI podem e não podem ver em seus dispositivos registrados. Consulte as [instruções de registro](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device) para ver os detalhes.

 - As mensagens de erro de registro agora são exibidas no aplicativo Portal da Empresa. Anteriormente, essas mensagens apareceram no site do Portal da Empresa. Fazer essa alteração significa que todas as mensagens de erro agora aparecem em um só lugar, em vez de dois locais diferentes.


## Janeiro de 2016

### Usufrua dos recursos do Windows 10
* **Acesso condicional com o Serviço de Atestado de Integridade** Os administradores podem exibir o status do Atestado de Integridade do Dispositivo Windows 10 no console de administração do Intune. O atestado de integridade do dispositivo permite que o administrador garanta que os computadores cliente têm configurações confiáveis de BIOS, TPM e software de inicialização. Para dar suporte ao atestado de integridade do dispositivo, os dispositivos do cliente devem estar executando o Windows 10 com o TPM 2 habilitado. O atestado de integridade do dispositivo exibe o número de dispositivos habilitados para cada um dos seguintes:
    * Antimalware de inicialização antecipada
    * BitLocker
    * Inicialização Segura
    * Integridade do código

    Leia [Introdução às políticas de conformidade do dispositivo do Microsoft Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md) para obter mais detalhes sobre a configuração de integridade do dispositivo, pontos de dados coletados e relatório de atestado de integridade. Os [detalhes do serviço HAS](https://msdn.microsoft.com/en-us/library/dn934876.aspx) explicam o serviço com mais detalhes.

* **Gerenciamento de certificado e Política do Windows 10 Passport for Work** Com o Intune, você pode [fazer a integração com o Microsoft Passport for Work](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md), que é um método de entrada alternativo para o Windows 10 que usa o Active Directory ou uma conta do Azure Active Directory para substituir uma senha, um cartão inteligente ou um cartão inteligente virtual. O Passport permite que você use um gesto de usuário para logon, em vez de uma senha. Um gesto do usuário pode ser um PIN simples, uma autenticação biométrica, como o Windows Hello, ou um dispositivo externo, como um leitor de impressão digital.

* **VPN para aplicativos específicos** Você pode selecionar os aplicativos que se conectam automaticamente à rede corporativa por VPN. Crie a lista de aplicativos ao configurar o perfil VPN, conforme descrito em Ajudar os usuários a se conectarem ao trabalho usando perfis VPN com o Microsoft Intune.

* **Suporte para Apagamento Completo do Windows 10** Agora você pode executar um apagamento remoto completo de dispositivos Windows 10 Desktop registrados no Intune através do console de administração do Intune. O apagamento completo do Windows 10 faz uma redefinição de fábrica do dispositivo.


### Atualização do VPP (Apple Volume Purchase Program)
O Intune agora pode ajudá-lo a [gerenciar aplicativos que você adquiriu pelo VPP (Apple Volume Purchase Program) para Empresas](manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune.md). Isso inclui a sincronização de informações de licença entre a Apple e o Intune e controle de quantas cópias de cada aplicativo você implantou.

### Use números IMEI para identificar dispositivos corporativos
Agora você pode [importar números IMEI (Identidade de Equipamentos Móveis Internacional)](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) em plataformas de dispositivos móveis para ajudar a identificar dispositivos móveis corporativos. Depois de registrados no Intune, os dispositivos com números IMEI importados são marcados como corporativos, que podem ser usados para a aplicação de políticas que são diferentes das que foram aplicadas a dispositivos de propriedade pessoal.

### Agora mais aplicativos são compatíveis com as políticas de MAM do Intune
Aplicativos adicionais de parceiros da Microsoft agora são compatíveis com políticas de MAM (gerenciamento de aplicativo móvel) do Intune (para dispositivos gerenciados pelo Intune):
* Box for EMM (da Box Inc) – somente iOS
* Adobe Reader (da Adobe) – somente Android
* Foxit PDF Reader (da Foxit Corporation) – iOS e Android


### O suporte do IE9 termina em janeiro
Iniciando em fevereiro de 2016, o Internet Explorer 9 não será mais suportado como um navegador oficial para acessar o site do portal da empresa do Microsoft Intune, o portal de contas do e o console de administração do Intune. Você precisará migrar para o Internet Explorer 10 ou posterior.

## Dezembro de 2015
### Alterações e atualizações no Portal da Empresa da Microsoft
As alterações a seguir foram feitas ao Portal da Empresa nesta versão.

**Aplicativo Android do Portal da Empresa**

As alterações a seguir foram feitas para atender aos novos requisitos do Google. Para dispositivos com Android 6.0 e superiores, duas novas mensagens são exibidas aos usuários:
* Permitir que o Portal da Empresa faça e gerencie chamadas telefônicas?
* Permitir que o Portal da empresa acesse fotos, mídia e arquivos em seu dispositivo?

Consulte as tabelas a seguir para obter detalhes sobre essas duas mensagens.



Texto da mensagem  |Permitir que o Portal da Empresa faça e gerencie chamadas telefônicas?  
---------|---------
Significado da mensagem     |  Permite que o IMEI e o número de telefone do dispositivo do usuário e sejam enviados ao serviço Intune e apareçam no console do Administrador, na página de Hardware.   </br></br>**Observação: o aplicativo Portal da Empresa nunca faz ou gerencia chamadas telefônicas!** O texto da mensagem é controlado pelo Google e não pode ser alterado. </br></br>Para ver a página **Hardware**, vá para **Grupos** > **Todos os dispositivos móveis** > **Dispositivos**. Selecione o dispositivo do usuário e vá para **Exibir Propriedades** > **Hardware**.    
Onde e quando a mensagem é exibida  | A mensagem é exibida quando os usuários entram no aplicativo de Portal da Empresa pela primeira vez para começar o registro de seu dispositivo.|         
O que acontece se os usuários permitirem o acesso  |  O IMEI e o número de telefone do dispositivo serão exibidos na página Hardware, no console do Administrador. |         
O que acontece se os usuários negarem o acesso     | Eles poderão continuar a usar o aplicativo de Portal da Empresa e registrar seus dispositivos, mas O IMEI e o número de telefone do dispositivo dos usuários ficará em branco na página Hardware no console do Administrador.       </br></br> Na segunda vez que os usuários entrarem no aplicativo Portal da Empresa após negarem acesso, a mensagem exibe uma caixa de seleção **Nunca Perguntar Novamente** que os usuários podem selecionar para que a mensagem nunca seja exibida novamente.</br></br>Se os usuários permitem mas posteriormente negam o acesso, a mensagem é exibida na próxima vez que os usuários entram no aplicativo de Portal da Empresa após o registro.</br></br>Se os usuários decidirem posteriormente permitir o acesso, eles poderão acessar **Configurações** > **Aplicativos** > **Portal da Empresa** > **Permissões** > **Telefone** e ativar a permissão.
Mais informações     |  Para seus usuários: [entrar no Portal da Empresa](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_signin_cp)  </br></br>Para profissionais de TI: as informações nesta tabela também estão em [Ajudando seus usuários a entender as mensagens do aplicativo Portal da Empresa](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs)   

Texto da mensagem  |Permitir que o Portal da empresa acesse fotos, mídia e arquivos em seu dispositivo?  
---------|---------
Significado da mensagem     |  Permite que o dispositivo grave logs de dados no cartão SD do dispositivo, o que permite que os logs sejam movidos usando um cabo USB.   </br></br>**OBSERVAÇÃO: o aplicativo Portal da Empresa nunca acessa fotos, mídia e arquivos dos usuários!** O texto da mensagem é controlado pelo Google e não pode ser alterado.     
Onde e quando a mensagem é exibida  | A mensagem é exibida quando os usuários tocam em **Enviar Dados** para enviar logs de dados ao seu administrador de TI.|         
O que acontece se os usuários permitirem o acesso  |  Os logs serão copiados para o cartão SD. |         
O que acontece se os usuários negarem o acesso     | Eles ainda podem enviar logs de dados, mas os logs não serão copiados para o cartão SD do dispositivo.       </br></br> Na segunda vez que os usuários entrarem no aplicativo Portal da Empresa após negarem acesso, a mensagem exibe uma caixa de seleção **Nunca Perguntar Novamente** que os usuários podem selecionar para que a mensagem nunca seja exibida novamente.</br></br>Se os usuários permitem mas posteriormente negam o acesso, a mensagem é exibida na próxima vez que os usuários tentam enviar logs.</br></br>Se os usuários decidirem posteriormente permitir o acesso, eles poderão acessar **Configurações** > **Aplicativos** > **Portal da Empresa** > **Permissões** > **Armazenamento** e ativar a permissão.
Mais informações     |  Para seus usuários: [enviar logs de dados de diagnóstico para seu administrador de TI usando o email](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_send_diag_logs)  </br></br>Para profissionais de TI: as informações nesta tabela também estão em [Ajudando seus usuários a entender as mensagens do aplicativo Portal da Empresa](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs)   


**Aplicativo Portal da Empresa para iOS**
* Os usuários agora podem usar o Microsoft Outlook ou outros aplicativos de email para enviar logs de diagnóstico para o administrador de TI. Anteriormente, apenas o aplicativo nativo podia ser usado.
* O suporte foi aprimorado para o DEP (programa de registro de dispositivo) e dispositivos registrados corporativamente da Apple. Para obter detalhes, consulte [Você será solicitado a identificar o dispositivo quando estiver tentando fazer o registro](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_id_your_device).
* Na lista de dispositivos registrados do usuário, uma marca de seleção verde agora aparece ao lado do dispositivo que o usuário está usando atualmente. Antes que a marca de seleção fosse adicionada, não era possível para os usuários indicar o dispositivo registrado que estavam utilizando.

**Aplicativo do Portal da Empresa para Windows**

A Microsoft coleta automaticamente dados anônimos sobre o desempenho e o uso do portal da empresa para aprimorar os produtos e serviços Microsoft. Os usuários finais podem desativar a coleta de dados usando a configuração de Dados de Uso em seu dispositivo, mas os administradores não têm controle sobre a coleta de dados e não podem alterar a seleção do usuário final para essa configuração.



## Novembro de 2015
### Gerenciamento de aplicativos
O Intune dá suporte a políticas MAM (gerenciamento de aplicativo móvel) que ajudam a evitar que dados corporativos vazem dos aplicativos ou serviços do consumidor. Historicamente, essas políticas somente deveriam ser impostas em aplicativos móveis executados em dispositivos que também foram registrados para MDM (gerenciamento de dispositivo móvel) no Intune.

Com a atualização deste mês, o Intune está expandindo suas funcionalidades de MAM para novas classes de dispositivos. Além dos dispositivos registrados no Intune, agora você pode impor políticas MAM em:
* dispositivos gerenciados por outras soluções MDM (gerenciamento de dispositivo móvel)
* dispositivos que não estão registrados em um sistema de gerenciamento de dispositivo, normalmente dispositivos BYO (traga seu próprio dispositivo)

Você encontrará mais informações sobre essas novas funcionalidades MAM nas postagens de blog a seguir:
* [Aumentando a produtividade móvel gerenciada](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)
* [Apresentação das novas funcionalidades do Microsoft Enterprise Mobility](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)

Além disso, estes são alguns destaques e informações adicionais sobre os recursos de MAM do Intune:
* Dados corporativos são isolados de dados do consumidor dentro dos aplicativos habilitados para o Intune, incluindo aplicativos Office Mobile, aplicativos de terceiros que adotaram o SDK do Intune ou aplicativos de linha de negócios encapsulados pelo Intune.
* Os dados da empresa podem ser compartilhados (**recortar/copiar/colar**) em aplicativos da empresa, evitando o compartilhamento de dados da empresa em aplicativos pessoais. Leia [Como as políticas de MAM protegem os dados do aplicativo](https://technet.microsoft.com/library/mt627825.aspx) para obter mais detalhes. Esse cenário de exemplo, [Usando o aplicativo Microsoft Word para tarefas de trabalho e pessoais](https://technet.microsoft.com/library/mt627827.aspx), mostra como o compartilhamento de dados da empresa em aplicativos pessoais é impedido.
* As políticas de prevenção de perda de dados importantes, como PIN por aplicativo, controles de salvar como e compartilhamento de dados gerenciados entre aplicativos. Leia [Criar e implantar políticas de gerenciamento de aplicativo móvel com o Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx) para ver uma lista com todas as políticas.
* Word, Excel, PowerPoint, Outlook, OneNote e OneDrive for Business: todos têm essas novas funcionalidades e podem ser gerenciados com e sem registro de dispositivo. Os recursos de proteção de perda de dados são nativamente criados nos aplicativos do Office padrão na Apple Store ou Google Play Store e não exigem o encapsulamento de aplicativo ou sideload.
* Para saber como começar, consulte [Introdução às políticas de gerenciamento de aplicativo móvel no Portal do Azure](https://technet.microsoft.com/library/mt627830.aspx). Para saber como configurar e implantar políticas de gerenciamento de aplicativo móvel, consulte [Criar e implantar políticas de gerenciamento de aplicativo móvel com o Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx).
* Quando os usuários finais se autenticam no aplicativo com suas credenciais corporativas, as funcionalidades de proteção de perda de dados serão configuradas automaticamente. O tópico [Experiência do usuário final para aplicativos associados a políticas de gerenciamento de aplicativo móvel do Microsoft Intune](https://technet.microsoft.com/library/mt627827.aspx) tem alguns cenários de exemplo para acessar o OneDrive em dispositivos iOS e Android.
* Funciona em dispositivos com Android e iOS.

A lista de [Aplicativos da Microsoft que você pode usar com políticas de gerenciamento de aplicativos móveis do Microsoft Intune](https://technet.microsoft.com/library/dn708489.aspx) foi atualizada para mostrar os aplicativos mais recentes.

### Gerenciamento de dispositivo
 **Gerenciamento de dispositivo Mac OS X** Com o Intune, agora você pode registrar e gerenciar dispositivos Mac OS X. Você pode fazer o seguinte com seus dispositivos Mac OS X:
* Registrar dispositivos a serem gerenciados pelo Intune. Consulte [Configurar gerenciamento de iOS e Mac com o Microsoft Intune](https://technet.microsoft.com/library/dn408185.aspx).
* Controlar as configurações de dispositivo com uma política de configuração geral. Consulte [Definições de política de configuração do Mac OS X no Microsoft Intune](https://technet.microsoft.com/library/mt627823.aspx).
* Implantar as configurações do Mac OS X criadas com o Apple Configurator. Consulte [Configurações de política personalizada do Mac OS X no Microsoft Intune](https://technet.microsoft.com/library/mt627820.aspx).
* Coletar o inventário de softwares e hardwares dos dispositivos Mac OS X. Consulte [Compreender seus dispositivos com um inventário no Microsoft Intune](https://technet.microsoft.com/library/jj733634.aspx).
* Execute novos relatórios que exibem detalhes sobre os dispositivos Mac OS X que você gerencia. Consulte [Entender as operações do Microsoft Intune usando relatórios](https://technet.microsoft.com/library/dn646977.aspx).

**Novas configurações do navegador Edge para dispositivos Windows 10** Foram adicionadas novas configurações para a política de configuração geral do Windows 10 que permitem que você gerencie as configurações e os recursos do navegador Microsoft Edge. Consulte [Definições de política de configuração do Windows 10 no Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx).

**Perfis de email** Uma nova política de perfis de email foi adicionada nos dispositivos Windows 10 Desktop e Windows 10 Mobile. Consulte [Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](https://technet.microsoft.com/library/dn646984.aspx).

**Novas configurações de política de conformidade** As seguintes configurações novas de política do sistema e segurança foram adicionadas à lista de políticas de conformidade:
* Para certificar-se de que os dispositivos Windows 8.1 ou posteriores que acessam os recursos da empresa têm as últimas atualizações instaladas, use a configuração **Requer atualizações automáticas**. Você também pode especificar o tipo de atualizações a serem instaladas automaticamente – todas as atualizações marcadas como instalação importante ou todas as atualizações marcadas como importantes ou recomendadas. Para obter uma lista completa das configurações de política, veja [Gerenciar políticas de conformidade de dispositivo para o Microsoft Intune](https://technet.microsoft.com/library/dn705843.aspx).
* A nova configuração **Exigir uma senha quando o dispositivo retorna do estado ocioso** combinada com a configuração existente **Minutos de inatividade antes da senha ser necessária** permite que você crie uma configuração de conformidade que requer que o usuário final insira uma senha para usar um dispositivo que está inativo por um certo tempo.

**Novas opções de política de acesso condicional** Você pode aplicar políticas de acesso condicional a **todos os usuários** em políticas de acesso condicional novas ou existentes. Todos os usuários licenciados para o Intune e Office 365 serão solicitados a registrar seus dispositivos, e se a plataforma do dispositivo não tiver suporte pelo Intune, o acesso será bloqueado para aplicativos cliente que usam [Autenticação do Active Directory com base em credenciais (autenticação moderna)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/).

Você também pode especificar que a política de acesso condicional se aplica a **todas as plataformas**.  Qualquer aplicativo cliente que usa a [autenticação com base em credenciais (autenticação moderna) do Active Directory](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/) está sujeito à política de acesso condicional e, se a plataforma não tiver suporte no Intune, o acesso ela será bloqueada.

### Alterações e atualizações no Portal da Empresa da Microsoft
As seguintes alterações foram feitas nos aplicativos de portal da empresa nesta versão:

* **Android**: uma tela de boas-vindas foi adicionada ao aplicativo Portal da Empresa para Android para ajudar os usuários a entender a finalidade do aplicativo Portal da Empresa. Esta tela tem como objetivo reduzir downloads do aplicativo pelos usuários cujas empresas não são assinantes do Intune.

* **iOS**: o Intune agora dá suporte ao registro de dispositivos Mac OS X usando o [site do Portal da Empresa](https://portal.manage.microsoft.com). Para obter instruções, consulte [Registrar seu dispositivo Mac OS X no Intune](https://technet.microsoft.com/library/mt598622.aspx).

* **Site do Portal da Empresa**: os usuários que registraram seus dispositivos no Intune agora podem redefinir sua senha usando a opção **Redefinir Senha** no site do Portal da Empresa. Anteriormente, somente os administradores de TI podiam redefinir senhas de usuários. Não há suporte para a opção Redefinir Senha em dispositivos Windows 8.1 e Windows RT, e a opção é exibida somente quando os dispositivos são registrados no MDM (gerenciamento de dispositivo móvel) ou MDM com o Exchange ActiveSync. Para obter instruções de usuário, consulte [Redefinir sua senha](https://technet.microsoft.com/library/mt590895.aspx).

### Alterações no licenciamento por administradores globais
Em outubro, compartilhamos que administradores globais (também conhecidos como administradores de locatários) podem continuar a executar tarefas de administração cotidianas sem uma licença separada do Intune ou EMS (Enterprise Mobility Suite). No entanto, se os administradores globais quiserem usar o serviço, como registrar seus próprios dispositivos, um dispositivo corporativo ou usar o Portal da Empresa do Intune, eles precisarão de uma licença do Intune ou EMS, assim como qualquer outro usuário. Abaixo estão alguns detalhes adicionais.
* O Portal da Empresa do Intune é onde os usuários finais podem:
    * registrar seus dispositivos
    * exibir o status de seus dispositivos
    * baixar o software que o administrador global implantou na organização
    * encontrar links publicados pelo administrador global para saber como entrar em contato com seu departamento de TI

    [Saiba mais sobre o Portal da Empresa](https://technet.microsoft.com/library/dn646966.aspx#BKMK_CompanyPortal) e sobre [maneiras de personalizar o Portal da Empresa](https://technet.microsoft.com/library/dn646983.aspx#BKMK_ConfigureCompanyPortal).
* A pessoa que se inscreve para comprar o Intune ou EMS em nome de uma organização automaticamente se torna o primeiro administrador global em seu locatário. Nesse outono, o Intune começou a atribuir automaticamente uma licença do Intune ou EMS para esse primeiro administrador global como parte da mudança para o [Portal do Office 365](http://portal.office.com/) e desativação do [Portal de Contas do Intune](http://account.manage.microsoft.com/). Os administradores globais adicionais inclusos podem continuar a fazer a administração cotidiana sem uma licença separada do Intune ou EMS. Atuar como um usuário final e registrar seu dispositivo (ou da empresa) ou baixar o software do portal da empresa dispararia uma necessidade de uma licença, assim como qualquer outro usuário.
* A alteração será introduzida gradualmente e será iniciada em janeiro de 2016.
* Para Microsoft Partners, essa alteração não deve afetar sua capacidade de administrar o serviço em nome dos clientes. Para tarefas do usuário final, um usuário precisará ter uma licença do Intune ou EMS para registrar um dispositivo e acessar ou baixar o software do Portal da Empresa.

Se você tiver dúvidas sobre essa alteração, fique à vontade para entrar em contato com a equipe de suporte do Intune:
* [Canais de suporte do Microsoft Intune](https://technet.microsoft.com/library/jj839713.aspx)
* [Suporte da comunidade](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)

Comentários gerais do Microsoft Intune, incluindo preenchimento de DCRs (Solicitações de Alteração de Design) ou bugs, acesse [Voz do usuário Intune](https://microsoftintune.uservoice.com/).


### Novidades na documentação do Intune – novembro de 2015
**Novo conteúdo**
* [Definições de política de configuração do Mac OS X no Microsoft Intune](https://technet.microsoft.com/library/mt627823.aspx): como controlar as configurações de dispositivo e os recursos para dispositivos Mac OS X.
* [Configurações de política personalizada do Mac OS X no Microsoft Intune](https://technet.microsoft.com/library/mt627820.aspx): como implantar configurações do dispositivo Mac OS X que você criou usando a ferramenta Apple Configurator.
* [Configurar políticas de aplicativo de prevenção de perda de dados com o Microsoft Intune](https://technet.microsoft.com/library/mt627825.aspx): contém informações sobre os cenários do suporte das políticas de gerenciamento de aplicativo móvel e como a política funciona na proteção de dados.
* [Introdução às políticas de gerenciamento de aplicativo móvel no portal do Azure](https://technet.microsoft.com/library/mt627830.aspx): o que você precisa para começar a usar a Versão Prévia do Portal do Azure para políticas de gerenciamento de aplicativo móvel.
* [Criar e implantar políticas de gerenciamento de aplicativo móvel com o Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx): contém uma explicação passo a passo de como criar políticas de gerenciamento de aplicativo móvel na Versão Prévia do Portal do Azure.
* [Monitorar políticas de gerenciamento de aplicativo móvel com o Microsoft Intune](https://technet.microsoft.com/library/mt627824.aspx): informações sobre como você pode monitorar suas políticas de gerenciamento de aplicativo móvel usando a Versão Prévia do Portal do Azure.
* [Políticas de gerenciamento de aplicativo móvel do Microsoft Intune e iOS Open In](https://technet.microsoft.com/library/mt627821.aspx): informações sobre como as políticas de gerenciamento de aplicativo móvel funcionam com o recurso Open In do iOS.
* [Experiência do usuário final para aplicativos associados a políticas de gerenciamento de aplicativo móvel do Microsoft Intune](https://technet.microsoft.com/library/mt627827.aspx): como é a experiência do usuário final ao usar aplicativos associados à política de gerenciamento de aplicativos móveis.
* [Apagar os dados de aplicativos da empresa gerenciados com o Microsoft Intune](https://technet.microsoft.com/library/mt627826.aspx): como você pode remover dados de aplicativos da empresa.

**Conteúdo atualizado**
* [Definições de política de configuração do Windows 10 no Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx): novas configurações do navegador Edge adicionadas.
* [Configurar o gerenciamento do Mac e iOS com o Microsoft Intune e iOS](http://technet.microsoft.com/library/dn408185.aspx): adicionadas informações sobre como registrar dispositivos Mac OS X.
* [Entender seus dispositivos com o inventário do Microsoft Intune](https://technet.microsoft.com/library/jj733634.aspx): adicionadas informações sobre o inventário coletado dos dispositivos Mac OS X. Além disso, o tópico com as informações mais recentes para todas as plataformas de dispositivo foi atualizado.
* [Entender as operações do Microsoft Intune usando relatórios](https://technet.microsoft.com/library/dn646977.aspx): adicionadas informações sobre os dois novos relatórios usados para exibir informações sobre os dispositivos gerenciados do Mac OS X.
* [Gerenciar políticas de conformidade do dispositivo do Microsoft Intune](https://technet.microsoft.com/library/dn705843.aspx): adicionadas informações sobre as novas políticas de conformidade para exigir atualizações automáticas e requisito de senha quando um dispositivo retorna do estado ocioso.
* [Gerenciar o acesso ao email com o Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx): adicionadas informações sobre a capacidade de aplicar a política de acesso condicional para todas as plataformas e todos os usuários.
* [Gerenciar o acesso ao SharePoint Online com o Microsoft Intune](https://technet.microsoft.com/library/dn705844.aspx): adicionadas informações sobre a capacidade de aplicar a política de acesso condicional para todas as plataformas e todos os usuários.

## Outubro de 2015

### Atualizações no acesso condicional para o Exchange local
**Agora você pode permitir acesso ao email do Exchange Active Sync para dispositivos compatíveis e registrados no Intune quando a regra global do Exchange estiver definida como bloqueada ou em quarentena** Até agora, para permitir o acesso ao email em dispositivos registrados e compatíveis, você precisava definir a regra padrão do Exchange global como **Permitir**.

Com a atualização de serviço, essa configuração não é mais um requisito para o acesso condicional. Se o seu ambiente do Exchange exigir que a regra global padrão seja definida como **Bloqueio/Quarentena**, basta marcar a caixa de seleção **Substituição de Regra Padrão** na página de política de acesso condicional do Exchange local. O tópico [Gerenciar o acesso de email com o Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx) tem mais detalhes sobre as regras e as notificações para o usuário final resultantes.

**Nova experiência de quarentena com um clique** Nós simplificamos a experiência de email de quarentena para permitir o registro com um clique. Com essa atualização de serviço, os usuários finais podem clicar em um único link no email de quarentena para concluir o processo de registro do aplicativo no portal da empresa.
### Atualizações de gerenciamento de aplicativo e dispositivo móvel
**Android** Todos os recursos de gerenciamento do Intune agora dão suporte ao Android 6.0 (Marshmallow) conforme descrito nesta postagem de blog: [Microsoft Intune dá suporte inicial para o Android Marshmallow](http://blogs.technet.com/b/microsoftintune/archive/2015/10/09/microsoft-intune-to-provide-day-0-support-for-android-marshmallow.aspx)

**iOS** Você não pode mais criar novas implantações de aplicativo para dispositivos iOS executando uma versão anterior ao iOS 7.1. As implantações de aplicativos existentes em dispositivos em execução em uma versão anterior ao iOS 7.1 continuarão funcionando e serão gerenciadas pelo Intune.

**Windows 10** O Intune agora dá suporte à implantação de aplicativos universais do Windows 10 usando o tipo de instalador de software do **pacote do aplicativo do Windows**. Para detalhes e requisitos, acesse [Get started with app deployment in Microsoft Intune](http://technet.microsoft.com/en-US/library/dn646955.aspx) (Introdução à implantação de aplicativo no Microsoft Intune).


### Alterações e atualizações nos aplicativos do portal Microsoft Company
As seguintes alterações foram feitas nos aplicativos do portal da empresa nesta versão: **iOS** Novos botões foram adicionados ao aplicativo do Portal da Empresa para tornar mais fácil para os usuários enviarem logs de diagnóstico para os administradores de TI:

|Nome do botão|Onde ele aparece|
|------------|---------------|
|Relatório|Mensagens de alerta de erro|
|Enviar relatório de diagnóstico|Tela de informações do aplicativo de Portal da Empresa|


>[!div class="step-by-step"]

>[&larr; **Novidades do Intune**](whats-new-in-microsoft-intune.md)    


<!--HONumber=May16_HO3-->


