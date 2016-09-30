---
title: Novidades | Microsoft Intune
description: "Descubra as novidades deste mês e os lançamentos anteriores do Microsoft Intune"
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 09/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5b3256852431efb83fb2cc9fa067dd3f4a68a050
ms.openlocfilehash: cef0a26204a22c95d2b639500246e435fcf7f9f7


---

# Novidades do Microsoft Intune – Setembro
Conheça as novidades nesta versão do Microsoft Intune. Você também pode descobrir sobre alterações futuras que você deve estar planejando, bem como informações sobre versões anteriores.

Todos esses recursos eventualmente terão suporte para implantações híbridas de clientes (Configuration Manager com o Intune). Para obter mais informações sobre os novos recursos híbridos, confira a [página Hybrid What’s New](https://technet.microsoft.com/library/mt718155.aspx) (Novidades do Híbrido).
<!---@Barry, the above blurb stays in each version, but make sure Tyler signs off each time. Also, remember to set the ms.date in the metadata to the sprint release. --->

>[!IMPORTANT]
>Postagem do blog - garantir que dispositivos móveis sejam atualizados usando o Microsoft Intune<br>
>Levando em consideração os ataques de malware "Trident" recentes em dispositivos iOS, publicamos uma nova postagem no blog, [Ensuring mobile devices are up to date using Microsoft Intune](https://blogs.technet.microsoft.com/enterprisemobility/2016/08/26/ensuring-mobile-devices-are-up-to-date-using-microsoft-intune/) (Garantindo que os dispositivos móveis sejam atualizados usando o Microsoft Intune) para ajudar você a saber mais sobre as diferentes maneiras em que o Intune pode ajudar a manter seus dispositivos seguros e atualizados.

## suporte para iOS 10
Os cenários existentes do Intune MDM e MAM são compatíveis com iOS 10. Para obter dicas, consulte o [Blob da Equipe de Suporte do Intune](https://blogs.technet.microsoft.com/intunesupport/2016/09/13/support-tip-intune-support-for-ios-10/).

## A Ferramenta de Disposição do Aplicativo dá suporte ao MAM sem registro de dispositivo para Android e iOS
A Ferramenta de Disposição do Aplicativo do Intune é uma ferramenta de linha de comando usada para habilitar o Intune MAM em aplicativos de linha de negócios (LOB) para iOS e Android. Esta é a maneira mais simples de incorporar o SDK do MAM do Intune em seu aplicativo, para que seu aplicativo possa impor políticas MAM implantadas por meio do Intune. Ao usar políticas MAM, você pode:

1. Criptografar os dados do aplicativo.
2. Exigir que o trabalhador de informações insira um PIN ao iniciar o aplicativo.
3. Permitir que o aplicativo transfira dados apenas para outros aplicativos gerenciados.
4. Impedir que o aplicativo faça backup de dados para Android, iTunes e iCloud.
5. Permitir que somente Recortar, Copiar e Colar em e fora de outros aplicativos gerenciados.

A visualização pública da Ferramenta de Disposição do Aplicativo do Intune atualizada agora dá suporte ao MAM sem registro de dispositivo em aplicativos LOB internos no iOS e Android. Isso significa que os usuários finais não precisam registrar seus dispositivos com o Intune para usar aplicativos LOB habilitados para MAM.

Qualquer pessoa pode testar o software de visualização pública e ler a documentação útil, localizada no GitHub do msintuneappsdk:

http://www.github.com/msintuneappsdk/intune-app-wrapper-ios-preview

http://www.github.com/msintuneappsdk/intune-app-wrapper-android-preview

Antes de instalar e usar o Wrapper do Aplicativo do Microsoft Intune para pré-lançamento para Android e iOS, você deve:

* Examinar os Termos de Licença da Microsoft para a Ferramenta de Disposição do Aplicativo do Microsoft Intune para pré-lançamento para Android e iOS
* Imprimir e guardar uma cópia dos termos de licença para seus registros. Ao baixar e usar a Ferramenta de Disposição do Aplicativo do Microsoft Intune para Pré-lançamento para Android, você concorda com estes termos de licença. Se você não aceitá-los, não use o software.
<!---TFS 1235607--->

## Os grupos do Intune começam a transição para o Azure Active Directory em setembro
Algumas novas contas do Intune usarão os grupos de segurança do Azure Active Directory em vez de grupos de usuários do Intune. Você saberá que você está trabalhando com grupos de segurança porque a página de grupos do portal do Intune terá um link que direciona para o portal de gerenciamento do Azure.

## Integração do Lookout para proteger os dispositivos Android
A Microsoft está se integrando com a solução de proteção de ameaças móveis do Lookout para proteger dispositivos móveis Android ao detectar malware, aplicativos arriscados e muito mais, em dispositivos. A solução do Lookout ajuda você a determinar o nível de ameaça, que é configurável. Você pode criar uma regra de política de conformidade do Intune para determinar a conformidade do dispositivo com base na avaliação de riscos pelo Lookout. Usando políticas de acesso condicional, você pode permitir ou bloquear o acesso aos recursos da empresa com base no status de conformidade do dispositivo.

Os usuários finais de dispositivos não compatíveis serão solicitados a se registrar e deverão instalar o aplicativo Lookout for Work em dispositivos Android, ativar o aplicativo e corrigir ameaças relatadas no aplicativo Lookout for Work para obter acesso. Para saber mais, consulte [Restringir o acesso com base no dispositivo, na rede e no risco do aplicativo](restrict-access-based-on-device-network-app-risk.md).


## Atualizações do Portal da Empresa

### Android

**Acréscimo de “Notificações” ao Portal da Empresa para Android**<br/>
Um novo ícone de Notificações foi acrescentado ao Portal da Empresa para Android na home page. Tocar nesse ícone acessará a página Notificações, que mostra a seus usuários finais todos os itens que exigem atenção no aplicativo Portal da Empresa, como a não conformidade de dispositivo, a atualização de registro e a ativação de registro. O aplicativo de Portal da Empresa para iOS já tem essa experiência de notificações. Ter a nova página de Notificações significa que o usuário não verá a página Configuração de Acesso da Empresa sempre que iniciar ou retomar o Portal da Empresa, contanto que o dispositivo já esteja registrado. Se você criar suas próprias diretrizes para o usuário final, convém atualizar a documentação para refletir essa alteração. Encontre capturas de tela atualizadas [aqui](https://aka.ms/androidcpupdate).  
<!---TFS 1095560--->

**Fornecendo comentários no Portal da Empresa para Android**</br>
Um novo item foi adicionado ao menu do Portal da Empresa para Android. Tocar em **Ajuda e Comentários** mostrará três ações:
* Use **Obter Ajuda** para relatar problemas para seu departamento de TI sobre o Portal da Empresa. O departamento de IT criará um email usando o cliente de email e anexará os logs do Portal da Empresa a ele. **Obter Ajuda** substitui o recurso **Enviar Dados** na página **Configurações**.
* Use **Enviar Comentários** para fornecer comentários à equipe do Portal da Empresa.
* Use **Classificar nosso aplicativo** para deixar no aplicativo do Portal da Empresa uma classificação ou uma análise no Google Play.

### iOS
**Alterações no suporte para o aplicativo Portal da Empresa do iOS**<br/>
Todos os usuários do aplicativo do Portal da Empresa Microsoft Intune para iOS agora devem usar a versão mais recente. Novos usuários só poderão baixar a versão mais recente e os usuários atuais precisarão atualizar para ela. A versão mais recente requer iOS 8.0 ou posterior, por isso dispositivos que executam versões anteriores do iOS não conseguirão usar o Portal da Empresa ou registrar-se até atualizar seu dispositivo para o iOS 8.0 ou posterior, para então atualizar o aplicativo de Portal da Empresa para a versão mais recente. Os dispositivos que executam versões abaixo do iOS 8.0 continuarão a ser gerenciados e listados no Console de Administração do Intune.
<!---TFS 1283165--->

**Melhorias na maneira como os usuários finais do iOS obtêm seus aplicativos**<br/>
As alterações a seguir foram feitas nos blocos de aplicativos no aplicativo Portal da Empresa para iOS para encaminhar os usuários a diferentes modos de exibição em um único local, o site Portal da Empresa, para todos os seus aplicativos. As restrições da Apple proíbem que aplicativos gerenciados e de linha de negócios da app store sejam listados no aplicativo Portal da Empresa e exigem que os usuários acessem diferentes modos de exibição para localizar todos os seus aplicativos.

- Anteriormente, o bloco **Aplicativos da Empresa** apontavam para uma lista de todos os aplicativos na guia TODOS do site Portal da Empresa e continuará funcionando da mesma maneira. O nome do bloco foi alterado para **Todos os Aplicativos**.
- Anteriormente, o bloco **Outros Aplicativos** apontava para um modo de exibição no aplicativo Portal da Empresa que lista todos os aplicativos que Apple permite que o aplicativo Portal da Empresa mostre. O nome do bloco foi alterado para **Aplicativos em Destaque** e, ao tocar no bloco, os usuários são levados para a guia EM DESTAQUE do site Portal da Empresa.
-  O bloco **Categorias** apontava para um modo de exibição no aplicativo Portal da Empresa que lista categorias de aplicativos. O nome do bloco não foi alterado, mas agora ele aponta para a guia CATEGORIAS do site Portal da Empresa.
Você pode encontrar capturas de tela atualizadas [aqui](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).
<!---TFS 1317133--->

**Solicitar a instalação do aplicativo de Navegador Gerenciado do iOS se o profissional de TI definir esse requisito para um aplicativo**<br/>
Se você tiver configurado um clipe da Web para ser aberto apenas no navegador gerenciado e o navegador gerenciado não estiver instalado em um dispositivo, o aplicativo Portal da Empresa no dispositivo solicitará que o usuário instale o navegador gerenciado para que o clipe da Web possa ser instalado.
<!---TFS 1228570--->

### Windows
**Botão de comentários adicionado ao aplicativo de Portal da Empresa do Windows Phone 8.1**<br/>
O aplicativo de Portal da Empresa do Windows Phone 8.1 permite aos usuários finais enviar comentários sobre o aplicativo usando um novo botão "enviar comentários". Para localizar o botão, os usuários tocam no menu de "reticências" na parte inferior direita da tela do aplicativo de Portal da Empresa e em **enviar comentários**. Os comentários anônimos coletados ajudarão a Microsoft a aprimorar a experiência do aplicativo do Portal da Empresa para os usuários.
<!---TFS 1317806--->


## O que está por vir

### Transição de grupos do Intune para os grupos do Azure Active Directory
O Intune está criando uma nova experiência de gerenciamento de grupos que usa os grupos de segurança do AAD (Azure Active Directory) como grupos de usuários e de dispositivos no Intune. Esses grupos serão usados para todo o gerenciamento de grupo, implantação de política e implantação de perfil **quando lançarmos o novo portal de administração do Intune baseado no Azure**.

Essa nova experiência evitará que você precise duplicar grupos entre serviços, **concederá acesso a alguns recursos de grupo novos do AADP (Azure Active Directory Premium)** e fornecerá extensibilidade usando o PowerShell e o Graph. Ela também unificará a experiência de gerenciamento de grupo no gerenciamento de mobilidade empresarial.

Para habilitar a mudança para grupos de segurança, a experiência no **console do administrador** atual passará por algumas modificações. **Essas alterações e o uso de grupos de segurança do AAD serão registrados na documentação do Intune**.

Os cientes que forem novos no Intune verão **algumas das alterações de grupos de segurança antes dos locatários atuais**.

Além das alterações no gerenciamento de grupo, **as seguintes funcionalidades serão preteridas**:
- Exclusão de membros ou grupos ao criar um novo grupo
- Grupos de **Usuários Desagrupados** e **Dispositivos Desagrupados**
- **Gerenciar Grupos** na função Administrador do Serviço
- Alertas personalizados com base em grupo para Regras de Notificação
- Dinamização com grupos em relatórios
<!--- TFS 1295329--->

### Novas política de aplicativo de Acesso Condicional para o Exchange Online e o SharePoint Online
Você poderá restringir o acesso ao Exchange Online e ao SharePoint Online para que o acesso seja somente de aplicativos móveis do Office, como Outlook, Word, Excel e OneDrive. Esse novo recurso se combina perfeitamente com políticas MAM (gerenciamento de aplicativo móvel) do Intune porque você pode bloquear o acesso a clientes de email interno ou outros aplicativos que não foram configurados com as políticas de MAM do Intune. Isso garante que os usuários estão acessando os dados da sua organização com aplicativos que podem ser protegidos usando o MAM do Intune. Você pode começar no gerenciamento de aplicativo móvel do Intune pelo portal do Azure. Procure a nova seção de Acesso Condicional na folha "Configurações".



### Serviço preterido

- **Aplicativos Portal da Empresa para Windows 8 e Windows Phone 8 serão preteridos** <br/>
A partir de outubro de 2016, o Microsoft Intune preterirá o suporte para aplicativos do Portal da Empresa do Windows 8 e Windows Phone 8. O Microsoft Intune também preterirá o suporte para a plataforma Windows Phone 8. Em consequência disso, você não poderá registrar nem atualizar dispositivos Windows Phone 8. Você pode continuar a gerenciar dispositivos Windows Phone 8 e Windows 8 já registrados. Atualize os dispositivos Windows Phone 8 e Windows 8 para Windows 8.1 e Windows Phone 8.1 e use os aplicativos do Portal da Empresa correspondentes do Windows 8.1 e do Windows Phone 8.1 para continuar a distribuir aplicativos para esses dispositivos sem interrupções.



### Roteiro de nuvem
Mantenha-se informado sobre futuros desenvolvimentos do Intune com a [Estratégia de plataforma em nuvem](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).


## Versões anteriores do Intune
Se você quiser ver o que foi lançado no Intune durante os últimos seis meses, consulte a lista no artigo [Previous Intune releases](previous-intune-releases.md) (Versões anteriores do Intune).

### Consulte também
* [Blog do Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Roteiro da Plataforma de Nuvem](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)



<!--HONumber=Sep16_HO4-->


