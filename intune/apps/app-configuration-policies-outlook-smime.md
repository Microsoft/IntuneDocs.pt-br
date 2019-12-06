---
title: Configurar o S/MIME com o Outlook para iOS no Microsoft Intune
description: Compreenda o S/MIME com o Outlook para iOS no Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: lance
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1b2f483415d050486ae9979899d9308154a9b131
ms.sourcegitcommit: a7b479c84b3af5b85528db676594bdb3a1ff6ec6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74411353"
---
# <a name="configure-smime-with-outlook-for-ios"></a>Configurar o S/MIME com o Outlook para iOS

Extensões S/MIME fornecem uma camada adicional de segurança para emails enviados para e de uma conta do Exchange ActiveSync (EAS). O [Microsoft Outlook](https://aka.ms/omsmime) pode utilizar o S/MIME para permitir que os usuários criptografem mensagens de saída e anexos, garantindo que somente o destinatário pretendido possa ler e acessar o conteúdo da mensagem ao utilizar contas do Office 365. Os usuários também podem assinar digitalmente uma mensagem, o que permite aos destinatários verificar a identidade do remetente e confirmar que a mensagem não foi adulterada. Essa funcionalidade é possível com o uso de certificados. Para saber mais, confira [Compreender o S/MIME](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65)?redirectedfrom=MSDN).

> [!NOTE]
> Este tópico descreve como implantar certificados raiz confiáveis por meio do [Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431). O Gerenciador de Ponto de Extremidade da Microsoft é uma plataforma única e integrada de gerenciamento de pontos de extremidade para gerenciar todos os seus pontos de extremidade. Esse centro de administração do Gerenciador de Ponto de Extremidade da Microsoft integra o ConfigMgr e o Microsoft Intune.

## <a name="about-message-encryption"></a>Sobre a criptografia de mensagens
Os usuários poderão enviar mensagens criptografadas para pessoas dentro e fora de suas organizações, se tiverem a parte pública dos certificados de criptografia. As chaves privadas associadas aos certificados de criptografia sempre devem ser protegidas e guardadas pelo destinatário da mensagem criptografada. A chave privada do certificado de criptografia é usada para descriptografar a mensagem pelo destinatário.

Mensagens criptografadas podem ser lidas apenas pelos destinatários que possuem o certificado correspondente àquele que as criptografou. Se você tentar enviar uma mensagem criptografada para destinatários cujo certificado de criptografia não está disponível, o aplicativo solicitará que você remova esses destinatários antes de enviar o email.

## <a name="about-digital-signatures"></a>Sobre assinaturas digitais
Uma mensagem assinada digitalmente garante ao destinatário que a mensagem não foi adulterada e que a identidade do remetente é autêntica. Os destinatários só poderão verificar a assinatura digital se estiverem usando um cliente de email com suporte para S/MIME.

## <a name="prerequisites"></a>Pré-requisitos
- O Outlook para iOS dá suporte ao S/MIME apenas em contas do Office 365.
- O S/MIME deve estar configurado para o Office 365. Para saber mais, confira [Como configurar o S/MIME no Office 365](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/How-to-Configure-S-MIME-in-Office-365/ba-p/584516).
- Você deve ter uma Autoridade de Certificação capaz de emitir certificados que possam ser usados para assinatura e criptografia.
- Implante certificados raiz confiáveis por meio do Gerenciador de Ponto de Extremidade. Para saber mais, confira [Criar perfis de certificado confiáveis](~/protect/certificates-configure.md#create-trusted-certificate-profiles).
- Certificados de criptografia devem ser importados para o Gerenciador de Ponto de Extremidade. Para saber mais, confira [Configurar e usar certificados PKCS importados com o Intune](~/protect/certificates-imported-pfx-configure.md).
- Instale e configure o Conector PFX para o Microsoft Intune. Para saber mais, confira [Baixar, instalar e configurar o Conector de Certificados PFX para o Microsoft Intune](~/protect/certificates-imported-pfx-configure.md#download-install-and-configure-the-pfx-certificate-connector-for-microsoft-intune).
- Os dispositivos devem estar registrados no MDM para receber certificados S/MIME e certificados raiz confiáveis automaticamente do Gerenciador de Ponto de Extremidade.

> [!IMPORTANT]
> Você deve baixar e instalar o conector PFX atualizado (versão 6.1911.11.0 ou posterior) para o Microsoft Intune a fim de usar certificados de criptografia S/MIME com o Outlook para iOS.

## <a name="smime-support-in-outlook-for-ios"></a>Suporte ao S/MIME no Outlook para iOS
O Outlook para iOS dá suporte à assinatura e à criptografia S/MIME de mensagens usando certificados. Muitos clientes possuem certificados de assinatura e criptografia separados, em vez de terem um único certificado que dê suporte para assinatura e criptografia ao mesmo tempo. Certificados de assinatura geralmente são únicos nos dispositivos registrados de um usuário individual, enquanto certificados de criptografia são compartilhados nos dispositivos registrados de um usuário individual. Geralmente, os usuários usam o S/MIME há anos e terão usado certificados de criptografia diferentes ao longo do tempo à medida que estes forem renovados. Os históricos de certificados de criptografia, incluindo suas chaves privadas, devem estar presentes no dispositivo do usuário para que o email que talvez tenha sido criptografado com qualquer um desses certificados no passado possa ser lido. Também é possível ter um único certificado com suporte para assinatura e criptografia.

O Outlook para iOS dá suporte a duas maneiras de entregar certificados aos dispositivos, para que eles possam ser usados para S/MIME:

- **Usuários** podem enviar certificados S/MIME por email para si mesmos e instalá-los por meio de anexos no Outlook para iOS em seus dispositivos móveis.
- **Administradores** podem importar históricos de certificados de criptografia de qualquer Autoridade de Certificação para o Gerenciador de Ponto de Extremidade. O Gerenciador de Ponto de Extremidade entregará automaticamente esses certificados para qualquer dispositivo que o usuário registre. Geralmente, o protocolo SCEP é usado para assinar certificados. Com o SCEP, a chave privada é gerada e armazenada no dispositivo registrado, e um certificado exclusivo é entregue a cada dispositivo que um usuário registra, que pode ser usado para não repúdio. Os administradores importam históricos de certificados de criptografia para seus usuários no Gerenciador de Ponto de Extremidade, que então fornecerá todos os certificados de criptografia dos usuários para qualquer dispositivo que eles registrarem. Por fim, o Gerenciador de Ponto de Extremidade dá suporte a credenciais derivadas para clientes que precisam de suporte para o padrão NIST 800-157. No iOS, o Portal da Empresa é usado para recuperar certificados de autenticação e criptografia do Intune.

## <a name="configuring-outlook-for-ios-smime-in-endpoint-manager"></a>Configurar o S/MIME do Outlook para iOS no Gerenciador de Ponto de Extremidade
Para configurar o S/MIME do Outlook para iOS no Gerenciador de Ponto de Extremidade, incluindo a entrega automática de certificados S/MIME que o Outlook para iOS pode usar, execute as seguintes etapas:

### <a name="add-the-microsoft-outlook-app"></a>Adicionar o aplicativo Microsoft Outlook
1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Adicione o aplicativo Microsoft Outlook para iOS da loja de aplicativos ao Gerenciador de Ponto de Extremidade ou sincronize o Outlook para iOS no Programa de Compras por Volume da Apple. Para saber mais, confira [Adicionar aplicativos da loja do iOS ao Microsoft Intune](~/apps/store-apps-ios.md) ou [Como gerenciar aplicativos iOS e macOS adquiridos no Programa de Compras por Volume da Apple com o Microsoft Intune](~/apps/vpp-apps-ios.md).

### <a name="create-the-outlook-for-ios-smime-configuration-policy"></a>Criar a política de configuração do S/MIME do Outlook para iOS

As etapas a seguir permitem criar e configurar a política de S/MIME do Outlook para iOS no Gerenciador de Ponto de Extremidade. Essas configurações fornecem a entrega automatizada dos certificados de autenticação e criptografia.

1. No [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), selecione **Aplicativos** > **Políticas de configuração de aplicativos** > **Adicionar**.<br>
O painel **Adicionar política de configuração** será exibido.
2. Insira o **Nome** e a **Descrição** da política de configuração.
3. Selecione **Dispositivos gerenciados** como o **Tipo de registro do dispositivo**.
4. Selecione **iOS/iPadOS**  como a **Plataforma**.
5. Clique em **Selecione o aplicativo necessário** para encontrar e associar o aplicativo Microsoft Outlook para iOS que você adicionou anteriormente. 
6. Clique em **Definições de configuração** para adicionar definições de configuração. 
    - Selecione **Usar designer de configuração** ao lado de **Formato de definições de configuração** e aceite as configurações padrão. Para obter mais informações, confira [Definições de configuração do Microsoft Outlook](~/apps/app-configuration-policies-outlook.md).
7. Clique em **S/MIME**  para exibir as **Configurações de S/MIME do Outlook**.

    ![Captura de tela das configurações de S/MIME do Outlook para iOS](./media/app-configuration-policies-outlook-smime/app-configuration-policies-outlook-smime-01.png)

8. Defina **Habilitar S/MIME**  como **Sim**.
9. Defina **Implantar certificados S/MIME do Intune** como **Sim**.
10. Em **Certificado de autenticação**, ao lado de **Tipo de perfil de certificado**, escolha uma das seguintes opções:
    - **SCEP** – Cria um certificado que é exclusivo para o dispositivo e o usuário e que pode ser usado pelo Microsoft Outlook para assinatura. Para obter informações relacionadas, confira [Configurar a infraestrutura para dar suporte ao SCEP com o Intune](~/protect/certificates-scep-configure.md) e [Criar um perfil de certificado SCEP](~/protect/certificates-profile-scep.md#create-a-scep-certificate-profile). 
    - **Certificados importados PKCS** - Usa um certificado exclusivo para o usuário, mas que pode ser compartilhado entre dispositivos e foi importado para o Gerenciador de Ponto de Extremidade pelo administrador em nome do usuário. O certificado é entregue em qualquer dispositivo que um usuário registre. O Endpoint Manager selecionará automaticamente o certificado importado com suporte para assinatura para entrega ao dispositivo que corresponde ao usuário registrado.
    - **Credenciais derivadas** - Usa um certificado que já está no dispositivo e pode ser usado para assinatura. O certificado deve ser recuperado no dispositivo, usando os fluxos de credenciais derivados no Intune.
11. Em **Certificado de criptografia**, ao lado de **Tipo de perfil de certificado**, escolha uma das seguintes opções:
    - **Certificados importados PKCS**  - Entrega todos os certificados de criptografia que foram importados para o Gerenciador de Ponto de Extremidade pelo administrador em qualquer dispositivo registrado por um usuário. O Gerenciador de Ponto de Extremidade selecionará automaticamente os certificados importados com suporte a criptografia para entrega ao dispositivo que corresponde ao usuário registrado.
    - **Credenciais derivadas** - Usa um certificado que já está no dispositivo e pode ser usado para assinatura. O certificado deve ser recuperado no dispositivo, usando os fluxos de credenciais derivados no Intune.
12. Ao lado de **Notificações do usuário final**, opte por notificar os usuários finais, selecionando **Portal da Empresa** ou **Email** para recuperar certificados S/MIME do Outlook para iOS.

    No iOS, os usuários devem usar o aplicativo Portal da Empresa para recuperar seus certificados S/MIME. O Gerenciador de Ponto de Extremidade informará ao usuário que ele precisa iniciar o Portal da Empresa para recuperar seus certificados S/MIME por meio da seção Notificações do Portal da Empresa, de uma notificação por push e/ou um de email. Clicar em uma das notificações levará o usuário a uma página de aterrissagem que o informa sobre o andamento da recuperação dos certificados. Depois que os certificados forem recuperados, o usuário poderá usar o S/MIME no Microsoft Outlook para iOS para assinar e criptografar emails.
    
    As notificações do usuário final incluem as seguintes opções:
       - **Portal da Empresa** – Se selecionado, os usuários receberão uma notificação por push em seus dispositivos, que irá levá-los até a página de aterrissagem no Portal da Empresa, onde os certificados S/MIME serão recuperados.
        - **Email** – Envia um email ao usuário final, informando que ele precisa iniciar o Portal da Empresa para recuperar seus certificados S/MIME. Se o usuário estiver no dispositivo iOS registrado quando clicar no link do email, ele será redirecionado ao Portal da Empresa para recuperar seus certificados.
    
13. Selecione **Atribuições** para atribuir a política de configuração do aplicativo aos grupos do Azure AD. Para saber mais, confira [Atribuir aplicativos a grupos com o Microsoft Intune](~/apps/apps-deploy.md).

## <a name="next-steps"></a>Próximas etapas

- Para saber mais, confira [Políticas de configuração de aplicativos do Microsoft Intune](app-configuration-policies-overview.md).
