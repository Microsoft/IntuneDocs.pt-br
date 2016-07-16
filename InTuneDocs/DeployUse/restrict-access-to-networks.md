---
title: Restringir o acesso a redes com o Cisco ISE | Microsoft Intune
description: "Use o Cisco ISE com o Intune para que os dispositivos sejam registrados no Intune e compatíveis com a política antes de acessarem Wi-Fi e VPN controlada pelo Cisco ISE."
keywords: 
author: nbigman
manager: jeffgilb
ms.date: 06/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5631bac3-921d-438e-a320-d9061d88726c
translationtype: Human Translation
ms.sourcegitcommit: f33a86c51320c75ce74d20e0cac2b9581990ecec
ms.openlocfilehash: 78945498a951e7b897164ae6f33c4e87d521ca5b


---

# Usando o Cisco ISE com o Microsoft Intune
A integração do Intune com o Cisco ISE permite criar políticas de rede em seu ambiente ISE usando o estado de conformidade e de registro do dispositivo do Intune. Essas políticas podem trabalhar para garantir que o acesso à rede da empresa seja restrito aos dispositivos gerenciados pelo Intune e em conformidade com as políticas do Intune. 

## Configuração

Para habilitar essa integração, você não precisa fazer nenhuma configuração no seu locatário do Intune. Você precisa fornecer permissões para seu servidor Cisco ISE para acessar o locatário do Intune e, depois disso, o restante da instalação acontece em seu servidor Cisco ISE. Este artigo fornece instruções sobre como fornecer a seu servidor ISE as permissões para acessar seu locatário do Intune. 

### Etapa 1: Gerenciar os certificados
1. No console do AAD (Azure Active Directory), exporte o certificado. 

    #### Internet Explorer 11
        
    a. Execute o Internet Explorer como administrador e faça logon no console do AAD.
  
    b. Escolha o ícone de cadeado na barra de endereços e escolha **Exibir certificados**
    
    c. Na guia **Detalhes** das propriedades do certificado, escolha **Copiar para arquivo**.

    d. Na página de boas-vindas **Assistente para Exportação de Certificados**, escolha **Avançar**. 

    e. Na pagina **Formato do arquivo de exportação**, deixe o padrão **x.509 binário codificado por DER (.CER)** e escolha **Avançar**.  

    f. Na página **Arquivo a ser exportado**, escolha **Procurar** para escolher um local no qual salvar o arquivo e forneça um nome de arquivo. Embora pareça que você está escolhendo um arquivo a ser exportado, na verdade você está nomeando o arquivo para o qual o certificado exportado será salvo. Escolha **Avançar** &gt; **Concluir**.

    #### Safari
    
    a. Faça logon no console do AAD.

    b. Escolha o ícone de cadeado &gt;  **Mais informações**.
    
    c. Escolha **Exibir certificado** &gt; **Detalhes**.

    d. Escolha o certificado e, em seguida, escolha **Exportar**.  


> [!IMPORTANT]
> Verifique a data de validade do certificado, pois você terá que exportar e importar um novo certificado quando este expirar.

    

2. De dentro do console do ISE, importe o certificado do Intune (o arquivo exportado) para o repositório **Certificados Confiáveis**.
3. No seu console do ISE, vá para **Administração** > **Certificados** > **Certificados do Sistema**.
4. Escolha o certificado do ISE e, em seguida, escolha **Exportar**.
5. Em um editor de texto, edite o certificado exportado:
 - Excluir ** -----INICIAR CERTIFICADO-----**
 - Excluir ** -----CONCLUIR CERTIFICADO-----**
 - Verifique se todo o texto está em uma única linha

### Etapa 2: Criar um aplicativo para o ISE em seu locatário do AAD
1. No console do AAD (Azure Active Directory), escolha **Aplicativos** > **Adicionar um aplicativo** > **Adicionar um aplicativo que minha organização esteja desenvolvendo**.
2. Forneça um nome e uma URL para o aplicativo. A URL pode ser o site da empresa.
3. Baixe o manifesto do aplicativo (um arquivo JSON).
4. Edite o arquivo JSON de manifesto. Na configuração da chamada **keyCredentials**, forneça o texto do certificado editado na Etapa 1 como valor da configuração.
5. Salve o arquivo sem alterar seu nome.
6. Forneça a seu aplicativo permissões para o Microsoft Graph e a API do Microsoft Intune.
    1. Do Microsoft Graph, escolha o seguinte
        - **Permissões do aplicativo**: ler dados do diretório
        - **Permissões delegadas**: 
            - Acessar dados do usuário a qualquer momento
          - Conectar usuários
   2. Para a API do Microsoft Intune, em **Permissões do aplicativo**, escolha **Obter estado do dispositivo e conformidade do Intune**.

