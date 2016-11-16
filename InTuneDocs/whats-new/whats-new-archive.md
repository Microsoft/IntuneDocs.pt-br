---
title: Arquivo de novidades | Microsoft Intune
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ed2db991-4729-49a7-a1e6-be2ffa0d03d1
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 861b5ea3bb0772d2853942e2b3f11f607dad3774
ms.openlocfilehash: 25128cfe93280e38a03779a7e6f38ddeb3c15612


---
# <a name="whats-new-archive"></a>Arquivo de Novidades

Esta página é um arquivo de comunicados recentes feitos em [Novidades do Microsoft Intune](whats-new-in-microsoft-intune.md).

## <a name="september-2016"></a>Setembro de 2016
### <a name="new-features-announcements-and-information"></a>Novos recursos, avisos e informações
* [Acesso condicional do Windows](#windows-conditional-access)
* [Suporte para iOS 10](#ios-10-support)
* [A Ferramenta de Encapsulamento de Aplicativo dá suporte ao MAM sem registro de dispositivo para Android e iOS](#app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios)
* [Os grupos do Intune começam a transição para o Azure Active Directory em setembro](#intune-groups-begin-transitioning-to-azure-active-directory-in-september)
* [Integração do Lookout para proteger dispositivos Android](#lookout-integration-to-protect-android-devices)
* [Atualizações do Portal da Empresa para Android, iOS e Windows](#company-portal-updates)
* [Glossário do Intune](#intune-glossary)
* [O que está por vir](#whats-coming)

### <a name="windows-conditional-access"></a>Acesso condicional do Windows
Agora é possível criar políticas de acesso condicional através do console de administrador do Intune para impedir que PCs Windows acessem o Exchange Online e o SharePoint Online. Você também pode criar políticas de acesso condicional para bloquear o acesso aos aplicativos da área de trabalho e universais do Office.

### <a name="ios-10-support"></a>suporte para iOS 10
Os cenários existentes do Intune MDM e MAM são compatíveis com iOS 10. Para obter dicas, consulte o [Blob da Equipe de Suporte do Intune](https://blogs.technet.microsoft.com/intunesupport/2016/09/13/support-tip-intune-support-for-ios-10/).

### <a name="app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios"></a>A Ferramenta de Disposição do Aplicativo dá suporte ao MAM sem registro de dispositivo para Android e iOS
A Ferramenta de Disposição do Aplicativo do Intune é uma ferramenta de linha de comando usada para habilitar o Intune MAM em aplicativos de linha de negócios (LOB) para iOS e Android. Esta é a maneira mais simples de incorporar o SDK do MAM do Intune em seu aplicativo, para que seu aplicativo possa impor políticas MAM implantadas por meio do Intune. Ao usar políticas MAM, você pode:

1. Criptografar os dados do aplicativo.
2. Exigir que o trabalhador de informações insira um PIN ao iniciar o aplicativo.
3. Permitir que o aplicativo transfira dados apenas para outros aplicativos gerenciados.
4. Impedir que o aplicativo faça backup de dados para Android, iTunes e iCloud.
5. Permitir que somente Recortar, Copiar e Colar em e fora de outros aplicativos gerenciados.

A visualização pública da Ferramenta de Disposição do Aplicativo do Intune atualizada agora dá suporte ao MAM sem registro de dispositivo em aplicativos LOB internos no iOS e Android. Isso significa que os usuários finais não precisam registrar seus dispositivos com o Intune para usar aplicativos LOB habilitados para MAM.

Qualquer pessoa pode testar o software de visualização pública e ler a documentação útil, localizada no GitHub do msintuneappsdk:

<p style="margin-left: 40px">http://www.github.com/msintuneappsdk/intune-app-wrapper-ios-preview

<p style="margin-left: 40px">http://www.github.com/msintuneappsdk/intune-app-wrapper-android-preview

Antes de instalar e usar o Wrapper do Aplicativo do Microsoft Intune para pré-lançamento para Android e iOS, você deve:

* Examinar os Termos de Licença da Microsoft para a Ferramenta de Disposição do Aplicativo do Microsoft Intune para pré-lançamento para Android e iOS
* Imprimir e guardar uma cópia dos termos de licença para seus registros. Ao baixar e usar a Ferramenta de Disposição do Aplicativo do Microsoft Intune para Pré-lançamento para Android, você concorda com estes termos de licença. Se você não aceitá-los, não use o software.
<!---TFS 1235607--->

### <a name="intune-groups-begin-transitioning-to-azure-active-directory-in-september"></a>Os grupos do Intune começam a transição para o Azure Active Directory em setembro
Algumas novas contas do Intune usarão os grupos de segurança do Azure Active Directory em vez de grupos de usuários do Intune. Você saberá que você está trabalhando com grupos de segurança porque a página de grupos do portal do Intune terá um link que direciona para o portal de gerenciamento do Azure.

### <a name="lookout-integration-to-protect-android-devices"></a>Integração do Lookout para proteger os dispositivos Android
A Microsoft está se integrando com a solução de proteção de ameaças móveis do Lookout para proteger dispositivos móveis Android ao detectar malware, aplicativos arriscados e muito mais, em dispositivos. A solução do Lookout ajuda você a determinar o nível de ameaça, que é configurável. Você pode criar uma regra de política de conformidade do Intune para determinar a conformidade do dispositivo com base na avaliação de riscos pelo Lookout. Usando políticas de acesso condicional, você pode permitir ou bloquear o acesso aos recursos da empresa com base no status de conformidade do dispositivo.

Os usuários finais de dispositivos não compatíveis serão solicitados a se registrar e deverão instalar o aplicativo Lookout for Work em dispositivos Android, ativar o aplicativo e corrigir ameaças relatadas no aplicativo Lookout for Work para obter acesso. Para saber mais, consulte [Restringir o acesso com base no dispositivo, na rede e no risco do aplicativo](restrict-access-based-on-device-network-app-risk.md).


### <a name="company-portal-updates"></a>Atualizações do Portal da Empresa

__Android__

<p style="margin-left: 40px">**Acréscimo de “Notificações” ao Portal da Empresa para Android**<br/>
<p style="margin-left: 40px">Um novo ícone de Notificações foi acrescentado ao Portal da Empresa para Android na home page. Tocar nesse ícone acessará a página Notificações, que mostra a seus usuários finais todos os itens que exigem atenção no aplicativo Portal da Empresa, como a não conformidade de dispositivo, a atualização de registro e a ativação de registro. O aplicativo de Portal da Empresa para iOS já tem essa experiência de notificações. Ter a nova página de Notificações significa que o usuário não verá a página Configuração de Acesso da Empresa sempre que iniciar ou retomar o Portal da Empresa, contanto que o dispositivo já esteja registrado. Se você criar suas próprias diretrizes para o usuário final, convém atualizar a documentação para refletir essa alteração. Encontre capturas de tela atualizadas [aqui](https://aka.ms/androidcpupdate).  

__iOS__
<p style="margin-left: 40px">**Alterações no suporte para o aplicativo do Portal da Empresa do iOS**<br/>
<p style="margin-left: 40px">Todos os usuários do aplicativo do Portal da Empresa Microsoft Intune para iOS agora devem usar a versão mais recente. Novos usuários só poderão baixar a versão mais recente e os usuários atuais precisarão atualizar para ela. A versão mais recente requer iOS 8.0 ou posterior, por isso dispositivos que executam versões anteriores do iOS não conseguirão usar o Portal da Empresa ou registrar-se até atualizar seu dispositivo para o iOS 8.0 ou posterior, para então atualizar o aplicativo de Portal da Empresa para a versão mais recente. Os dispositivos que executam versões abaixo do iOS 8.0 continuarão a ser gerenciados e listados no Console de Administração do Intune.
<!---TFS 1283165--->

<p style="margin-left: 40px">**Melhorias na maneira como os usuários finais do iOS obtêm seus aplicativos**<br/>
<p style="margin-left: 40px">As alterações a seguir foram feitas nos blocos de aplicativos no aplicativo Portal da Empresa para iOS para encaminhar os usuários a diferentes modos de exibição em um único local, o site Portal da Empresa, para todos os seus aplicativos. As restrições da Apple proíbem que aplicativos gerenciados e de linha de negócios da loja de aplicativos sejam listados no aplicativo Portal da Empresa e exigem que os usuários acessem diferentes modos de exibição para localizar todos os seus aplicativos.

<p style="margin-left: 40px">Anteriormente, o bloco **Aplicativos da Empresa** apontavam para uma lista de todos os aplicativos na guia TODOS do site Portal da Empresa e continuará funcionando da mesma maneira. O nome do bloco foi alterado para **Todos os Aplicativos**.

<p style="margin-left: 40px">Anteriormente, o bloco **Outros Aplicativos** apontava para um modo de exibição no aplicativo Portal da Empresa que lista todos os aplicativos que Apple permite que o aplicativo Portal da Empresa mostre. O nome do bloco foi alterado para **Aplicativos em Destaque** e, ao tocar no bloco, os usuários são levados para a guia EM DESTAQUE do site Portal da Empresa.

<p style="margin-left: 40px">O bloco **Categorias** apontava para um modo de exibição no aplicativo Portal da Empresa que lista categorias de aplicativos. O nome do bloco não foi alterado, mas agora ele aponta para a guia CATEGORIAS do site Portal da Empresa. Você pode encontrar capturas de tela atualizadas [aqui](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).
  <!---TFS 1317133--->

<p style="margin-left: 40px">**Solicite a instalação do aplicativo de Navegador Gerenciado do iOS se o profissional de TI definir esse requisito para um aplicativo**<br/>
<p style="margin-left: 40px">Se você tiver configurado um clipe da Web para ser aberto apenas no navegador gerenciado e o navegador gerenciado não estiver instalado em um dispositivo, o aplicativo Portal da Empresa no dispositivo solicitará que o usuário instale o navegador gerenciado para que o clipe da Web possa ser instalado.
  <!---TFS 1228570--->

__Windows__
<p style="margin-left: 40px">**Botão de comentários adicionado ao aplicativo do Portal da Empresa do Windows Phone 8.1**<br/>
<p style="margin-left: 40px">O aplicativo de Portal da Empresa do Windows Phone 8.1 permite aos usuários finais enviar comentários sobre o aplicativo usando um novo botão "enviar comentários". Para localizar o botão, os usuários tocam no menu de "reticências" na parte inferior direita da tela do aplicativo de Portal da Empresa e em **enviar comentários**. Os comentários anônimos coletados ajudarão a Microsoft a aprimorar a experiência do aplicativo do Portal da Empresa para os usuários.
<!---TFS 1317806--->

### <a name="intune-glossarybr"></a>Glossário do Intune</br>
Adicionamos um novo [tópico de glossário](https://docs.microsoft.com/intune/understand-explore/intune-glossary) na biblioteca para ajudá-lo a entender alguns dos termos usados no produto Intune.

### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new-in-microsoft-intune.md) para saber detalhes sobre os desenvolvimentos mais recentes.



<!--HONumber=Nov16_HO2-->


