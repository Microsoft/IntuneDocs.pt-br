---
title: Acessar o email corporativo com perfis de email | Microsoft Docs
description: "As configurações de perfil de email podem ser usadas para definir configurações de acesso de email para clientes de email específicos em dispositivos móveis."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 10f0cd61-e514-4e44-b13e-aeb85a8e53ae
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 519d3f475e158391b08ab4e51f9410b7bdefcd4c


---

# <a name="configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune"></a>Configurar o acesso a email corporativo usando perfis de email com o Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Muitas plataformas móveis incluem um cliente de email nativo que é fornecido como parte do sistema operacional. Alguns desses clientes podem ser configurados usando perfis de email, conforme descrito neste tópico.

As configurações de perfil de email podem ser usadas para definir configurações de acesso de email para clientes de email específicos em dispositivos móveis. Em plataformas com suporte, os clientes de email nativos podem ser configurados pelo Microsoft Intune para permitir aos usuários acessar o email corporativo em seus dispositivos pessoais, sem qualquer configuração adicional.

Se você precisar tomar medidas adicionais de prevenção de perda de dados, use o [Acesso condicional](restrict-access-to-email-and-o365-services-with-microsoft-intune.md), que controla o acesso à caixa de correio do usuário para qualquer cliente de email, incluindo clientes de email nativos.

Os administradores de TI ou usuários também podem optar por instalar clientes de email alternativos (por exemplo, Microsoft Outlook para Android ou iOS). Esses clientes de email podem não dar suporte a perfis de email e não podem ser configurados usando perfis de email do Intune.  

Você pode usar perfis de email para configurar o cliente de email nativo nos seguintes tipos de dispositivo:
-   Windows Phone 8.1 e posterior
-   Windows 10 (para desktop), Windows 10 Mobile e posterior
-   iOS 8.0 e posterior
-   Samsung KNOX padrão (4.0 e posterior)
-   Android for Work

>[!NOTE]
>O Intune fornece dois perfis de email do Android for Work, um para o aplicativo Gmail e outro para o Nine Work. Esses aplicativos estão disponíveis na loja do Google Play e dão suporte a conexões com o Exchange. Para habilitar a conectividade de email, implante um desses aplicativos de email nos dispositivos dos usuários e crie e implante o perfil apropriado.

Além de configurar uma conta de email no dispositivo, você pode definir quantos emails sincronizar e, dependendo do tipo de dispositivo, os tipos de conteúdo a serem sincronizados.

>[!NOTE]
>
>Se o usuário tiver instalado um perfil de email antes de configurar um perfil pelo Intune, o resultado da implantação do perfil de email do Intune dependerá da plataforma de dispositivo:

>**iOS**: um perfil de email existente e duplicado é detectado com base no nome do host e no endereço de email. O perfil de email duplicado criado pelo usuário bloqueia a implantação de um perfil criado pelo administrador do Intune. Esse é um problema comum, pois usuários do iOS normalmente criam um perfil de email e, depois, se registram. O portal da empresa informa o usuário de que ele não é compatível devido ao seu perfil de email configurado manualmente e solicita que o usuário remova esse perfil. O usuário deve remover seu perfil de email para que o perfil do Intune possa ser configurado. Para evitar o problema, instrua os usuários a se registrarem antes de instalar um perfil de email e permitirem que o Intune configure o perfil.

>**Windows**: um perfil de email existente e duplicado é detectado com base no nome do host e no endereço de email. O Intune substitui o perfil de email existente criado pelo usuário.

>**Samsung KNOX**: um perfil de email existente e duplicado é detectado com base no endereço de email e é substituído pelo perfil do Intune. Se o usuário configurar essa conta, ela será substituída novamente pelo perfil do Intune. Observe que isso pode causar confusão para o usuário.

>Como o Samsung KNOX não usa o nome do host para identificar o perfil, é recomendável que você não crie vários perfis de email para usar com o mesmo endereço de email em hosts diferentes, pois eles substituirão uns aos outros.

>**Android for Work**: o perfil do Intune se aplica somente a aplicativos de email específicos no perfil de trabalho do dispositivo e não afeta a configuração de email no perfil do usuário do dispositivo.


## <a name="secure-email-profiles"></a>Proteger perfis de email
Você pode proteger perfis de email usando um certificado ou uma senha.

### <a name="certificates"></a>Certificados
Ao criar o perfil de email, você escolhe um perfil de certificado que você criou anteriormente no Intune. Ele é conhecido como certificado de identidade e é usado para autenticar em relação a um perfil de certificado confiável (ou um certificado raiz) para estabelecer que o dispositivo do usuário tem permissão para se conectar. O certificado confiável é implantado no computador que autentica a conexão de email, em geral, o servidor de email nativo.

Para obter mais informações sobre como criar e usar perfis de certificado no Intune, consulte [Secure resource access with certificate profiles](secure-resource-access-with-certificate-profiles.md) (Proteger o acesso a recursos com perfis de certificado).

### <a name="user-name-and-password"></a>Nome e senha do usuário
O usuário se autentica no servidor de email nativo fornecendo seu nome de usuário e senha.

A senha não está contida no perfil do email, portanto o usuário deve fornecê-la ao se conectar ao email.

### <a name="create-an-email-profile"></a>Criar um perfil de email

