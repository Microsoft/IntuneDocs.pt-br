---
title: Arquivo de novidades | Microsoft Intune
description: 
keywords: 
author: Lindavr
manager: jeffgilb
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ed2db991-4729-49a7-a1e6-be2ffa0d03d1
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 805dfa1eeb81f4407066e27f203f315451937f8b
ms.openlocfilehash: acf502bdf73176450157535577047c9428aabfd1


---
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



## Setembro de 2015
### Atualizações de gerenciamento de aplicativo e dispositivo móvel
**Todos os recursos de gerenciamento de iOS do Intune agora dão suporte ao iOS 9** Para obter detalhes sobre os recursos de gerenciamento do iOS 9, consulte [esta postagem de blog](http://blogs.technet.com/b/microsoftintune/archive/2015/09/09/day-zero-support-for-ios-9-with-intune.aspx).

**Nova política de configuração de aplicativo móvel para iOS** Use a nova política de configuração de aplicativo móvel para fornecer automaticamente configurações de que um aplicativo iOS pode precisar quando é executado. Por exemplo, você poderia fornecer uma porta de rede ou um nome de usuário. Para detalhes, consulte [Configurar aplicativos com as políticas de configuração de aplicativo móvel no Microsoft Intune](https://technet.microsoft.com/library/mt481447.aspx).

**Gerenciamento de aplicativos mais fácil para usuários do iOS 9**
 Nesta versão, você pode colocar aplicativos já implantados sob gerenciamento do Intune para usuários do iOS 9. Para versões anteriores do iOS, quando você implantar um aplicativo e uma versão não gerenciada dele já estiver instalada em um dispositivo, você ainda precisará pedir ao usuário para desinstalar o aplicativo manualmente antes que o Intune possa instalar o aplicativo gerenciado.

 Mas, ao começar com esta versão do Intune, você agora pode solicitar que os usuários de dispositivos iOS 9 permitam que o Intune assuma o gerenciamento do aplicativo e aplique as políticas de gerenciamento de aplicativo móvel relevantes.

 **Gerenciamento do Windows 10** Use a nova [Política de configuração geral do Windows 10](https://technet.microsoft.com/library/mt404697.aspx) para configurar a senha, o dispositivo, o navegador e outras configurações para dispositivos que executam o Windows 10 e Windows 10 Mobile.

 **Criar e implantar aplicativos em dispositivos Windows 10 registrados** Um novo tipo de instalador de software, o Windows Installer, por meio do MDM (&#42;.msi) permite criar e implantar aplicativos do Windows Installer em dispositivos registrados que executam o Windows 10. Para detalhes, consulte [Introdução à implantação de aplicativo no Microsoft Intune](https://technet.microsoft.com/library/dn646955.aspx).

### Alterações e atualizações nos aplicativos do portal Microsoft Company
As seguintes alterações foram feitas nos aplicativos de portal da empresa nesta versão:

**iOS**
* A Microsoft coleta automaticamente dados anônimos sobre o desempenho e o uso do portal da empresa para aprimorar os produtos e serviços Microsoft. Os usuários finais podem desativar a coleta de dados usando a configuração de Dados de Uso em seu dispositivo, mas os administradores não têm controle sobre a coleta de dados e não podem alterar a seleção do usuário final para essa configuração.
* Suporte de resolução de tela completo no iPhone 6 e iPhone 6 Plus
* Correções de bugs para aumentar a segurança

### Novidades na documentação do Intune – setembro de 2015
**Novos tópicos**

|Nome|Detalhes|
|----|--------|
|[Definições de política de configuração do Windows 10 no Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx)|Esta é uma nova política de configuração que permite que você gerencie as configurações e recursos em dispositivos que executam o Windows 10 e Windows 10 Mobile.
| [Configurar aplicativos com as políticas de configuração de aplicativo móvel no Microsoft Intune](https://technet.microsoft.com/library/mt481447.aspx)|Este é um novo tipo de política que permite que você forneça automaticamente as configurações que podem ser necessárias quando o usuário executa um aplicativo iOS. |

**Tópicos atualizados**

|Nome|Detalhes|
|----|-------|
|[Usar políticas para gerenciar computadores e dispositivos móveis com o Microsoft Intune](https://technet.microsoft.com/library/dn743712.aspx)|Atualizado para incluir as informações mais recentes para ajudá-lo a entender e criar políticas.|

## Agosto de 2015
### Atualizações de gerenciamento de aplicativo e dispositivo móvel
* Os**Termos e condições** para registro no Intune e acesso da empresa agora [são gerenciados usando políticas](https://technet.microsoft.com/library/mt405893.aspx). Você pode direcionar conjuntos diferentes de termos e condições para atender a requisitos específicos de grupo de usuários. Por exemplo, você pode implantar termos e condições em idiomas diferentes para grupos de usuários definidos geograficamente. Você também pode [editar seus termos e condições](https://technet.microsoft.com/library/mt405893.aspx#BKMK_TCVers) e especificar se deseja incrementar números de versão, exigindo que os usuários concordem com os novos termos e condições para poderem usar o portal da empresa.
* **Diversas políticas do Intune foram renomeadas** para torná-los mais consistente em todo o produto e para facilitar a localização. Consulte [Usar políticas para gerenciar computadores e dispositivos móveis com o Microsoft Intune](https://technet.microsoft.com/library/dn743712.aspx) para obter uma lista de todas as políticas disponíveis do Intune.
* **Perfis de Certificado PKCS #12 (.PFX)** estão disponíveis para Android 4.0 ou posterior e Windows 10 (Desktop e Mobile) e posterior. Usar o .PFX não requer um servidor NDES. Saiba como usar os perfis de certificado .PFX em [Habilitar o acesso aos recursos da empresa usando perfis de certificado com o Microsoft Intune](http://technet.microsoft.com/library/dn818904.aspx)
* **As configurações de limites corporativos para Windows 10 Desktop e Mobile** habilitam configurações de VPN granulares, conforme descrito em [Ajudar os usuários a se conectarem ao seu trabalho usando perfis de VPN com o Microsoft Intune](https://technet.microsoft.com/library/dn818905.aspx)
* **O aplicativo OneDrive para Android agora dá suporte a várias identidades**. Esta e outras atualizações às políticas de gerenciamento de aplicativos móveis são descritas na lista de [aplicativos da Microsoft que você pode gerenciar](https://technet.microsoft.com/library/dn708489.aspx).
* **Ignorar Bloqueio de Ativação do iOS**. Se dispositivos iOS da empresa estiverem protegidos pelo Bloqueio de Ativação, você deverá inserir a ID Apple e a senha do usuário antes de apagar ou reativar o dispositivo. Isso pode representar um desafio quando os usuários deixam a empresa e retornam um dispositivo da empresa sem desativar o Bloqueio de Ativação. Para ajudar a resolver esse problema, você pode usar o [Bypass de Bloqueio de Ativação do Intune](https://technet.microsoft.com/library/mt414176.aspx)

### Acesso condicional para PCs
Agora você pode configurar políticas de acesso condicional para PCs. Isto permite que aplicativos da área de trabalho do Office acessem os serviços do Exchange Online e do SharePoint Online.
Para habilitar a política de acesso condicional para PCs, o PC deve ser ingressado no domínio ou ser compatível.
* A seção **Introdução** em [Gerenciar acesso ao email e SharePoint com o Microsoft Intune](http://technet.microsoft.com/library/dn818907) (.aspx) lista o conjunto completo de requisitos para habilitar o acesso condicional para PCs.
* Consulte [Gerenciar acesso ao email com o Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx) para obter as opções que você pode definir para habilitar o acesso condicional para acesso de email.
* Consulte [Gerenciar acesso ao SharePoint Online com o Microsoft Intune](https://technet.microsoft.com/library/dn705844.aspx) para obter as opções que você pode definir para habilitar o acesso condicional para acesso ao SharePoint Online.

### Alterações e atualizações nos aplicativos do portal Microsoft Company
As seguintes alterações foram feitas nos aplicativos de portal da empresa nesta versão:

**Android**

Os usuários agora encontrarão instruções de registro de dispositivo depois de entrar se não tiverem registrado seus dispositivos para gerenciamento.

### Novidades na documentação do Intune – Agosto de 2015
**Novos tópicos**

|Título|Detalhes|
|-----|-------|
|[Ajude a proteger dispositivos iOS com bypass de Bloqueio de Ativação para o Microsoft Intune](https://technet.microsoft.com/library/mt414176.aspx)|Saiba mais sobre como você pode usar o Intune para ignorar o bloqueio de Ativação do iOS quando um usuário sair da empresa e devolver um dispositivo bloqueado.|

**Tópicos atualizados**

|Título|Detalhes|
|-----|-------|
|[Aplicativos da Microsoft podem ser usados com políticas de gerenciamento de aplicativos móveis Microsoft Intune](https://technet.microsoft.com/library/dn708489.aspx)|Atualizado com as informações mais recentes sobre aplicativos que você pode gerenciar com políticas de gerenciamento de aplicativos móveis.
|[Usar políticas para gerenciar computadores e dispositivos móveis com o Microsoft Intune](http://technet.microsoft.com/library/dn743712.aspx)|Atualizado com as políticas mais recentes adicionadas ao Intune.|
<!---
## July 2015
July updates for Intune are limited to behind-the-scenes enhancements that allow us to continue providing you with a high-quality service experience. New features are not included in this service update.

### Intune Onboarding benefit
Microsoft offers the Intune Onboarding benefit for eligible plans. The Onboarding benefit lets you work remotely with Microsoft specialists to get your Intune environment ready for use. For more information, see [Microsoft Intune Onboarding benefit description](https://technet.microsoft.com/library/mt228266.aspx)
### Changes and updates to Microsoft Company Portal apps
The following changes have been made to the company portal apps in this release.

**Android**

Microsoft automatically collects anonymous data about the performance and use of the company portal to improve Microsoft products and services. End users can turn off data collection by using the Usage Data setting on their device, but administrators have no control over the data collection and cannot change the end user’s selection for this setting.--->



<!--HONumber=Jul16_HO3-->