7. Escolha **Exibir pontos de extremidade** e copie os seguintes valores para uso nas configurações do ISE:

|Valor no portal do AAD|Campo correspondente no portal do ISE|
|-------------------|---------------------------------|
|Ponto de extremidade da API do Microsoft Azure AD Graph|URL de descoberta automática|
|Ponto de Extremidade do Token OAuth 2.0|URL de emissão de token|
|Atualizar seu código com sua ID de cliente|ID do Cliente|


### Etapa 3: Definir configurações do ISE 
2. No console de administração do ISE, forneça estes valores de configuração: 
  - **Tipo de servidor**: Gerenciador de Dispositivos Móveis
  - **Tipo de autenticação**: OAuth – Credenciais do cliente
  - **Descoberta automática**: sim
  - **URL de descoberta automática**: insira o valor da Etapa 1
  - **ID do cliente**: insira o valor da Etapa 1
  - **URL de emissão de token**: insira o valor da Etapa 1



## Informações compartilhadas entre seu locatário do Intune e seu servidor Cisco ISE
Esta tabela lista as informações compartilhadas entre seu locatário do Intune e seu servidor Cisco ISE para dispositivos gerenciados pelo Intune.

|Propriedade|  Descrição|
|---------------|------------------------------------------------------------|
|complianceState|   Verdadeiro ou falso (string) que indica se o dispositivo é compatível ou incompatível.|
|isManaged| Verdadeiro ou falso (que indica se o cliente é gerenciado pelo Intune ou não.|
|macAddress|Endereço Mac do dispositivo.|
|serialNumber|O número de modelo do dispositivo. Aplica-se somente a dispositivos iOS.|
|imei|O IMEI (15 dígitos decimais: 14 dígitos mais um dígito de verificação) ou IMEISV (16 dígitos) inclui informações sobre a origem, o modelo e o número de série do dispositivo. A estrutura do IMEI/SV é especificada em 3GPP TS 23.003. Aplica-se apenas aos dispositivos com cartões SIM.)|
|udid|O identificador de dispositivo exclusivo, uma sequência de 40 letras e números específicos para dispositivos iOS.|
|meid|Identificador de equipamentos móveis, um número exclusivo globalmente que identifica uma peça física de equipamentos de estação móvel CDMA. O formato de número é definido pelo relatório 3GPP2 S.R0048, mas em termos práticos, ele pode ser visto como um IMEI, mas com dígitos hexadecimais. Um MEID tem 56 bits (14 dígitos hexadecimais). Ele consiste em três campos, incluindo um código regional de 8 bits (RR), um código do fabricante de 24 bits e um número de série atribuído pelo fabricante de 24 bits.| 
|osVersion| Versão do sistema operacional do dispositivo.
|modelo|Modelo do dispositivo.
|fabricante|Fabricante do dispositivo.
|azureDeviceId| A ID do dispositivo após ele ter o local de trabalho associado com o Azure Active Directory. Será um guid vazio para dispositivos que não estão associados.|
|lastContactTimeUtc|A data e hora quando o dispositivo fez a última verificação no serviço de gerenciamento do Intune. 


## Experiência do usuário

Quando um usuário tenta acessar recursos usando um dispositivo não registrado, eles recebe uma solicitação para registrar, como mostrado aqui:

![Exemplo da solicitação de registro](../media/cisco-ise-user-iphone.png)

Quando o usuário escolhe registrar, ele é redirecionado para o processo de registro do Intune. A experiência de registro do usuário para o Intune é descrita nestes tópicos:

- [Registrar seu dispositivo Android no Intune](/intune/end-user/enroll-your-device-in-Intune-android)</br>
- [Registrar seu dispositivo iOS no Intune](/intune/end-user/enroll-your-device-in-intune-ios)</br>
- [Registrar seu dispositivo Mac OS X no Intune](/intune/end-user/enroll-your-device-in-intune-mac-os-x)</br>
- [Registrar seu dispositivo Windows no Intune](/intune/end-user/enroll-your-device-in-intune-windows)</br> 

Também há um [conjunto baixável de instruções de registro](https://gallery.technet.microsoft.com/End-user-Intune-enrollment-55dfd64a) que você pode usar para criar orientação personalizada para sua experiência de usuário.


### Consulte também

[Guia do Administrador do Mecanismo de Serviços de Identidade da Cisco, versão 2.1](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html#task_820C9C2A1A6647E995CA5AAB01E1CDEF)




<!--HONumber=Jun16_HO4-->


