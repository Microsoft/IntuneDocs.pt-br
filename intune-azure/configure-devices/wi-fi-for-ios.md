---
title: "Configurações de Wi-Fi do Intune para dispositivos iOS | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: saiba mais sobre as configurações do Intune que você pode usar para configurar conexões Wi-Fi em dispositivos iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 89229a5e-3421-4221-a62f-fa800620cc0d
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ac907e4cb63e4175dafc4c50239d3e0cbe581ad9
ms.openlocfilehash: 1790878c1d1b4ad8381e6c3a3689542877ec6d26


---

# <a name="intune-wi-fi-settings-for-ios-devices-in-intune-azure-preview"></a>Configurações Wi-Fi para dispositivos iOS na versão prévia do Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]



## <a name="wi-fi-settings-for-basic-and-enterprise-profiles"></a>Configurações Wi-Fi para perfis básico e empresarial

- **Nome da rede** – Insira um nome para esta conexão Wi-Fi. Esse é o nome que os usuários verão ao navegarem pela lista de conexões disponíveis no seu dispositivo.
- **SSID** – Abreviação de identificador de conjunto de serviço (service set identifier em inglês). Esse é o nome real da rede sem fio à qual os dispositivos se conectarão. No entanto, os usuários veem apenas o nome de rede criado anteriormente ao escolher a conexão.
- **Conectar-se automaticamente** – Faz com que o dispositivo se conecte sempre que estiver no intervalo da rede.
- **Rede oculta** – Impede que essa rede seja exibida na lista de redes disponíveis no dispositivo.
- **Configurações de proxy** – Escolha dentre:
    - **Nenhum** – Nenhuma configuração de proxy será definida.
    - **Manual** – Insira o **Endereço do servidor proxy** (como um endereço IP) e seu **Número da porta** associado.
    - **Automático** – Use um arquivo para configurar o servidor proxy. Digite a **URL do servidor proxy** (por exemplo **http://proxy.contoso.com**) que contém o arquivo de configuração.

## <a name="wi-fi-settings-for-basic-profiles-only"></a>Configurações Wi-Fi apenas para perfis básicos

- **Tipo de segurança** – Selecione o protocolo de segurança a ser usado para autenticar-se à rede Wi-Fi:
    - **Abrir (sem autenticação)** – Use essa opção somente se a rede não for segura.
    - **WPA/WPA2 – Pessoal**
    - **WEP**

## <a name="wi-fi-settings-for-enterprise-profiles-only"></a>Configurações Wi-Fi para apenas para perfis empresariais

- **Tipo de EAP** – Escolha o tipo de Protocolo EAP (Extensible Authentication Protocol) usado para autenticar as conexões sem fio seguras:
    - **EAP-FAST**
    - **EAP-SIM**
    - **EAP-TLS**
    - **EAP-TTLS**
    - **LEAP**
    - **PEAP**

### <a name="further-options-when-you-choose-an-eap-type"></a>Opções adicionais ao escolher um tipo de EAP


|Nome da configuração|Mais informações|Usar quando|
|--------------|-------------|----------|
|**Configurações de PAC (Protected Access Credential)**|Selecione para usar credenciais de acesso protegido para estabelecer um túnel autenticado entre o cliente e o servidor de autenticação. Selecione um de:<br>- **Usar PAC** – Um arquivo PAC existente será usado, se existir.<br>- **Usar e Provisionar PAC** – Provisiona o arquivo PAC para os dispositivos.<br>- **Usar e Provisionar PAC Anonimamente** – Provisione o arquivo PAC para seus dispositivos e verifique se tal arquivo foi provisionado sem autenticar o servidor.|O tipo de EAP é **EAP-FAST**|

#### <a name="server-trust"></a>Confiança do Servidor


|Nome da configuração|Mais informações|Usar quando|
|--------------|-------------|----------|
|**Nomes de servidor de certificados**|Especifique um ou mais nomes comuns usados nos certificados emitidos pela sua AC (autoridade de certificação) confiável. Se você fornecer essas informações, poderá fazer o bypass da caixa de diálogo de confiança dinâmica que é exibida em dispositivos de usuários finais quando eles se conectam à rede Wi-Fi.|O tipo de EAP é **EAP-TLS**, **EAP-TTLS** ou **PEAP**.|
|**Certificado raiz para validação do servidor**|Escolha o perfil de certificado raiz confiável usado para autenticar a conexão. |O tipo de EAP é **EAP-TLS**, **EAP-TTLS** ou **PEAP**|
|**Privacidade de identidade (identidade externa)**|Especifique o texto enviado em resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.|O tipo de EAP é **PEAP**|


#### <a name="client-authentication"></a>Autenticação do Cliente


|Nome da configuração|Mais informações|Usar quando|
|--------------|-------------|----------|
|**Certificado de cliente para autenticação de cliente (Certificado de identidade)**|Escolha o perfil de certificado SCEP ou PKCS usado para autenticar a conexão.|O tipo de EAP é **EAP-TLS**|
|**Método de autenticação**|Selecione o método de autenticação para a conexão:<br>- **Certificados** para selecionar o certificado cliente SCEP ou PKCS que é o certificado de identidade apresentado ao servidor.<br><br>- **Nome de Usuário e Senha** para especificar um método de autenticação diferente. <br><br>Se você selecionou **Nome de Usuário e Senha**, configure:<br><br>-  **Método não EAP (identidade interna)**, em seguida, selecione como você autenticará a conexão de:<br>- **Nenhum**<br>- **Senha não criptografada (PAP)**<br>- **Protocolo CHAP**<br>- **Microsoft CHAP (MS-CHAP)**<br>- **Microsoft CHAP Versão 2 (MS-CHAP v2)**<br>As opções disponíveis dependem do tipo de EAP selecionado.<br><br>**e**<br><br>- **Privacidade de identidade (identidade externa)** – Especifique o texto enviado em resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.|O tipo de EAP é **EAP-TTLS** ou *



<!--HONumber=Feb17_HO1-->


