---
title: Definir as configurações de Wi-Fi do Microsoft Intune para dispositivos que executam o Android
titleSuffix: ''
description: Conheça as definições de configuração de Wi-Fi do Intune em dispositivos que executam o Android e Android for Work.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ee82da997a794bb2f65929a6fd9e0de0cc776a6e
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31831054"
---
# <a name="configure-wi-fi-settings-in-microsoft-intune-for-devices-running-android-and-android-for-work"></a>Definir as configurações de Wi-Fi no Microsoft Intune para dispositivos que executam o Android e o Android for Work  

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Este artigo mostra as configurações de Wi-Fi que você pode definir no Microsoft Intune para dispositivos que executam Android e Android for Work.

## <a name="wi-fi-settings-for-basic-and-enterprise-profiles"></a>Configurações Wi-Fi para perfis básico e empresarial

As seguintes configurações de Wi-Fi estão disponíveis para dispositivos Android e Android for Work:

- **Nome da rede** – Insira um nome para esta conexão Wi-Fi. Esse é o nome que os usuários verão ao navegarem pela lista de conexões disponíveis no dispositivo.
- **SSID** – Abreviação de identificador de conjunto de serviço (service set identifier em inglês). Esse é o nome real da rede sem fio à qual os dispositivos se conectam. No entanto, os usuários veem apenas o nome de rede configurado ao escolher a conexão.
- **Conectar-se automaticamente** – Faz com que o dispositivo se conecte sempre que estiver no intervalo da rede.
- **Rede oculta** – Impede que essa rede seja exibida na lista de redes disponíveis no dispositivo.


## <a name="wi-fi-settings-for-enterprise-profiles-only"></a>Configurações Wi-Fi para apenas para perfis empresariais

- **Tipo de EAP** – Escolha o tipo de Protocolo EAP (Extensible Authentication Protocol) usado para autenticar as conexões sem fio seguras:
    - **EAP-TLS**
    - **EAP-TTLS**
    - **PEAP**

### <a name="further-options-when-you-choose-an-eap-type"></a>Opções adicionais ao escolher um tipo de EAP

#### <a name="server-trust"></a>Confiança do Servidor



|Nome da configuração|Mais informações|Usar quando|
|-------------|---------------|-----------|
|**Nomes de servidor de certificados**|Especifique um ou mais nomes comuns usados nos certificados emitidos pela sua AC (autoridade de certificação) confiável. Se você fornecer essas informações, poderá fazer o bypass da caixa de diálogo de confiança dinâmica que é exibida em dispositivos de usuários quando eles se conectam à rede Wi-Fi.|O tipo EAP é **EAP-TLS** ou **EAP-TTLS**|
|**Certificado raiz para validação do servidor**|Escolha o perfil de certificado raiz confiável usado para autenticar a conexão. |O tipo de EAP é **EAP-TLS**, **EAP-TTLS** ou **PEAP**|
|**Privacidade de identidade (identidade externa)**|Especifique o texto enviado em resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.|O tipo de EAP é **PEAP**|


#### <a name="client-authentication"></a>Autenticação do Cliente


|                                     Nome da configuração                                     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       Mais informações                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |                            Usar quando                            |
|--------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------|
| <strong>Certificado de cliente para autenticação de cliente (Certificado de identidade)</strong> |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       Escolha o perfil de certificado SCEP ou PKCS usado para autenticar a conexão.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |              O tipo de EAP é <strong>EAP-TLS</strong>              |
|                        <strong>Método de autenticação</strong>                        | Selecione o método de autenticação para a conexão:<br>- <strong>Certificados</strong> para selecionar o certificado cliente SCEP ou PKCS que é o certificado de identidade apresentado ao servidor.<br><br>- <strong>Nome de Usuário e Senha</strong> para especificar um método de autenticação diferente. <br><br>Se você selecionou <strong>Nome de Usuário e Senha</strong>, configure:<br><br>-  <strong>Método não EAP (identidade interna)</strong>, em seguida, selecione como você autenticará a conexão de:<br>- <strong>Nenhum</strong><br>- <strong>Senha não criptografada (PAP)</strong><br>- <strong>Protocolo CHAP</strong><br>- <strong>Microsoft CHAP (MS-CHAP)</strong><br>- <strong>Microsoft CHAP Versão 2 (MS-CHAP v2)</strong><br>As opções disponíveis dependem do tipo de EAP selecionado.<br><br><strong>e</strong><br><br>- <strong>Privacidade de identidade (identidade externa)</strong> – Especifique o texto enviado em resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro. | O tipo de EAP é <strong>EAP-TTLS</strong> ou <strong>PEAP</strong> |

