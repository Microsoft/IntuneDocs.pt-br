---
title: Registrar dispositivos Android Enterprise dedicados ou dispositivos totalmente gerenciados no Intune
titleSuffix: Microsoft Intune
description: Saiba como registrar dispositivos Android Enterprise dedicados ou dispositivos totalmente gerenciados no Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/15/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4012dc4046eccf836c73e15409dae182eaf12231
ms.sourcegitcommit: c19584b36448bbd4c8638d7cab552fe9b3eb3408
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "71163265"
---
# <a name="enroll-your-android-enterprise-dedicated-devices-or-fully-managed-devices"></a>Registrar dispositivos Android Enterprise dedicados ou dispositivos totalmente gerenciados

Após configurar seus [dispositivos Android Enterprise dedicados](android-kiosk-enroll.md) ou [dispositivos totalmente gerenciados](android-fully-managed-enroll.md) no Intune, será possível registrá-los. A maneira como você registra seus dispositivos Android Enterprise depende do sistema operacional.

| Método de registro | Versão mínima do sistema operacional Android para dispositivos dedicados e totalmente gerenciados |
| ----- | ----- |
| Comunicação a curta distância | 5.1 |
| Entrada de token | 6.0 |
| Código QR | 7.0 |
| Zero Touch  | 8.0\* |

\* em fabricantes participantes.

## <a name="enroll-by-using-near-field-communication-nfc"></a>Registrar usando NFC (comunicação a curta distância)

Para dispositivos compatíveis com NFC, você pode provisionar os dispositivos criando uma marca de NFC especialmente formatada. Você pode usar seu próprio aplicativo ou qualquer ferramenta de criação de marca de NFC. Para obter mais informações, veja [Registro de dispositivo Android Enterprise com base em C com o Microsoft Intune](https://blogs.technet.microsoft.com/cbernier/2018/10/15/nfc-based-android-enterprise-device-enrollment-with-microsoft-intune/) e [Documentação da API de gerenciamento do Android da Google](https://developers.google.com/android/management/provision-device#nfc_method).

## <a name="enroll-by-using-a-token"></a>Registrar usando um token

Para dispositivos Android 6 e posteriores, você pode usar o token para registrar o dispositivo. O Android 6.1 e versões posteriores também podem aproveitar a verificação de código QR ao usar o método de registro **afw#setup**.

1. Ligue o dispositivo apagado.
2. Na tela **Boas-vindas**, selecione seu idioma.
3. Conecte-se ao **Wi-Fi** e, em seguida, escolha **AVANÇAR**.
4. Aceite os termos e condições do Google e, em seguida, escolha **AVANÇAR**.
5. Na tela de entrada do Google, digite **afw#setup** em vez de uma conta do Gmail e, em seguida, selecione **AVANÇAR**.
6. Escolha **INSTALAR** para o aplicativo **Política do Dispositivo Android**.
7. Continue a instalação dessa política.  Alguns dispositivos podem exigir a aceitação de termos adicionais.
8. Na tela **Registrar este dispositivo**, permita que o dispositivo verifique o código QR ou escolha inserir o token manualmente.
9. Siga as instruções na tela para concluir o registro.

## <a name="enroll-by-using-a-qr-code"></a>Registrar usando um código QR

Nos dispositivos Android 7 e posteriores, você pode examinar o código QR do perfil de registro para registrar o dispositivo.

> [!Note]
> O zoom do navegador pode fazer com que os dispositivos não consigam digitalizar o código QR. Aumentar o zoom do navegador resolve o problema.

1. Para iniciar uma leitura de QR no dispositivo Android, toque várias vezes na primeira tela que é exibida após um apagamento.
2. Para dispositivos Android 7 e 8, será solicitado que você instale um leitor de QR. Os dispositivos Android 9 e versões posteriores já têm um leitor de QR instalado.
3. Use o leitor de QR para examinar o código QR do perfil de registro e, em seguida, siga as instruções na tela para registrar.

## <a name="enroll-by-using-google-zero-touch"></a>Registrar usando o Google Zero Touch

Para usar o sistema Zero Touch do Google, o dispositivo precisa ser compatível com ele e ser afiliado a um fornecedor que faça parte do serviço.  Para obter mais informações, confira o [site do programa Zero Touch do Google](https://www.android.com/enterprise/management/zero-touch/).

1. Crie uma nova configuração no console do Zero Touch.
2. Escolha **Microsoft Intune** na lista suspensa DPC de EMM.
3. No console do Zero Touch do Google, copie/cole o JSON a seguir no campo DPC extra. Substitua a cadeia de caracteres *YourEnrollmentToken* pelo token de registro criado como parte do perfil de registro. Coloque o token de registro entre aspas duplas.

    ```json
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


## <a name="next-steps"></a>Próximas etapas
- [Implantar aplicativos Android](apps-deploy.md)
- [Adicionar políticas de configuração do Android](device-profiles.md)

