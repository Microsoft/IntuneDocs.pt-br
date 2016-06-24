---
# required metadata

title: Configurar o acesso a email corporativo usando perfis de email | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 05/05/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 10f0cd61-e514-4e44-b13e-aeb85a8e53ae

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: karanda
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Configurar o acesso a email corporativo usando perfis de email com o Microsoft Intune
Muitas plataformas móveis incluem um cliente de email *nativo* que é fornecido como parte do sistema operacional.  Alguns desses clientes podem ser configuráveis usando perfis de email, descritos neste tópico.

Se você precisar de DLP (prevenção de perda de dados) adicional, escolha [Acesso condicional](restrict-access-to-email-and-o365-services-with-microsoft-intune.md), que controla o acesso à caixa de correio do usuário para qualquer cliente de email, incluindo clientes de email nativos.

As configurações de perfil de email podem ser usadas para definir configurações de acesso de email para clientes de email específicos em dispositivos móveis.   A maioria das plataformas móveis inclui um cliente de email *nativo* que é fornecido como parte do sistema operacional.  Em plataformas com suporte os clientes de email nativos podem ser configurados pelo Microsoft Intune para permitir aos usuários acessar seu email corporativo nos dispositivos pessoais sem qualquer configuração.  

Os administradores de TI ou usuários também podem optar por instalar clientes de email alternativos, por exemplo, o Microsoft Outlook para Android ou iOS.  Esses clientes de email podem não dar suporte a perfis de email e não são configuráveis usando perfis de email do Microsoft Intune.  

Você pode usar perfis de email para configurar o cliente de email nativo nos seguintes tipos de dispositivo:
-   Windows Phone 8 e posterior
-   Windows 10 Desktop, Windows 10 Mobile e posterior
-   iOS 7.1 e posterior
-   Samsung KNOX padrão (4.0 e posterior)


Além de configurar uma conta de email no dispositivo, você pode ajustar as configurações de sincronização, como quantos emails sincronizar e, dependendo do tipo de dispositivo, os tipos de conteúdo para sincronizar.

## Proteger perfis de email
Você pode proteger os perfis de email usando um destes dois métodos:

### Certificados
Ao criar o perfil de email, você escolhe um perfil de certificado que você criou anteriormente no Intune. Isso é conhecido como certificado de identidade e é usado para autenticar em relação a um perfil de certificado confiável (ou um certificado raiz) para estabelecer que o dispositivo do usuário tem permissão para se conectar. O certificado confiável é implantado no computador que autentica a conexão de email, em geral, o servidor de email nativo.

Para obter mais informações sobre como criar e usar perfis de certificado no Intune, consulte [Secure resource access with certificate profiles](secure-resource-access-with-certificate-profiles.md) (Proteger o acesso a recursos com perfis de certificado).

### Nome de usuário e senha
O usuário se autentica no servidor de email nativo fornecendo seu nome de usuário e senha.

A senha não está contida no perfil do email, portanto o usuário deve fornecê-la ao se conectar ao email.

### Criar um perfil de email

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com), clique em **Política** &gt; **Adicionar Política**.

2.  Configure um dos seguintes tipos de política:

    -   **Perfil de email para Samsung KNOX padrão (4.0 e posterior)**

    -   **Perfil de email (iOS 7.1 e posterior)**

    -   **Perfil de email (Windows Phone 8 e posterior)**

    -   **Perfil de email (Windows 10 Desktop e Mobile e posterior)**

    Você só pode criar e implantar uma política de perfil de email personalizado. Configurações recomendadas não estão disponíveis.

