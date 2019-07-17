---
title: Configurar VPN por aplicativo para dispositivos iOS no Microsoft Intune – Azure | Microsoft Docs
description: Consulte os pré-requisitos, crie um grupo para os usuários da VPN (rede virtual privada), adicione um perfil de certificado SCEP, configure um perfil de VPN por aplicativo e atribua alguns aplicativos ao perfil de VPN no Microsoft Intune em dispositivos iOS. Também lista as etapas para verificar a conexão VPN no dispositivo.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: D9958CBF-34BF-41C2-A86C-28F832F87C94
ms.reviewer: tycast
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1dc78f8126e0fa9c65fdbe70cfd909da70391e3e
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67884529"
---
# <a name="set-up-per-app-virtual-private-network-vpn-for-ios-devices-in-intune"></a>Configurar VPN (rede virtual privada) por aplicativo para dispositivos iOS no Intune

No Microsoft Intune, você pode criar e usar VPNs (redes virtuais privadas) atribuídas a um aplicativo. Esse recurso é chamado de "VPN por aplicativo". Você escolhe os aplicativos gerenciados que podem usar a VPN em dispositivos gerenciados pelo Intune. Ao usar uma VPN por aplicativo, os usuários finais se conectam automaticamente por meio da VPN e obtêm acesso aos recursos organizacionais, tais como documentos.

Esse recurso aplica-se a:

- iOS 9 e posterior

Verifique a documentação do seu provedor VPN para ver se a sua VPN dá suporte a VPN por aplicativo.

Este artigo mostra como criar um perfil de VPN por aplicativo e atribuir esse perfil a seus aplicativos. Use estas etapas para criar uma experiência VPN por aplicativo contínuo para seus usuários finais. Para a maioria das VPNs que dão suporte a VPN por aplicativo, o usuário abre um aplicativo e conecta-se automaticamente à VPN.

Algumas VPNs permitem autenticação de nome de usuário e senha com a VPN por aplicativo. Ou seja, os usuários precisam inserir um nome de usuário e senha para se conectar à VPN.

## <a name="per-app-vpn-with-zscaler"></a>VPN por aplicativo com o Zscaler

