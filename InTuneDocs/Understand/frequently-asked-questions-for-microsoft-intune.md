---
# required metadata

title: Perguntas frequentes | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a8126cca-9ec4-454b-a20b-dc1bb6797327

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Perguntas frequentes sobre o Intune
Este artigo responde às perguntas mais frequentes sobre o Intune. Se você não vir uma resposta à sua pergunta aqui, [fale conosco](https://microsoftintune.uservoice.com/).

## Problemas gerais

-   **Como saber quando o serviço Intune foi atualizado?**

    Faça logon na sua conta em manage.microsoft.com. Na Visão Geral de Administração, escolha **Exibir Status do Serviço**. O local do seu locatário e a agenda de manutenção são listados lá. Leia sobre as atualizações do serviço no artigo [Novidades](/intune/deploy-use/whats-new-in-microsoft-intune).

-   **Se um usuário renomear um dispositivo no aplicativo Portal da Empresa esse nome será alterado no Intune ou no Configuration Manager?**

    Não, essa alteração de nome é apenas para conveniência do usuário.

-   **Existe uma funcionalidade de assistência remota no Intune para dispositivos móveis?**

    Não, não existe. Aplicativos de terceiros, como [Bomgar](http://www.bomgar.com/) <!---and [TeamViewer](https://www.teamviewer.com/)---> podem ser úteis.

## Contas

-   **Se eu começar a avaliar o Intune e criar um novo locatário para a avaliação, posso adicionar Office 365 à avaliação usando o mesmo locatário?**

    Sim. Basta entrar usando o administrador global da assinatura/locatário do Intune existente, como *globaladmin@&lt;empresa&gt;.onmicrosoft.com*.

-   **Se eu atribuir autoridade MDM durante uma assinatura de avaliação, isso dificulta alternar para o serviço de outra empresa se mudar de ideia sobre o Intune?**

    Embora seja difícil imaginar que você não adequar-se com o Intune, a escolha de autoridade MDM não afeta sua capacidade de mover para outro serviço. É especificamente sobre escolher Intune ou Intune com System Center Configuration Manager.

-   **Posso usar meu nome de domínio existente do Office 365 para minha conta do Intune subsequente?**

    Sim, se você entrar com a ID organizacional que está associada ao locatário existente do Office 365 e o domínio verificado ao criar a avaliação do Intune ou ativar as licenças.

    O Intune usará o mesmo domínio/usuários/etc. da sua conta do Office 365. Observe que cada usuário do Office 365 precisa ser habilitado como um usuário Intune, usando uma licença do Intune. Isso precisa ser feito pelo administrador global que gerencia o locatário.

## Registro

-   **Onde meus usuários podem aprender a registrar seus dispositivos?**

    Você pode usar ou personalizar informações das [Instruções de registro do Intune do usuário final para administradores de TI](https://gallery.technet.microsoft.com/End-user-Intune-enrollment-55dfd64a).

-   **Como posso solucionar problemas do registro do dispositivo?**

    Modos de solucionar problemas comuns de registro são fornecidos em [Solucionar problemas de registro de dispositivo no Intune](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune).

-   **Como posso coletar logs de registro se um usuário tiver um problema de registro?**

    Siga [essas instruções](http://www.microsoft.com/en-us/download/46391).

## Gerenciamento de dispositivos móveis

-   **MDM geral**

    -   **O Intune detecta se um dispositivo está com jailbreak?**

        Sim, para alguns sistemas operacionais. Para obter informações sobre como gerenciar dispositivos desbloqueados, consulte [Create a device compliance policy (Criar uma política de conformidade do dispositivo)](/intune/deploy-use/create-a-device-compliance-policy-in-microsoft-intune.md).

    -   **Posso limpar seletivamente dados corporativos de um dispositivo?**

        Sim. Para informações sobre apagamento seletivo, consulte [Help protect your data with remote wipe, remote lock, or passcode reset (Ajude a proteger seus dados com apagamento remoto, bloqueio remoto ou redefinição de senha)](/intune/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune.md).

    -   **Há uma maneira de bloquear determinados sites no navegador do dispositivo móvel por meio do Intune?**

        Não no navegador nativo de qualquer plataforma. No entanto, você pode permitir ou bloquear URLs depois de implantar o navegador da Web gerenciado por Intune em dispositivos iOS e Android. Para obter mais informações, consulte [Manage Internet access using managed browser policies (Gerenciar o acesso à Internet usando políticas de navegador gerenciado)](/intune/Deploy-Use/Manage-Internet-access-using-managed-browser-policies-with-Microsoft-Intune.md).

    -   **É possível impedir um usuário de desinstalar um aplicativo?**

        Em geral, não. No entanto, em um dispositivo iOS supervisionado você pode impedir que um usuário desinstale um aplicativo distribuído usando o Apple Configurator. 

    -   **Há uma maneira de gerenciar o uso de dados móveis?**

        Não diretamente, mas você pode garantir que o Wi-Fi seja o método preferencial de conexão enviando perfis de Wi-Fi para os dispositivos, conforme descrito em [Ajudar usuários a se conectarem às redes da empresa usando perfis de Wi-Fi](/intune/Deploy-Use/wi-fi-connections-in-microsoft-intune.md). Além disso, algumas plataformas (por exemplo, iOS e Android KNOX) oferecem a capacidade de controlar configurações como voz e roaming de dados.

    -   **Há uma maneira de impedir que um usuário cancele o registro de um dispositivo? E se ele for um dispositivo da empresa?**

        Em geral, não. No entanto, ao usar as configurações personalizadas do Windows Phone, você pode impedir o cancelamento do registro do usuário no Windows Phone 8.1. Além disso, para dispositivos iOS supervisionados e registrados no DEP (Programa de Registro do Dispositivo) da Apple, é possível impedir um usuário de cancelar o registro de um dispositivo.

    -   **Posso mudar minha autoridade MDM escolhida?**

        Você pode mudar a autoridade MDM em algumas situações. Para isso, entre em contato com suporte, conforme descrito em [Como obter suporte para o Microsoft Intune](/intune/Troubleshoot/How-to-get-support-for-Microsoft-Intune.md). A tabela a seguir descreve as alterações que são possíveis. Alterações na autoridade MDM exigem um novo registro de dispositivos.

        ||**To:** Intune!**To:** O365|**To:** Configuration Manager com o Intune| |**From:** Intune| |Yes&#42;|Yes| |**From:** O365||Yes&#42;||Yes| |**From:** Configuration Manager com o Intune|Yes|Yes| |
        
        &#42;As autoridades MDM do O365 e do Intune podem coexistir. Você não precisará registrar novamente os dispositivos móveis.



-   **Windows**

    -   **É possível realizar sideload de um aplicativo da Windows Store?**

        Não é possível realizar sideload de aplicativos publicamente disponíveis. Mesmo que você consiga baixar o XAP, você não pode carregá-lo Intune porque ele é um XAP público, criptografado e assinado com o certificado de assinatura de código do desenvolvedor. Somente nos aplicativos que você desenvolver e entrar com seu próprio certificado de assinatura de código você pode realizar sideload.

    -   **Aplicativos do Windows Phone Store distribuídos por meio do Portal da Empresa exigem que o usuário final tenha uma Conta da Microsoft?**

        Sim, o usuário final não poderá obter os aplicativos sem uma Conta da Microsoft. É realizado sideload da exceção, aplicativos LOB particulares que podem ser implantados em um dispositivo sem uma Conta da Microsoft.

    -   **Uma Conta da Microsoft é necessária em um Windows Phone 8.1 para que ele seja gerenciado pelo Intune?**

        Não. No entanto, ela será necessária para instalar a maioria dos aplicativos da loja pública.

        **Por que o Windows Phone pede um certificado Symantec para gerenciamento?**
        O Windows Phone controla como você pode instalar aplicativos. Qualquer usuário com uma conta da Microsoft pode instalar aplicativos da loja do Windows Phone, ou empresas podem instalar ou fazer sideload de seus aplicativos de linha de negócios (LOB) desenvolvidos internamente usando um processo especial descrito na documentação do Windows Phone. Ao instalar aplicativos de LOB, dispositivos Windows Phone confiam apenas em um tipo especial de certificado emitido pela Symantec. Você não pode usar nenhum outro certificado gerado de modo comercial ou privado. Esse requisito se aplica a todas as soluções de gerenciamento de dispositivos móveis, não só ao Intune.

        O certificado da Symantec cria um token de registro de aplicativo (AET). O AET pode ser instalado em um dispositivo quando o dispositivo é registrado para o gerenciamento de dispositivo móvel, ou pode ser instalado fora de banda por meio de um site seguro ou um anexo de email. Administradores devem assinar todos os aplicativos de LOB com o certificado da Symantec, usando as ferramentas fornecidas no [SDK do Windows Phone](http://go.microsoft.com/fwlink/?LinkId=268439). Quando os usuários tentam instalar aplicativos de LOB, o sistema operacional do Windows Phone verifica a assinatura do AET em relação à assinatura no aplicativo. Se as assinaturas forem correspondentes, a instalação pode continuar. Se o AET não puder ser verificado, a instalação falha. Há várias razões pelas quais o AET pode não ser verificado:

        -   O AET nunca foi instalado no dispositivo

        -   O AET expirou

        -   O AET não foi criado usando o mesmo certificado da Symantec usado para assinar o aplicativo

        O Windows Phone não pede que o AET esteja presente durante o registro no MDM, mas, antes da versão de novembro de 2014, o Intune pedia o AET e um ssp.xap assinado, porque não havia outra forma de instalar o AET e o ssp.xap que não fosse durante o registro.

    **Como o AET é criado para usuários do Intune?**
  Quando administradores carregam o arquivo .pfx de seu certificado da Symantec, o Intune cria o AET automaticamente e o implanta nos dispositivos Windows Phone registrados. Administradores do Intune não precisam usar a ferramenta de geração de AET no SDK do Windows Phone.

      > [!IMPORTANT] O Intune não dá suporte à criação manual do AET e à sua implantação fora de banda.

    **Quais alterações foram feitas para reduzir o requisito de um certificado da Symantec?**
       Na versão de novembro de 2014, o Intune fez alterações para permitir cenários em que as empresas não têm um certificado da Symantec.

       -   O Portal da Empresa para Windows Phone 8.1 está disponível para instalação na loja, portanto não precisa ser assinado com um certificado da Symantec e validado em relação a um AET. Em vez disso, o aplicativo é validado como parte do processo de publicação na loja.

        -   Dispositivos Windows Phone 8.1 podem ser registrados com ou sem um AET no telefone. Se um AET estiver disponível, ele é instalado na primeira vez que o dispositivo sincroniza com o Intune. Se não houver AET, o dispositivo ainda pode ser gerenciado pelo Intune, e os usuários podem instalar o Portal da Empresa por meio da loja e usar a maioria dos recursos do Portal da Empresa sem um certificado da Symantec para assinar aplicativos.

        Não há nenhuma alteração do requisito de Symantec para dispositivos Windows Phone 8. Dispositivos Windows Phone 8 devem ter o ssp.xap assinado e o AET presentes durante o registro ou não poderão ser registrados.

        **Qual funcionalidade tem suporte se um dispositivo Windows Phone 8.1 está registrado, mas não tem um certificado da Symantec?**
        Se um dispositivo Windows Phone 8.1 está registrado, mas não tem um certificado da Symantec, você pode:

        -   Criar políticas e enviá-las por push para o dispositivo

        -   Configurar informações de contato para o departamento de TI, que são exibidas no Portal da Empresa

        -   Criar links profundos para a loja e implantá-los no Portal da Empresa

        -   Criar links para páginas da web e implantá-los no Portal da Empresa

        -   Criar termos e condições que devem ser aceitos pelos usuários para que eles possam usar o Portal da Empresa

        A única coisa que você não pode fazer sem um certificado da Symantec é implantar aplicativos de LOB.

        > [!IMPORTANT]
        > O fornecedor de software do Intune não verifica se os aplicativos estão assinados quando você os carrega. Se você implanta aplicativos não assinados, eles falham quando os usuários tentam instalá-los.

        **O que os usuários podem fazer se tiverem o Portal da Empresa, mas não tiverem um certificado da Symantec?**
        Dispositivos Windows Phone 8.1 não precisam estar registrados para que os usuários instalem o Portal da Empresa por meio da loja. Se o dispositivo não estiver registrado, os usuários são solicitados a registrar. Tocar o prompt no Portal da Empresa leva os usuários diretamente a **Configurações/Local de Trabalho**, em que eles podem registrar seus dispositivos.

        Mesmo sem registrar o dispositivo, os usuários podem executar as seguintes ações com o Portal da Empresa instalado por meio da loja:

        -   Aceitar ou recusar termos e condições configurados pelo administrador. Se os usuários recusam os termos e condições, o Portal da Empresa fecha.

        -   Exibir as informações de contato do departamento de TI

        -   Exibir qualquer dispositivo registrado, incluindo dispositivos iOS, Android e Windows

        -   Usar links profundos para aplicativos na loja

        -   Usar links da web para abrir páginas da web

        Com o dispositivo registrado, os usuários podem exibir o dispositivo na lista **Meus dispositivos** . Depois de registrado, o dispositivo está sujeito a qualquer política do Intune implantada. Os dispositivos devem estar registrados para receber o AET e instalar aplicativos e LOB. Um dispositivo não registrado que tenta instalar um aplicativo de LOB é encaminhado para o registro.

        A única coisa que os usuários não podem fazer se a empresa não tiver um certificado da Symantec é instalar aplicativos de LOB implantados pelo administrador.

        **Nossa empresa já tem um certificado e está registrando dispositivos Windows Phone 8.1. Eu tenho que fazer algo de outra forma, agora que o Portal da Empresa está disponível na loja?**
        O ssp.xap atual do Centro de Download ainda funciona em dispositivos Windows Phone 8.1. Você pode continuar orientando os usuários a se registrarem e receberem o portal da empresa durante a instalação.

        **Quais são as vantagens e desvantagens de usuários que obtêm o Portal da Empresa na loja?**
        Vantagens:

        -   Os usuários recebem links profundos e links da web, mesmo se o dispositivo Windows Phone 8.1 não estiver registrado

        -   Quando a Microsoft atualiza o Portal da Empresa, o aplicativo da loja é atualizado automaticamente, sem precisar baixar, assinar e reimplantar o ssp.xap

        -   A documentação para usuários de Windows Phone 8.1, iOS, Android e Windows é consistente: "Vá para a loja e instale o Portal da empresa."

        -   Os usuários veem o aplicativo conforme ele instala e recebem instruções para o registro quando ele abre

        Desvantagens:

        -   Os usuários veem uma caixa de seleção para instalar um "**hub da empresa**", mas nada os direciona para o Portal da Empresa na lista de aplicativos do dispositivo

        -   Os usuários não precisam aceitar termos e condições personalizados antes de abrir o Portal da Empresa

        Nas seguintes circunstâncias, você pode continuar orientando os usuários a se registrarem e instalarem o ssp.xap durante o registro:

        -   Se a empresa bloqueia o acesso à loja por meio do Windows Phone, o ssp.xap deve ser instalado durante o registro.

        -   Se os usuários não têm contas da Microsoft configuradas em seus dispositivos Windows Phone, eles não podem instalar o Portal da Empresa por meio da loja.

        -   Se a documentação existente para o registro do Windows Phone orientá-los a ir para Configurações, Local de trabalho primeiro, pode demorar um pouco para atualizar os documentos e encaminhar os usuários para a loja.

        **Qual é a diferença entre o ssp.xap no Centro de Download e o aplicativo na loja?**

        -   O Portal da Empresa na loja não precisa ser assinado por um certificado da Symantec para ser instalado

        -   O Portal da Empresa na loja apresenta os termos e condições para o usuário, mas o ssp.xap no Centro de Download não

        -   O Portal da Empresa na loja é um .appx, em vez de um .xap

        **Eu posso obter o arquivo do Portal da empresa e enviá-lo por push aos meus usuários, em vez de encaminhá-los à loja?**
        Sim. O aplicativo do Portal da Empresa pode ser baixado para os seguintes sistemas operacionais do Centro de Download:

        -   Windows Phone 8.1: [http://go.microsoft.com/fwlink/?LinkId=615799](http://go.microsoft.com/fwlink/?LinkId=615799)

        -   Windows Phone 8.0: [http://go.microsoft.com/fwlink/?LinkId=268440](http://go.microsoft.com/fwlink/?LinkId=268440)

        -   Windows 8.1: [http://go.microsoft.com/fwlink/?LinkId=615800](http://go.microsoft.com/fwlink/?LinkId=615800)

        **As empresas ainda podem usar a Ferramenta de Suporte para Gerenciamento de Avaliação do Windows Intune para Windows Phone se não tiverem um certificado da Symantec, e seus usuários ainda podem instalar o Portal da Empresa por meio da loja?**
        Sim. Se você precisa fazer uma verificação de conceito que inclui a instalação de aplicativos de LOB, a ferramenta de avaliação de gerenciamento funciona com a versão da loja do Portal da Empresa. No entanto, como o AET do certificado da Symantec não é mais necessário para registrar dispositivos Windows Phone 8.1, as empresas podem testar a instalação do aplicativo usando links profundos para aplicativos na loja.

        A Ferramenta de Suporte para Gerenciamento de Avaliação do Windows Intune do Windows Phone é somente para assinaturas de avaliação do Intune.

        > [!IMPORTANT]
        > Use somente os testes da ferramenta de avaliação de gerenciamento. Dispositivos registrados com o AET da ferramenta de avaliação de gerenciamento devem cancelar o registro e registrar novamente se o certificado da Symantec para a ferramenta de avaliação de gerenciamento não estiver mais disponível ou se a empresa obtiver seu próprio certificado da Symantec para assinar aplicativos.

        **As empresas podem começar sem um certificado da Symantec e adicionar um posteriormente, mesmo depois que os dispositivos Windows Phone 8.1 forem registrados?**
        Sim. Mesmo se os dispositivos Windows Phone 8.1 já estiverem registrados, você pode obter um certificado da Symantec, assinar o ssp.xap, carregá-lo e carregar o arquivo pfx. O Intune gera o AET. Dispositivos Windows Phone 8.1 recebem o AET na próxima vez que sincronizarem, com limite de oito horas. Espere pelo menos oito horas antes de implantar aplicativos de linha de negócios depois de carregar o xap e o pfx.


-   **Android**

    -   **Quanto tempo demora para criptografar um dispositivo Android?**

        Isso depende principalmente da velocidade do processador do dispositivo e a quantidade de memória total e usada e não é uma função do Intune.

-   **iOS**

    -   **Ao implantar aplicativos do iOS com o Intune, se o arquivo de manifesto e de IPA do aplicativo forem carregados; o dispositivo precisa ter uma ID da Apple especificada para continuar a instalação?**

        Não. Quando o Intune estiver fornecendo os bits (carregado por IPA para o Intune), é realizado sideload dos aplicativos e eles não requerem uma ID da Apple.

    -   **Há uma maneira de habilitar a instalação de aplicativos em iOS sem permitir o acesso à Apple Store?**

        Não, mas você pode habilitar a App Store e usar aplicativos permitidos e bloqueados no iOS para acompanhar o que os usuários estão fazendo. Aplicativos de LOB com sideload não exigem acesso ao aplicativo da Apple App Store.

    -   **Os aplicativos da Apple Store distribuídos por meio do Portal da empresa exigem que o usuário final tenha uma conta do iTunes?**

        Sim, o usuário final não poderá obter os aplicativos sem uma conta do iTunes.

    -   **Posso bloquear a App Store?**

        Sim, é possível, mas isso bloqueará todas as instalações de aplicativos e atualizações da App Store, não apenas aquelas iniciadas pelo usuário final. Isso significa que qualquer aplicativo público da loja de aplicativos implantado por meio do Intune também pode falhar.

## Implantação de aplicativos

-   **Como adicionar um aplicativo recomendado?**

    No Intune, eles são chamados de "aplicativos em destaque" e documentados em [Implantar aplicativos no Microsoft Intune](/Intune/Deploy-Use/deploy-apps-in-microsoft-intune.md).

-   **Posso obter armazenamento em nuvem adicional para aplicativos que desejo implantar?**

    Sim. Você pode ler sobre isso em [Implantar aplicativos](/Intune/Deploy-Use/deploy-apps.md), na seção *Requisitos de armazenamento em nuvem*.

## Segurança 

-   **O BitLocker pode ser imposto pelo Intune?**

    O agente do OMA-DM no Windows 8.1/RT permite que você leia (obtenha) o status de criptografia. Você não pode defini-lo. Isso é verdadeiro para o Intune e outros serviços de gerenciamento de dispositivo móvel.

-   **Se eu criptografar um tablet Windows 8 usando o BitLocker, posso impor apagamento completo do dispositivo se um usuário falhar consecutivamente ao fazer logon várias vezes?**

    Não há nenhuma opção para apagamento completo em dispositivos Windows 8.1/RT para qualquer serviço de gerenciamento de dispositivos móveis, incluindo Intune. O Intune fornece apagamento seletivo para esses dispositivos. Para obter mais informações sobre o apagamento/apagamento seletivo no Intune, consulte [Protect apps and data with Microsoft Intune (Proteger aplicativos e dados com o Microsoft Intune)](/intune/Deploy-Use/protect-apps-and-data-with-microsoft-intune.md).

## Portal da Empresa

-   **Posso personalizar meu Portal da empresa?**

    Sim. No console de administração do Intune, vá para **Admin&gt;Portal da Empresa** para essas configurações.

## Microsoft Intune com Configuration Manager

-   **Quando uso o Configuration Manager com o Intune, onde gerencio meus dispositivos?**

    Gerencie todos os seus dispositivos no console do Configuration Manager, embora os dispositivos com o agente do Intune instalado neles aparecerão no console do Intune. Os dispositivos móveis não aparecerão no console do Intune.

-   **Posso fazer um apagamento seletivo em dispositivos?**

    Se você estiver usando o System Center 2012 R2 Configuration Manager ou posterior com o Intune, você pode fazer um apagamento seletivo que remove dados da empresa. Para obter mais informações, consulte [Protect apps and data with Microsoft Intune (Proteger aplicativos e dados com o Microsoft Intune)](/intune/Deploy-Use/protect-apps-and-data-with-microsoft-intune.md).

-   **Se estiver usando o Configuration Manager com o Intune, ainda posso usar o Portal de Administrador do Intune?**

    É possível, mas somente computadores com o agente Intune instalado poderão ser gerenciados nesse portal. Também há algumas outras informações úteis no portal sobre alertas do serviço, o status do serviço, etc., mas nenhuma configuração de gerenciamento de dispositivo se aplicará a dispositivos registrados.



<!--HONumber=Jun16_HO2-->


