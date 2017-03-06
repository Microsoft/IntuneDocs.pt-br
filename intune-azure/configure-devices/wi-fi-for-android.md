---
title: "Configurações de Wi-Fi do Intune para dispositivos Android | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: saiba mais sobre as configurações do Intune que você pode usar para configurar conexões Wi-Fi em dispositivos Android."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 103e17a4-2993-4359-b340-73e2acf4cf7d
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: e4d42dd165d6a485e9b5691ef9ed9f420d82d3dc
ms.lasthandoff: 02/16/2017


---

# <a name="wi-fi-settings-for-android-devices-in-microsoft-intune"></a>Configurações de Wi-Fi para dispositivos Android no Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="wi-fi-settings-for-basic-and-enterprise-profiles"></a>Configurações Wi-Fi para perfis básico e empresarial

- **Nome da rede** – Insira um nome para esta conexão Wi-Fi. Esse é o nome que os usuários verão ao navegarem pela lista de conexões disponíveis no seu dispositivo.
- **SSID** – Abreviação de identificador de conjunto de serviço (service set identifier em inglês). Esse é o nome real da rede sem fio à qual os dispositivos se conectarão. No entanto, os usuários veem apenas o nome de rede criado anteriormente ao escolher a conexão.
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
|**Nomes de servidor de certificados**|Especifique um ou mais nomes comuns usados nos certificados emitidos pela sua AC (autoridade de certificação) confiável. Se você fornecer essas informações, poderá fazer o bypass da caixa de diálogo de confiança dinâmica que é exibida em dispositivos de usuários finais quando eles se conectam à rede Wi-Fi.|O tipo EAP é **EAP-TLS** ou **EAP-TTLS**|
|**Certificado raiz para validação do servidor**|Escolha o perfil de certificado raiz confiável usado para autenticar a conexão. |O tipo de EAP é **EAP-TLS**, **EAP-TTLS** ou **PEAP**|
|**Privacidade de identidade (identidade externa)**|Especifique o texto enviado em resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.|O tipo de EAP é **PEAP**|


#### <a name="client-authentication"></a>Autenticação do Cliente


|Nome da configuração|Mais informações|Usar quando|
|----------|--------------|----------|
|**Certificado de cliente para autenticação de cliente (Certificado de identidade)**|Escolha o perfil de certificado SCEP ou PKCS usado para autenticar a conexão.|O tipo de EAP é **EAP-TLS**|
|**Método de autenticação**|Selecione o método de autenticação para a conexão:<br>- **Certificados** para selecionar o certificado cliente SCEP ou PKCS que é o certificado de identidade apresentado ao servidor.<br><br>- **Nome de Usuário e Senha** para especificar um método de autenticação diferente. <br><br>Se você selecionou **Nome de Usuário e Senha**, configure:<br><br>-  **Método não EAP (identidade interna)**, em seguida, selecione como você autenticará a conexão de:<br>- **Nenhum**<br>- **Senha não criptografada (PAP)**<br>- **Protocolo CHAP**<br>- **Microsoft CHAP (MS-CHAP)**<br>- **Microsoft CHAP Versão 2 (MS-CHAP v2)**<br>As opções disponíveis dependem do tipo de EAP selecionado.<br><br>**e**<br><br>- **Privacidade de identidade (identidade externa)** – Especifique o texto enviado em resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.|O tipo de EAP é **EAP-TTLS** ou **PEAP**|