O ZPA (Acesso Privado do Zscaler) integra-se com o Azure AD (Azure Active Directory) para autenticação. Ao usar o ZPA, você não precisa de perfis de [certificado confiável](#create-a-trusted-certificate-profile) ou de [certificado SCEP ou PKCS](#create-a-scep-or-pkcs-certificate-profile) (descritos neste artigo). Se você tem um perfil de VPN por aplicativo configurado para o Zscaler, a abertura de um dos aplicativos associados não conecta automaticamente ao ZPA. Em vez disso, o usuário precisa primeiro entrar no aplicativo Zscaler. Em seguida, o acesso remoto é limitado aos aplicativos associados.

## <a name="prerequisites-for-per-app-vpn"></a>Pré-requisitos para a VPN por aplicativo

> [!IMPORTANT]
> O fornecedor VPN pode ter outros requisitos para VPN por aplicativo, como hardware ou licenciamento específico. Consulte a documentação e cumpra esses pré-requisitos antes de configurar o VPN por aplicativo no Intune.

Para provar sua identidade, o servidor da VPN apresenta o certificado que deve ser aceito sem um aviso pelo dispositivo. Para confirmar a aprovação automática do certificado, crie um perfil de certificado confiável que contenha o certificado raiz do servidor da VPN emitido pela AC (Autoridade de Certificação). 

#### <a name="export-the-certificate-and-add-the-ca"></a>Exportar o certificado e adicionar a AC

1. Abra o console de administração no seu servidor da VPN.
2. Verifique se o servidor da VPN usa a Autenticação Baseada em Certificado. 
3. Exporte o arquivo do certificado raiz confiável. Ele tem uma extensão .cer, e você pode adicioná-lo quando criar um perfil de certificado confiável.
4. Adicione o nome da AC que emitiu o certificado para autenticação no servidor da VPN.

    Se a AC apresentada pelo dispositivo corresponder a uma AC na lista de autoridades de certificação confiáveis no servidor da VPN, o servidor da VPN autenticará o dispositivo com êxito.

## <a name="create-a-group-for-your-vpn-users"></a>Criar um grupo para os usuários da VPN

Crie ou escolha um grupo existente no Azure AD (Azure Active Directory) para os usuários ou dispositivos que usam VPN por aplicativo. Para criar um novo grupo, veja [Adicionar grupos para organizar usuários e dispositivos](groups-add.md).

## <a name="create-a-trusted-certificate-profile"></a>Criar um perfil de certificado confiável

Importe o certificado raiz do servidor da VPN emitido pela AC em um perfil criado no Intune. O perfil de certificado confiável instrui o dispositivo iOS a confiar automaticamente na AC que o servidor da VPN apresenta.

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
3. Insira as seguintes propriedades:
    - **Nome**
    - **Descrição**
    - **Plataforma**: Selecione **iOS**.
    - **Tipo de perfil**: Selecione **Certificado confiável**.
4. Selecione o ícone de pasta e navegue até seu certificado da VPN (arquivo .cer) que você exportou do console de administração da VPN. 
5. Selecione **OK** > **Criar**.

    ![Criar um perfil de certificado confiável para dispositivos iOS no Microsoft Intune](./media/vpn-per-app-create-trusted-cert.png)

## <a name="create-a-scep-or-pkcs-certificate-profile"></a>Criar um perfil de certificado SCEP ou PKCS

O perfil de certificado raiz confiável permite que o dispositivo confie automaticamente no servidor da VPN. O certificado SCEP ou PKCS fornece as credenciais do cliente VPN do iOS para o servidor da VPN. O certificado permite que o dispositivo autentique silenciosamente sem solicitar um nome de usuário e senha. 

Para configurar e atribuir o certificado de autenticação de cliente, veja um dos seguintes artigos:

- [Configurar e gerenciar certificados SCEP com o Intune](certificates-scep-configure.md)
- [Configurar e gerenciar certificados PKCS com o Intune](certficates-pfx-configure.md)

Não deixe de configurar o certificado para autenticação do cliente. Você pode definir isso diretamente em perfis de certificado SCEP (lista de **Uso estendido de chave** > **Autenticação de cliente**). Para PKCS, defina a autenticação de cliente do modelo de certificado na AC (autoridade de certificação).

![Criar um perfil de certificado SCEP no Microsoft Intune, incluindo o nome da entidade, uso de chave, uso estendido de chave e muito mais](./media/vpn-per-app-create-scep-cert.png)

## <a name="create-a-per-app-vpn-profile"></a>Criar um perfil de VPN por aplicativo

O perfil de VPN contém o certificado SCEP ou PKCS que contém as credenciais do cliente, as informações de conexão com a VPN e o sinalizador da VPN por aplicativo para habilitar o uso do recurso de VPN por aplicativo pelo aplicativo iOS.

1. No **Intune**, selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**. 
2. Insira as seguintes propriedades: 
    - **Nome**
    - **Descrição**
    - **Plataforma**: Selecione **iOS**.
    - **Tipo de perfil**: Selecione **VPN**.
3. Em **Tipo de conexão**, selecione seu aplicativo de cliente VPN.
4. Selecione **VPN de base**. As [configurações de VPN do iOS](vpn-settings-ios.md) listam e descrevem todas as configurações. Ao usar a VPN por aplicativo, verifique se você definiu as seguintes propriedades conforme listado: 
    
    - **Método de autenticação**: Selecione **certificados**. 
    - **Certificado de autenticação**: Selecione um certificado SCEP ou PKCS existente > **OK**.      
    - **Túnel dividido**: Selecione **Desabilitar** para forçar todo o tráfego para usar o túnel VPN quando a conexão VPN está ativa. 

      ![Em um perfil de VPN por aplicativo, insira uma conexão, um endereço IP ou FQDN, um método de autenticação e um túnel dividido no Microsoft Intune](./media/vpn-per-app-create-vpn-profile.png)

    Para obter informações sobre as outras configurações, veja [Configurações de VPN do iOS](vpn-settings-ios.md).

5. Selecione **VPN automática** > **Tipo de VPN automática** > **VPN por aplicativo**

    ![No Intune, defina VPN automática para VPN por aplicativo em dispositivos iOS](./media/vpn-per-app-automatic.png)

6. Selecione **OK** > **OK** > **Criar**.

## <a name="associate-an-app-with-the-vpn-profile"></a>Associar um aplicativo ao perfil da VPN

Depois de adicionar o perfil da VPN, associe o aplicativo e o grupo do Microsoft Azure AD ao perfil.

1. No **Intune**, selecione **Aplicativos cliente** > **Aplicativos**.
2. Selecione um aplicativo na lista > **Atribuições** > **Adicionar grupo**.
3. Em **Tipo de atribuição**, selecione **Necessário** ou **Disponível para dispositivos registrados**.
4. Selecione **Grupos incluídos** >  **Selecionar grupos a incluir** > Selecione o grupo que [você criou](#create-a-group-for-your-vpn-users) (neste artigo) > **Selecionar**.
5. Em **VPNs**, selecione o perfil de VPN por aplicativo que [você criou](#create-a-per-app-vpn-profile) (neste artigo).

    ![Atribuir um aplicativo ao perfil de VPN por aplicativo no Microsoft Intune](./media/vpn-per-app-app-to-vpn.png)

6. Selecione **OK** > **Salvar**.

Uma associação entre um aplicativo e um perfil é removida durante o próximo check-in do dispositivo, quando todas as seguintes condições existem:

- O aplicativo foi direcionado com a intenção de instalação obrigatória.
- Tanto o perfil quanto o aplicativo são direcionados para o mesmo grupo.
- Você remove a configuração VPN por aplicativo da atribuição do aplicativo.

Uma associação entre um aplicativo e um perfil persistirá até que o usuário final solicite uma reinstalação do Portal da Empresa, quando as seguintes condições existirem:

- O aplicativo foi direcionado com a intenção de instalação disponível.
- Tanto o perfil quanto o aplicativo são direcionados para o mesmo grupo.
- O usuário final solicitou a instalação do aplicativo no Portal da Empresa, o que resulta na instalação do aplicativo e do perfil no dispositivo.
- Você remover ou alterar a configuração de VPN por aplicativo da atribuição de aplicativo.

## <a name="verify-the-connection-on-the-ios-device"></a>Verifique a conexão no dispositivo iOS

Com a VPN por aplicativo configurada e associada ao seu aplicativo, verifique se a conexão funciona a partir de um dispositivo.

### <a name="before-you-attempt-to-connect"></a>Antes de tentar se conectar

- Verifique se você implantou todas as políticas mencionadas acima no mesmo grupo. Caso contrário, a experiência de VPN por aplicativo não funcionará.
- Se você estiver usando o aplicativo de VPN da Pulse Secure ou um aplicativo cliente personalizado, haverá a opção de usar o túnel de camada de pacote ou de camada de aplicativo. Defina o valor de **ProviderType** como **app-proxy** para o túnel de camada de aplicativo ou como **packet-tunnel** para o túnel de camada de pacote. Verifique a documentação do seu provedor de VPN para verificar se você está usando o valor correto.

### <a name="connect-using-the-per-app-vpn"></a>Conectar-se usando a VPN por aplicativo

Confira a experiência de toque zero ao se conectar sem a necessidade de selecionar a VPN ou digitar suas credenciais. A experiência de toque zero significa que:

- O dispositivo não pede para você confiar no servidor da VPN. Ou seja, o usuário não vê a caixa de diálogo **Confiança Dinâmica**.
- O usuário não precisa digitar credenciais.
- O dispositivo do usuário é conectado à VPN quando o usuário abre um dos aplicativos associados.

<!-- ## Troubleshooting the per-app VPN

The user experiences the feature by silently connecting to the VPN. This experience, however, can provide little information for troubleshooting. You can review the event logs crated by the iOS device.

`Note -- use the Apple Configurator as the supported tool. Only runs on a mac.'

To review event logs:

1. Connect your iOS device to a PC
2. Open the **iPhone Configuration Utility** (IPCU). If you do not have a copy, you can install it from [CompatCenter](http://www.microsoft.com/en-us/windows/compatibility/CompatCenter/ProductDetailsViewer?Name=iPhone%20Configuration%20Utility&vendor=Apple&Locale=1033%2C2057%2C3081%2C4105%2C16393&ModelOrVersion=3&BreadCrumbPath=iphone%20configuration%20utility&LastSearchTerm=iphone%2Bconfiguration%2Butility&Type=Software&tempOsid=Windows%208.1)
3. Review the logs. -->

## <a name="next-steps"></a>Próximas etapas

- Para examinar as configurações do iOS, consulte [Configurações de VPN para dispositivos iOS no Microsoft Intune](vpn-settings-ios.md).
- Para saber mais sobre a configuração da VPN e do Intune, veja [definir configurações de VPN no Microsoft Intune](vpn-settings-configure.md).
