---
title: Configurar VPN por aplicativo para dispositivos iOS no Microsoft Intune – Azure | Microsoft Docs
description: Consulte os pré-requisitos, crie um grupo para os usuários da VPN (rede virtual privada), adicione um perfil de certificado SCEP, configure um perfil de VPN por aplicativo e atribua alguns aplicativos ao perfil de VPN no Microsoft Intune em dispositivos iOS. Também lista as etapas para verificar a conexão VPN no dispositivo.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: D9958CBF-34BF-41C2-A86C-28F832F87C94
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7cf005b225dd11ca6b95dbed0a82330544575f92
ms.sourcegitcommit: 2d1e89fa5fa721e79648e41fde147a035e7b047d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/31/2018
ms.locfileid: "43347467"
---
# <a name="set-up-per-app-virtual-private-network-vpn-in-intune-for-ios-devices"></a>Configurar VPN (rede virtual privada) por aplicativo no Intune para dispositivos iOS

Você pode especificar quais aplicativos gerenciados poderão usar a VPN (rede virtual privada) em dispositivos iOS gerenciados pelo Intune. Ao criar uma VPN por aplicativo no Intune, um usuário final se conecta automaticamente por meio da sua VPN no momento em que acessa os documentos corporativos.

A VPN por aplicativo está disponível para os seguintes provedores:

 - VPN de acesso remoto de ponto de verificação
 - Cisco AnyConnect
 - Citrix
 - F5
 - Pulse Connect Secure
 - SonicWall
 - Palo Alto Networks GlobalProtect
 - Zscaler

## <a name="prerequisites-for-per-app-vpn"></a>Pré-requisitos para a VPN por aplicativo

> [!IMPORTANT]
> O fornecedor VPN pode ter outros requisitos específicos para VPN por aplicativo, como hardware ou licenciamento específico. Consulte a documentação e cumpra esses pré-requisitos antes de configurar o VPN por aplicativo no Intune.

Para provar sua identidade, o servidor da VPN apresenta o certificado que deve ser aceito sem um aviso pelo dispositivo. Para garantir a aprovação automática do certificado, crie um perfil de certificado confiável que contenha o certificado raiz do servidor da VPN emitido pela AC (autoridade de certificação). 

Exportar o certificado e adicionar a AC.

1. Abra o console de administração no seu servidor da VPN.
2. Verifique se o servidor da VPN usa a Autenticação Baseada em Certificado. 
3. Exporte o arquivo do certificado raiz confiável. Ele tem uma extensão .cer, e você pode adicioná-lo quando criar um perfil de certificado confiável.
4. Adicione o nome da AC que emitiu o certificado para autenticação no servidor da VPN.
    Se a AC apresentada pelo dispositivo coincidir com uma das ACs na lista de autoridades de certificação confiáveis no servidor da VPN, o servidor da VPN autenticará o dispositivo com êxito.

## <a name="create-a-group-for-your-vpn-users"></a>Criar um grupo para os usuários da VPN

Crie ou escolha um grupo existente no Azure AD (Azure Active Directory) para conter os membros que têm acesso à VPN por aplicativo.

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
2. Escolha **Grupos** e clique em **Novo grupo**.
3. Selecione um **Tipo de grupo** para o grupo. 
3. Digite o **Nome do grupo** para o grupo. 
4. Digite a **Descrição do grupo** para o grupo. 
5. Selecione **Atribuído** para o **Tipo de associação**.
7. Pesquise os usuários da VPN por nome ou endereço de email no painel **Membros**.
8. Selecione cada usuário e clique em **Selecionar**.
9. Clique em **Criar**

## <a name="create-a-trusted-certificate-profile"></a>Criar um perfil de certificado confiável

Importe o certificado raiz do servidor da VPN emitido pela AC em um perfil criado no Intune. O perfil de certificado confiável instrui o dispositivo iOS a confiar automaticamente na AC que o servidor da VPN apresenta.

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
2. Escolha **Configuração do dispositivo** e, em seguida, clique em **Perfis**.
3. Clique em **Criar perfil**. Em **Criar perfil**:
    1. Digite o **Nome**.
    2. Digite a **Descrição**.
    3. Selecione **iOS** para a **Plataforma**.
    4. Selecione **Certificado confiável** para o **Tipo de perfil**.