1.  No [console de administração do Microsoft Intune](https://manage.microsoft.com), escolha **Política** &gt; **Adicionar Política**.

2.  Configure um dos seguintes tipos de política:

    -   **Perfil de email para Samsung KNOX Standard (4.0 e posterior)**

    -   **Perfil de email (iOS 8.0 e posterior)**

    -   **Perfil de email (Windows Phone 8.1 e posterior)**

    -   **Perfil de email (Windows 10 Desktop e Mobile e posterior)**

    -   **Perfil de email (Android for Work – Gmail)**

    -   **Perfil de email (Android for Work – Nine Work)**

    Você só pode criar e implantar uma política de perfil de email personalizado. Configurações recomendadas não estão disponíveis.

3.  Use a tabela a seguir para ajudá-lo a definir configurações de perfil de email:

|Nome da configuração | Mais informações|
| ----------- | --------------- |
    |**Nome**|Nome exclusivo do perfil de email.|
    |**Descrição**|Uma descrição que ajuda a identificar esse perfil.|
    |**Host**|O nome do host do servidor da empresa que hospeda o serviço de email nativo.|
    |**Nome da conta**|O nome de exibição para a conta de email, como será exibido para os usuários em seus dispositivos.|
    |**Nome de usuário**|Esse é o atributo no AD (Active Directory) ou no Azure AD, que será usado para gerar o nome de usuário para este perfil de email. Selecione o Endereço SMTP Primário, como *user1@contoso.com*, ou nome UPN, como *user1* ou *user1@contoso.com*.|
    |**Endereço de email**|Como o endereço de email do usuário em cada dispositivo é gerado. Selecione **Endereço SMTP Primário** para usar o endereço SMTP primário para fazer logon no Exchange ou use **Nome UPN** para usar o nome da entidade completo como o endereço de email.|
    |**Método de autenticação** (Android for Work, Samsung KNOX e iOS)|Selecione **Nome de Usuário e Senha** ou **Certificados** como o método de autenticação usado pelo perfil de email.|
    |**Selecione um certificado de cliente para autenticação de cliente (Certificado de Identidade)** (Android for Work, Samsung KNOX e iOS)|Selecione o certificado do protocolo SCEP cliente que você criou anteriormente e que será usado para autenticar a conexão do Exchange. Para obter mais informações sobre como usar perfis de certificado no Intune, consulte [Secure resource access with certificate profiles](secure-resource-access-with-certificate-profiles.md) (Proteger o acesso a recursos com perfis de certificado). Essa opção é exibida somente quando o método de autenticação é **Certificados**.|
    |**Usar S/MIME** (Samsung KNOX e iOS)|Enviar email de saída usando a criptografia de S/MIME.|
    |**Certificado de autenticação** (Samsung KNOX e iOS)|Selecione o certificado de autenticação que será usado para assinar o email de saída. Esta opção é exibida somente quando você seleciona **Usar S/MIME**.|
    |**Número de dias de email para sincronizar**|O número de dias de email que você deseja sincronizar, ou selecione **Ilimitado** para sincronizar todos os emails disponíveis.|
    |**Agenda de sincronização** (Android for Work, Samsung KNOX, Windows Phone 8 e posterior, Windows 10)|Selecione a agenda segundo a qual os dispositivos sincronizarão dados do Exchange Server. Você também pode selecionar **Conforme as mensagens chegam**, que sincroniza os dados assim que eles chegam, ou **Manual**, em que o usuário do dispositivo deve iniciar a sincronização.|
    |**Usar SSL**|Use comunicação SSL (protocolo SSL) ao enviar e receber emails e se comunicar com o Exchange Server. Para dispositivos que executam o Samsung KNOX 4.0 ou posterior, você deve exportar o certificado SSL do Exchange Server e implantá-lo como um Perfil de Certificado Confiável do Android no Intune. O Intune não dará suporte ao acesso a este certificado se ele estiver instalado no Exchange Server por outros meios.|
    |**Tipo de sincronização de conteúdo** (todas as plataformas, exceto Gmail do Android for Work)|Selecione os tipos de conteúdo que você deseja sincronizar com dispositivos.|
    |**Permitir que o email seja enviado de aplicativos de terceiros** (somente iOS)|Permita que o usuário selecione este perfil como a conta padrão para enviar email e permitir que aplicativos de terceiros abram o email no aplicativo de email nativo, por exemplo, para anexar arquivos de email.|

> [!IMPORTANT]
>
> Se você implantou um perfil de email e deseja alterar os valores do **host** ou do **Endereço de Email**, deverá excluir o perfil de email existente e criar um novo com os valores necessários.

4.  Quando tiver terminado, clique em **Salvar política**.

A nova política é exibida no nó **Políticas de configuração** do espaço de trabalho **Política**.

## <a name="deploy-the-policy"></a>Implantar a política

1.  No espaço de trabalho **Política**, selecione a política que deseja implantar e selecione **Gerenciar Implantação**.

2.  Na caixa de diálogo **Gerenciar implantação**:

    -   **Para implantar a política** – Selecione um ou mais grupos aos quais você deseja implantar a política e selecione **Adicionar** &gt; **OK**.

    -   **Para fechar a caixa de diálogo sem implantá-la** - Clique em **Cancelar**.

Um resumo de status e alertas na página **Visão geral** do espaço de trabalho **Política** identifica problemas com a política que exigem atenção. Além disso, um resumo de status aparece no espaço de trabalho Painel.

> [!NOTE]
> - Para o Android for Work, implante também os aplicativos Gmail ou Nine Work além do perfil de email apropriado.
> - Se você quiser remover um perfil de email de um dispositivo, edite a implantação e remova todos os grupos dos quais o dispositivo é membro.



<!--HONumber=Dec16_HO2-->


