---
title: Registrar dispositivos de quiosque Android Enterprise no Intune
titlesuffix: Microsoft Intune
description: Saiba como registrar dispositivos de quiosque Android Enterprise no Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 6/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: 637fe2d2c764cf78e67e728bfa77567cf12e88ce
ms.sourcegitcommit: fff179f59bd542677cbd4bf3bacc24bb880e2cb6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/07/2018
ms.locfileid: "53031986"
---
# <a name="set-up-intune-enrollment-of-android-enterprise-kiosk-devices"></a>Configurar o registro no Intune de dispositivos de quiosque Android Enterprise

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

O Android dá suporte a dispositivos no estilo quiosque com seu conjunto de soluções de uso único de propriedade corporativa. Esses dispositivos são usados para uma finalidade única, como sinalização digital, impressão de tíquete ou gerenciamento de inventário, para mencionar apenas alguns. Os administradores bloqueiam o uso de um dispositivo a um conjunto limitado de aplicativos e links da Web. Isso também impede que os usuários adicionem outros aplicativos ou executem outras ações no dispositivo.

O Intune ajuda você a implantar aplicativos e configurações em dispositivos de quiosque Android. Para obter detalhes específicos sobre o Android Enterprise, confira [Requisitos do Android Enterprise](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

Os dispositivos que você gerencia dessa maneira são registrados no Intune sem uma conta de usuário e não são associados a nenhum usuário final. Eles não estão destinados a aplicativos de uso pessoal nem a aplicativos que têm um requisito rigoroso em relação a dados de conta específicos do usuário, como o Outlook ou o Gmail.

## <a name="device-requirements"></a>Requisitos do dispositivo

Os dispositivos precisam atender a esses requisitos para serem gerenciados como um dispositivo de quiosque Android Enterprise:

- Sistema operacional Android versão 5.1 e posterior.
- Os dispositivos precisam executar uma distribuição do Android que tem conectividade com GMS (Google Mobile Services). Os dispositivos precisam ter o GMS disponível e conseguir se conectar a ele.

## <a name="set-up-android-kiosk-management"></a>Configurar o gerenciamento de quiosque do Android

Para configurar o gerenciamento de quiosque do Android, siga estas etapas:

1. Para preparar-se para gerenciar dispositivos móveis, você precisa [definir a autoridade de MDM (gerenciamento de dispositivo móvel) para o **Microsoft Intune**](mdm-authority-set.md) para obter instruções. Você define esse item apenas uma vez, na primeira vez que configura o Intune para o gerenciamento de dispositivo móvel.
2. [Conecte sua conta de locatário do Intune à sua conta do Android Enterprise](connect-intune-android-enterprise.md).
3. [Crie um perfil de registro.](#create-an-enrollment-profile)
4. [Crie um grupo de dispositivos](#create-a-device-group).
5. [Registre os dispositivos de quiosque](#enroll-the-kiosk-devices).

### <a name="create-an-enrollment-profile"></a>Criar um perfil de registro

Você precisa criar um perfil de registro para que seja possível registrar os dispositivos de quiosque. Quando o perfil é criado, ele fornece um token de registro (uma cadeia de caracteres aleatória) e um código QR. Dependendo do sistema operacional Android e da versão do dispositivo, é possível usar o token ou o código QR para [registrar o dispositivo de quiosque](#enroll-the-kiosk-devices).

1. Acesse o [Portal do Intune](https://portal.azure.com) e escolha **Registro do dispositivo** > **Registro do Android** > **Registros de dispositivo de quiosque e de tarefa**.
2. Escolha **Criar** e preencha os campos obrigatórios.
    - **Nome**: digite um nome que você usará ao atribuir o perfil ao grupo de dispositivos dinâmicos.
    - **Data de vencimento do token**: a data em que o token expira. O Google impõe o máximo de 90 dias.
3. Escolha **Criar** para salvar o perfil.

### <a name="create-a-device-group"></a>Criar um grupo de dispositivos

Você pode direcionar aplicativos e políticas a grupos de dispositivos atribuídos ou dinâmicos. Você pode configurar grupos de dispositivos dinâmicos do AAD para popular automaticamente os dispositivos registrados com um perfil de registro específico, seguindo estas etapas:

1. Acesse o [Portal do Intune](https://portal.azure.com) e escolha **Grupos** > **Todos os grupos** > **Novo grupo**.
2. Na folha **Grupo**, preencha os campos obrigatórios da seguinte forma:
    - **Tipo de grupo**: Segurança 
    - **Nome do grupo**: digite um nome intuitivo (como, dispositivos Fábrica 1)
    - **Tipo de associação**: dispositivo dinâmico
3. Escolha **Adicionar consulta dinâmica**.
4. Na folha **Regras de associação dinâmica**, preencha os campos da seguinte maneira:
    - **Adicionar regra de associação dinâmica**: regra simples
    - **Adicionar dispositivos em que**: enrollmentProfileName
    - Na caixa do meio, escolha **Corresponder**.
    - No último campo, insira o nome do perfil de registro que você criou anteriormente.
    Para obter mais informações sobre regras de associação dinâmica, consulte [Regras de associação dinâmica para grupos no AAD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership). 
5. Escolha **Adicionar consulta** > **Criar**.

### <a name="replace-or-remove-tokens"></a>Substituir ou remover os tokens

Você pode substituir ou remover tokens e os códigos QR.

- **Substituir token**: você pode gerar um novo código QR/token quando um deles se aproximar da expiração usando Substituir token.
- **Revogar token**: você pode expirar imediatamente o código QR/token. Desse ponto em diante, o código QR/token não é mais utilizável. Use essa opção quando você:
    - compartilhar acidentalmente o código QR/token com uma entidade não autorizada
    - concluir todos os registros e não precisar mais do token/QR código

A substituição ou a revogação de um código QR/token não terá nenhum efeito em dispositivos que já estejam registrados.

1. Acesse o [Portal do Intune](https://portal.azure.com) e escolha **Registro do dispositivo** > **Registro do Android** > **Registros de dispositivo de quiosque e de tarefa**.
2. Escolha o perfil com o qual deseja trabalhar.
3. Escolha **Token**.
4. Para substituir o token, escolha **Substituir token**.
5. Para revogar o token, escolha **Revogar token**.

## <a name="enroll-the-kiosk-devices"></a>Registrar dispositivos de quiosque

Depois de criar o perfil de registro e o grupo de dispositivos dinâmicos, você poderá registrar seus dispositivos de quiosque. A maneira de registrar seus dispositivos Android depende do sistema operacional.

| Método de registro | Versão mínima do sistema operacional Android com suporte |
| ----- | ----- |
| Comunicação a curta distância | 5.1 |
| Entrada de token | 6.0 |
| Código QR | 7.0 |
| Zero Touch | 8.0, em fabricantes participantes |

### <a name="enroll-by-using-near-field-communication-nfc"></a>Registrar usando NFC (comunicação a curta distância)

Para dispositivos Android 5.1 e posteriores compatíveis com NFC, você pode provisionar os dispositivos criando uma marca de NFC especialmente formatada. Você pode usar seu próprio aplicativo ou qualquer ferramenta de criação de marca de NFC. Para obter mais informações, confira a [documentação da API de gerenciamento do Android do Google](https://developers.google.com/android/management/provision-device#nfc_method).

### <a name="enroll-by-using-a-token"></a>Registrar usando um token

Para dispositivos Android 6 e posteriores, você pode usar o token para registrar o dispositivo. O Android 6.1 e versões posteriores também podem aproveitar a verificação de Código QR ao usar o método de registro **aft#setup**.

1. Ligue o dispositivo apagado.
2. Na tela **Boas-vindas**, selecione seu idioma.
3. Conecte-se ao **Wi-Fi** e, em seguida, escolha **AVANÇAR**.
4. Aceite os termos e condições do Google e, em seguida, escolha **AVANÇAR**.
5. Na tela de entrada do Google, digite **afw#setup** em vez de uma conta do Gmail e, em seguida, selecione **AVANÇAR**.
6. Escolha **INSTALAR** para o aplicativo **Política do Dispositivo Android**.
7. Continue a instalação dessa política.  Alguns dispositivos podem exigir a aceitação de termos adicionais. 
8. Na tela **Registrar este dispositivo**, permita que o dispositivo verifique o código QR ou escolha inserir o token manualmente.
9. Siga as instruções na tela para concluir o registro. 

### <a name="enroll-by-using-a-qr-code"></a>Registrar usando um código QR

Nos dispositivos Android 7 e posteriores, você pode examinar o código QR do perfil de registro para registrar o dispositivo.

> [!Note]
> O zoom do navegador pode fazer com que os dispositivos não consigam digitalizar o código QR. Aumentar o zoom do navegador resolve o problema.

1. Para iniciar uma leitura de QR no dispositivo Android, toque várias vezes na primeira tela que é exibida após um apagamento.
2. Para dispositivos Android 7 e 8, será solicitado que você instale um leitor de QR. Os dispositivos Android 9 e versões posteriores já têm um leitor de QR instalado.
3. Use o leitor de QR para examinar o código QR do perfil de registro e, em seguida, siga as instruções na tela para registrar.

### <a name="enroll-by-using-google-zero-touch"></a>Registrar usando o Google Zero Touch

Para usar o sistema Zero Touch do Google, o dispositivo precisa ser compatível com ele e ser afiliado a um fornecedor que faça parte do serviço.  Para obter mais informações, confira o [site do programa Zero Touch do Google](https://www.android.com/enterprise/management/zero-touch/). 


1. Crie uma nova configuração no console do Zero Touch.
2. Escolha **Microsoft Intune** na lista suspensa DPC de EMM.
3. No console do Zero Touch do Google, copie/cole o JSON a seguir no campo DPC extra. Substitua a cadeia de caracteres *YourEnrollmentToken* pelo token de registro criado como parte do perfil de registro. Coloque o token de registro entre aspas duplas.

```
{ 
    "android.app.extra.PROVISIONING_DEVICE_ADMIN_COMPONENT_NAME": "com.google.android.apps.work.clouddpc/.receivers.CloudDeviceAdminReceiver", 

    "android.app.extra.PROVISIONING_DEVICE_ADMIN_SIGNATURE_CHECKSUM": "I5YvS0O5hXY46mb01BlRjq4oJJGs2kuUcHvVkAPEXlg", 

    "android.app.extra.PROVISIONING_DEVICE_ADMIN_PACKAGE_DOWNLOAD_LOCATION": "https://play.google.com/managed/downloadManagingApp?identifier=setup", 

    "android.app.extra.PROVISIONING_ADMIN_EXTRAS_BUNDLE": { 
        "com.google.android.apps.work.clouddpc.EXTRA_ENROLLMENT_TOKEN": "YourEnrollmentToken" 
    } 
} 
```
4. Escolha **Aplicar**.

## <a name="managing-apps-on-android-kiosk-devices"></a>Gerenciando aplicativos em dispositivos de quiosque Android

Somente os aplicativos que têm o tipo de atribuição [definido como Obrigatório](apps-deploy.md#to-assign-an-app) podem ser instalados em dispositivos de quiosque Android. Os aplicativos são instalados da Google Play Store gerenciada da mesma maneira que os dispositivos de perfil de trabalho Android.

Os aplicativos são atualizados automaticamente nos dispositivos gerenciados quando o desenvolvedor do aplicativo publica uma atualização no Google Play.

Para remover um aplicativo de dispositivos de quiosque Android, você pode fazer o seguinte:
-   Excluir a implantação do aplicativo necessário.
-   Criar uma implantação de desinstalação para o aplicativo.


## <a name="next-steps"></a>Próximas etapas
- [Implantar aplicativos de quiosque Android](apps-deploy.md)
- [Adicionar políticas de configuração de quiosque Android](device-profiles.md)