4. Clique no ícone de pasta e navegue até seu certificado da VPN (arquivo .cer) que você exportou do console de administração da VPN. Clique em **OK**.
5. Clique em **Criar**.

    ![Criar um perfil de certificado confiável](./media/vpn-per-app-create-trusted-cert.png)

## <a name="create-a-scep-certificate-profile"></a>Criar um perfil de certificado SCEP

O perfil de certificado raiz confiável permite que o iOS confie automaticamente no servidor da VPN. O certificado SCEP fornece as credenciais do cliente VPN do iOS para o servidor da VPN. O certificado permite que o dispositivo autentique silenciosamente sem solicitar um nome de usuário e senha ao usuário do dispositivo iOS. 

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
2. Escolha **Configuração do dispositivo** e, em seguida, clique em **Perfis**.
3. Clique em **Criar perfil**. Em **Criar perfil**:
    1. Digite o **Nome**.
    2. Digite a **Descrição**.
    3. Selecione **iOS** para a **Plataforma**.
    4. Selecione **Certificado SCEP** para o **Tipo de perfil**.
4. Selecione **Anos** e digite `2` para o **Período de validade do certificado**.
5. Selecione **Nome comum** para o **Formato de nome da entidade**.
6. Selecione **UPN (nome principal de usuário)** para o **Nome alternativo da entidade**.
7. Selecione **Assinatura digital** e **Codificação de chave** para **Uso da chave**.
8. Selecione **2048** para **Tamanho da chave (bits)**.
9. Clique no certificado raiz e selecione um certificado SCEP. Clique em **OK**.
10. Digite `Client Authentication` em **Nome** para **Uso estendido de chave**.
11. Digite `1.3.6.1.5.5.7.3.2` no **Identificador de objeto**.
12. Clique em **Adicionar**.
13. Digite ***URL do servidor*** e clique em **Adicionar**.
14. Clique em **OK**.
15. Clique em **Criar**.

    ![Criar um perfil de certificado SCEP](./media/vpn-per-app-create-scep-cert.png)

## <a name="create-a-per-app-vpn-profile"></a>Criar um perfil de VPN por aplicativo

O perfil de VPN contém o certificado SCEP que leva as credenciais do cliente, as informações de conexão com a VPN e o sinalizador da VPN por Aplicativo para habilitar o recurso VPN por Aplicativo para uso pelo aplicativo iOS.

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
2. Escolha **Configuração do dispositivo** e, em seguida, clique em **Perfis**.
3. Clique em **Criar perfil**. Em **Criar perfil**:
    1. Digite o **Nome**.
    2. Digite a **Descrição**.
    3. Selecione **iOS** para a **Plataforma**.
    4. Selecione **VPN** para o **Tipo de perfil**.
4. Selecione **VPN de base**. Em **VPN de base**:
    1. Digite o **Nome da conexão**.
    2. Digite o **Endereço IP ou o FQDN**.
    3. Selecione **Certificados** para o **Método de autenticação**.
    4. Selecione o certificado SCEP em **Certificado de autenticação** e clique em **OK**.
    5. Selecione sua VPN para o **Tipo de conexão**.
    6. Se necessário, configure os atributos da sua VPN.
    7. Selecione para **Desabilitar o túnel dividido**.
5. Clique em **VPN automática**. Em **VPN automática**:
    1. Selecione **VPN por aplicativo** para o **Tipo de VPN automática**.
    2. Digite a URL para a VPN e clique em **Adicionar**.
    3. Clique em **OK**.
6. Clique em **OK**.
7. Clique em **Criar**.

    ![Criar um perfil de VPN por aplicativo](./media/vpn-per-app-create-vpn-profile.png)


## <a name="associate-an-app-with-the-vpn-profile"></a>Associar um aplicativo ao perfil da VPN

Depois de adicionar o perfil da VPN, associe o aplicativo e o grupo do Microsoft Azure AD ao perfil.