3.  Use a tabela a seguir para ajudá-lo a definir configurações de perfil de email:
    |Nome da configuração|Mais informações|
    |----------------|-----------------------------------------------------------------------------|
    |**Nome**|Nome exclusivo do perfil de email.|
    |**Descrição**|Uma descrição que ajudará a identificar esse perfil.|
    |**Host**|O nome do host do servidor da empresa que hospeda o serviço de email nativo.|
    |**Nome da Conta**|O nome de exibição para a conta de email, como será exibido para os usuários em seus dispositivos.|
    |**Nome de usuário**|Como o nome de usuário da conta de email será obtido. Selecione **Nome de usuário** para um servidor Exchange local ou selecione **Nome UPN** para o Office 365.|
    |**Endereço de email**|Como o endereço de email do usuário em cada dispositivo é gerado. Selecione **Endereço SMTP Primário** para usar o endereço SMTP primário para fazer logon no Exchange ou use **Nome UPN** para usar o nome da entidade completo como o endereço de email.|
    |**Método de autenticação** (Samsung KNOX e iOS)|Selecione **Nome de Usuário e Senha** ou **Certificados** como o método de autenticação usado pelo perfil de email.|
    |**Selecione um certificado de cliente para autenticação de cliente (Certificado de Identidade)** (Samsung KNOX e iOS)|Selecione o certificado do protocolo SCEP cliente que você criou anteriormente e que será usado para autenticar a conexão do Exchange. Para obter mais informações sobre como usar perfis de certificado no Intune, consulte [Secure resource access with certificate profiles](secure-resource-access-with-certificate-profiles.md) (Proteger o acesso a recursos com perfis de certificado).<br /><br />Essa opção é exibida somente quando o método de autenticação é **Certificados**.|
    |**Usar S/MIME** (Samsung KNOX e iOS)|Enviar email de saída usando a criptografia de S/MIME.|
    |**Certificado de autenticação** (Samsung KNOX e iOS)|Selecione o certificado de autenticação que será usado para assinar o email de saída.<br /><br />Esta opção é exibida somente quando você seleciona **Usar S/MIME**.|
    |**Número de dias de email para sincronizar**|O número de dias de email que você deseja sincronizar ou selecione **Ilimitado** para sincronizar todos os emails disponíveis.|
    |**Agenda de sincronização** (Samsung KNOX, Windows Phone 8 e posterior, Windows 10)|Selecione a agenda pela qual os dispositivos sincronizarão os dados do Exchange Server. Você também pode selecionar **Conforme as mensagens chegam**, que sincroniza os dados assim que eles chegam, ou **Manual**, em que o usuário do dispositivo deve iniciar a sincronização.|
    |**Usar SSL**|Use comunicação Secure Sockets Layer (SSL) ao enviar e receber emails, e se comunicar com o Exchange Server.<br /><br />Para dispositivos que executam o Samsung KNOX 4.0 ou posterior, você deve exportar o certificado SSL do Exchange Server e implantá-lo como um Perfil de Certificado Confiável do Android no Intune. O Intune não dá suporte ao acesso a este certificado se ele estiver instalado no Exchange Server por outros meios.|
    |**Tipo de conteúdo para sincronizar**|Selecione os tipos de conteúdo que você deseja sincronizar com dispositivos.| 
    |**Permitir que o email seja enviado de aplicativos de terceiros** (somente iOS)|Permita que aplicativos de terceiros abram emails no aplicativo de email nativo, por exemplo, para anexar arquivos ao email.|

    > [!IMPORTANT] Se você implantou um perfil de email e deseja alterar os valores do **host** ou do **Endereço de email**, deverá excluir o perfil de email existente e criar um novo com os valores necessários.

4.  Quando tiver terminado, clique em **Salvar política**.

A nova política é exibida no nó **Políticas de configuração** do espaço de trabalho **Política** .

## Implantar a política

1.  No espaço de trabalho **Política** , selecione a política que deseja implantar e clique em **Gerenciar Implantação**.

2.  Na caixa de diálogo **Gerenciar implantação** :

    -   **Para implantar a política** - Selecione um ou mais grupos ao qual você deseja implantar a política, clique **Adicionar** &gt; **OK**.

    -   **Para fechar a caixa de diálogo sem implantá-la** - clique em **Cancelar**.

Um resumo de status e alertas na página **Visão geral** do espaço de trabalho **Política** identifica problemas com a política que exigem atenção. Além disso, um resumo de status aparece no espaço de trabalho Painel.

> [!NOTE] Se você quiser remover um perfil de email de um dispositivo, edite a implantação e remova todos os grupos dos quais o dispositivo é membro.




<!--HONumber=Jun16_HO1-->