1. Entre no [portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
3. Escolha **Aplicativos clientes**.
4. Clique em **Aplicativos**.
5. Selecione o aplicativo na lista de aplicativos.
6. Clique em **Atribuições**.
7. Clique em **Adicionar grupo**.
8. Selecione **necessário** para o **tipo de atribuição** no painel **Adicionar grupo**.
9. Selecione o grupo que você definiu anteriormente e marque para **Tornar este aplicativo necessário**.
10. Selecione sua definição de VPN para a **VPN**.
 
    > [!NOTE]  
    > Às vezes, leva até um minuto para que a definição da VPN recupere o valor. Aguarde de três a cinco minutos antes de clicar em **Salvar**.

11. Clique em **OK** e em **Salvar**.

    ![Associar um aplicativo à VPN](./media/vpn-per-app-app-to-vpn.png)

Uma associação entre um aplicativo e um perfil será removida durante o próximo check-in do dispositivo, quando as seguintes condições existirem:
- O aplicativo foi direcionado com a intenção de instalação obrigatória.
- Tanto o perfil quanto o aplicativo são direcionados para o mesmo grupo.
- Você remove a configuração VPN por aplicativo da atribuição do aplicativo.

Uma associação entre um aplicativo e um perfil ainda existirá até que o usuário final solicite uma reinstalação do portal da empresa, quando as seguintes condições existirem:
- O aplicativo foi direcionado com a intenção de instalação disponível.
- Tanto o perfil quanto o aplicativo são direcionados para o mesmo grupo.
- O usuário final solicitou a instalação do aplicativo no portal da empresa, o que resulta na instalação do aplicativo e do perfil no dispositivo.
- Você remove a configuração VPN por aplicativo da atribuição do aplicativo.

## <a name="verify-the-connection-on-the-ios-device"></a>Verifique a conexão no dispositivo iOS

Com a VPN por aplicativo configurada e associada ao seu aplicativo, verifique se a conexão funciona a partir de um dispositivo.

### <a name="before-you-attempt-to-connect"></a>Antes de tentar se conectar

 - Você deve estar executando iOS 9 ou posterior.
 - Verifique se você implantou *todas* as políticas mencionadas acima no mesmo grupo de usuários. Caso contrário, a experiência da VPN por aplicativo será drasticamente interrompida.  
 - Verifique se você tem o aplicativo de VPN de terceiros compatível instalado. Os seguintes aplicativos de VPN são compatíveis:
    - Conexão de cápsula do ponto de verificação
    - Cisco AnyConnect
    - VPN Citrix
    - Acesso por F5
    - Pulse Secure
    - SonicWall Mobile Connect
    - Aplicativo Zscaler

    > [!NOTE]
    > Se você estiver usando o aplicativo de VPN da Pulse Secure, haverá a opção de usar o túnel de camada de pacote ou de camada de aplicativo. Defina o valor de **ProviderType** como **app-proxy** para o túnel de camada de aplicativo ou como **packet-tunnel** para o túnel de camada de pacote.

### <a name="connect-using-the-per-app-vpn"></a>Conectar-se usando a VPN por aplicativo

Confira a experiência de toque zero ao se conectar sem a necessidade de selecionar a VPN ou digitar suas credenciais. A experiência de toque zero significa que:

 - O dispositivo não pede para você confiar no servidor da VPN. Ou seja, você vê a caixa de diálogo **Confiança dinâmica**.
 - Você não precisa digitar as credenciais.
 - Você é conectado à VPN depois de tocar no botão de conexão.

Verificar a conexão em um dispositivo iOS.

1. Toque no aplicativo da VPN.
2. Toque em **Conectar**.  
A VPN se conecta com êxito, sem avisos adicionais.

<!-- ## Troubleshooting the per-app VPN

The user experiences the feature by silently connecting to the VPN. This experience, however, can provide little information for troubleshooting. You can review the event logs crated by the iOS device.

`Note -- use the Apple Configurator as the supported tool. Only runs on a mac.'

To review event logs:

1. Connect your iOS device to a PC
2. Open the **iPhone Configuration Utility** (IPCU). If you do not have a copy, you can install it from [CompatCenter](http://www.microsoft.com/en-us/windows/compatibility/CompatCenter/ProductDetailsViewer?Name=iPhone%20Configuration%20Utility&vendor=Apple&Locale=1033%2C2057%2C3081%2C4105%2C16393&ModelOrVersion=3&BreadCrumbPath=iphone%20configuration%20utility&LastSearchTerm=iphone%2Bconfiguration%2Butility&Type=Software&tempOsid=Windows%208.1)
3. Review the logs. -->

## <a name="next-steps"></a>Próximas etapas

- Para examinar as configurações do iOS, consulte [Configurações de VPN para dispositivos iOS no Microsoft Intune](vpn-settings-ios.md).
-  Para saber mais sobre a configuração da VPN e do Intune, consulte [Como definir configurações de VPN no Microsoft Intune](vpn-settings-configure.md).
