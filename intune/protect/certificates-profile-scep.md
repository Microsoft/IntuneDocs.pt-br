---
title: Usar perfis de Certificado SCEP com o Microsoft Intune – Azure | Microsoft Docs
description: Crie e atribua perfis de certificado do protocolo SCEP com o Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/13/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3cd153a4c602ba49a5b5135d1d6cb32a61f2668d
ms.sourcegitcommit: 47c9af81c385c7e893fe5a85eb79cf08e69e6831
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/25/2020
ms.locfileid: "77576503"
---
# <a name="create-and-assign-scep-certificate-profiles-in-intune"></a>Criar e atribuir perfis de Certificado SCEP no Intune

Depois de [configurar a infraestrutura](certificates-scep-configure.md) para dar suporte a certificados do protocolo SCEP, você poderá criar e, em seguida, atribuir perfis de Certificado SCEP a usuários e dispositivos no Intune.

> [!IMPORTANT]  
> Antes de criar perfis de Certificado SCEP, os dispositivos que usarão um perfil de Certificado SCEP precisarão confiar na AC (autoridade de certificação) raiz confiável. Use um *perfil de certificado confiável* no Intune para provisionar o Certificado de Autoridade de Certificação raiz confiável para usuários e dispositivos. Para obter informações sobre o perfil de certificado confiável, confira [Exportar o Certificado de Autoridade de Certificação raiz confiável](certificates-configure.md#export-the-trusted-root-ca-certificate) e [Criar perfis de certificado confiável](certificates-configure.md#create-trusted-certificate-profiles) em *Usar certificados para autenticação no Intune*.


## <a name="create-a-scep-certificate-profile"></a>Criar um perfil de certificado SCEP

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecione **Dispositivos** > **Perfis de configuração** > **Criar perfil**.

3. Insira as seguintes propriedades:

4. Insira um **Nome** e uma **Descrição** para o perfil de certificado SCEP.

5. Na lista suspensa **Plataforma**, selecione uma [plataforma de dispositivo compatível](certificates-configure.md#supported-platforms-and-certificate-profiles) para esse Certificado SCEP.

6. Na lista suspensa **Tipo de perfil**, selecione **Certificado SCEP**.  

   Para a plataforma **Android Enterprise**, o *Tipo de perfil* é dividido em duas categorias: *Somente Proprietário do Dispositivo* e *Somente Perfil de Trabalho*. Certifique-se de selecionar o perfil de certificado SCEP correto para os dispositivos que você gerencia.  

   Os perfis de certificado CEP para o perfil *Somente Proprietário do Dispositivo* têm as seguintes limitações:

   1. Em Monitoramento, o relatório de certificado não está disponível para perfis de certificado SCEP do Proprietário do Dispositivo.

   2. Você não pode usar o Intune para revogar certificados que foram provisionados por perfis de certificado SCEP para Proprietários de Dispositivo. Você pode gerenciar a revogação por meio de um processo externo ou diretamente com a autoridade de certificação. 

   4. Para dispositivos Android Enterprise dedicados, perfis de certificado SCEP têm suporte somente para configuração e autenticação de rede Wi-Fi.  Os perfis de certificado SCEP em dispositivos Android Enterprise dedicados não têm suporte para autenticação de aplicativo ou VPN.   

   
7. Selecione **Configurações** e, em seguida, conclua as seguintes configurações:

   - **Tipo de certificado**:

     *(Aplica-se ao:  Android, Android Enterprise, iOS/iPadOS, macOS, Windows 8.1 e posterior e Windows 10 e posterior.)*

     Selecione um tipo, dependendo de como você usará o perfil de certificado:

     - **Usuário**: Os certificados de *usuário* podem conter atributos de usuário e de dispositivo na entidade e no SAN do certificado.  
     - **Dispositivo**:  Certificados de *dispositivo* podem conter somente os atributos do dispositivo na entidade e no SAN do certificado.

       Use **Dispositivo** para cenários como dispositivos sem usuário (como quiosques) ou para dispositivos Windows. Em dispositivos Windows, o certificado é colocado no repositório de certificados do computador local.

   - **Formato de nome de entidade**:

     Selecione como o Intune cria automaticamente o nome da entidade na solicitação de certificado. As opções para o formato de nome da entidade dependem do Tipo de certificado selecionado, **Usuário** ou **Dispositivo**.

     > [!NOTE]
     > Há um [problema conhecido](#avoid-certificate-signing-requests-with-escaped-special-characters) no uso do SCEP para obter certificados quando o nome da entidade na CSR (Solicitação de Assinatura de Certificado) resultante inclui um dos seguintes caracteres como um caractere de escape (seguido por uma barra invertida \\):
     > - \+
     > - ;
     > - ,
     > - =

     - **Tipo de certificado de usuário**

       As opções de formato para o *Formato de nome da entidade* incluem:

       - **Não configurado**
       - **Nome comum**
       - **Nome comum incluindo email**
       - **Nome comum como email**
       - **IMEI (Identificação Internacional de Equipamento Móvel)**
       - **Número de série**
       - **Personalizado**: Ao selecionar essa opção, a caixa de texto **Personalizado** também é exibida. Use esse campo para inserir um formato de nome de entidade personalizado, incluindo variáveis. O formato personalizado dá suporte a duas variáveis: **Nome Comum (NC)** e **Email (E)** . **CN (Nome Comum)** pode ser definido para qualquer uma das seguintes variáveis:

         - **CN={{UserName}}** : O nome UPN do usuário, como janedoe@contoso.com.
         - **CN={{AAD_Device_ID}}** : Uma ID atribuída ao registrar um dispositivo no Azure AD (Active Directory). Essa ID normalmente é usada para autenticar com o Azure AD.
         - **CN={{SERIALNUMBER}}** : O SN (número de série) exclusivo normalmente usado pelo fabricante para identificar um dispositivo.
         - **CN={{IMEINumber}}** : O número exclusivo do IMEI (Identidade Internacional de Equipamento Móvel) usado para identificar um celular.
         - **CN={{OnPrem_Distinguished_Name}}** : Uma sequência de nomes diferenciados relativos separados por vírgula, como *CN=Leila Dias,OU=UserAccounts,DC=corp,DC=contoso,DC=com*.

           Para usar a variável *{{OnPrem_Distinguished_Name}}* , sincronize o atributo de usuário *onpremisesdistinguishedname* com o Azure AD usando o [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

         - **CN={{onPremisesSamAccountName}}** : Os administradores podem sincronizar o atributo samAccountName do Active Directory para o Azure AD usando o Azure AD Connect em um atributo chamado *onPremisesSamAccountName*. O Intune pode substituir essa variável como parte de uma solicitação de emissão de certificados na entidade de um certificado. O atributo samAccountName é o nome de entrada do usuário usado para dar suporte a clientes e servidores de uma versão anterior do Windows (pré-Windows 2000). O formato do nome de entrada do usuário é: *DomainName\testUser* ou apenas *testUser*.

            Para usar a variável *{{onPremisesSamAccountName}}* , sincronize o atributo de usuário *onPremisesSamAccountName* com o Azure AD usando o [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

         Usando uma combinação de uma ou mais dessas variáveis e cadeias de caracteres estáticas, é possível criar um formato de nome de entidade personalizado, como:  
         - **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US**

         Este exemplo inclui um formato de nome de entidade que usa as variáveis CN e E e cadeias de caracteres para os valores Unidade Organizacional, Organização, Localização, Estado e País. [Função CertStrToName](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) descreve essa função e suas cadeias de caracteres compatíveis.

      - **Tipo de certificado de dispositivo**

        As opções de formato para o Formato de nome da entidade incluem as seguintes variáveis:

        - **{{AAD_Device_ID}}** ou **{{AzureADDeviceId}}** – qualquer variável pode ser usada para identificar um dispositivo por sua ID do Azure AD.
        - **{{Device_Serial}}**
        - **{{Device_IMEI}}**
        - **{{SerialNumber}}**
        - **{{IMEINumber}}**
        - **{{WiFiMacAddress}}**
        - **{{IMEI}}**
        - **{{DeviceName}}**
        - **{{FullyQualifiedDomainName}}** *(Aplicável somente aos dispositivos Windows e ingressados no domínio)*
        - **{{MEID}}**

        Especifique essas variáveis, seguidas pelo texto da variável, na caixa de texto. Por exemplo, o nome comum para um dispositivo chamado *Device1* pode ser adicionado como **CN={{DeviceName}}Device1**.

        > [!IMPORTANT]
        > - Ao especificar uma variável, coloque o nome da variável entre chaves { }, como mostrado no exemplo, para evitar um erro.  
        > - As propriedades do dispositivo usadas na *entidade* ou no *SAN* de um certificado de dispositivo, como **IMEI**, **SerialNumber** e **FullyQualifiedDomainName**, são propriedades que podem ser falsificadas por uma pessoa com acesso ao dispositivo.
        > - Um dispositivo precisa dar suporte a todas as variáveis especificadas em um perfil de certificado para que esse perfil seja instalado nesse dispositivo.  Por exemplo, se **{{IMEI}}** for usado no nome da entidade de um perfil SCEP e for atribuído a um dispositivo que não tenha um número IMEI, o perfil não será instalado.

   - **Nome alternativo da entidade**: Selecione como o Intune cria automaticamente o SAN (nome alternativo da entidade) na solicitação de certificado. As opções para o SAN dependem do Tipo de certificado selecionado, **Usuário** ou **Dispositivo**.

      - **Tipo de certificado de usuário**

        Selecione um dos atributos disponíveis:

        - **Endereço de email**
        - **Nome UPN**

        Por exemplo, os tipos de certificado de usuário podem incluir o nome UPN no nome alternativo da entidade. Se um certificado do cliente for usado para se autenticar em um Servidor de Políticas de Rede, defina o nome alternativo da entidade como o UPN.

      - **Tipo de certificado de dispositivo**

        Use a lista suspensa **Atributo** e selecione um atributo, atribua um **Valor** e **Adicione**-o ao perfil de certificado. Adicione vários valores selecionando mais atributos.

        Os atributos disponíveis incluem:

        - **Endereço de email**
        - **Nome UPN**
        - **DNS**

        Com o tipo de certificado *Dispositivo*, é possível usar as seguintes variáveis de certificado do dispositivo para o valor:

        - **{{AAD_Device_ID}}** ou **{{AzureADDeviceId}}** – qualquer variável pode ser usada para identificar um dispositivo por sua ID do Azure AD.
        - **{{Device_Serial}}**
        - **{{Device_IMEI}}**
        - **{{SerialNumber}}**
        - **{{IMEINumber}}**
        - **{{WiFiMacAddress}}**
        - **{{IMEI}}**
        - **{{DeviceName}}**
        - **{{FullyQualifiedDomainName}}**
        - **{{MEID}}**

        Para especificar um valor para um atributo, inclua o nome da variável com chaves, seguido pelo texto da variável. Por exemplo, um valor para o atributo DNS pode ser adicionado como **{{AzureADDeviceId}}.domain.com**, em que *.domain.com* é o texto. Para um usuário chamado *User1*, um endereço de email poderá ser exibido como {{FullyQualifiedDomainName}}User1@Contoso.com.

        > [!IMPORTANT]
        > - Ao usar uma variável de certificado do dispositivo, coloque a variável entre chaves { }.
        > - Não use chaves **{ }** , símbolos de barra vertical **|** nem ponto e vírgula **;** no texto após a variável.
        > - As propriedades do dispositivo usadas na *entidade* ou no *SAN* de um certificado de dispositivo, como **IMEI**, **SerialNumber** e **FullyQualifiedDomainName**, são propriedades que podem ser falsificadas por uma pessoa com acesso ao dispositivo.
        > - Um dispositivo precisa dar suporte a todas as variáveis especificadas em um perfil de certificado para que esse perfil seja instalado nesse dispositivo.  Por exemplo, se **{{IMEI}}** for usado no SAN de um perfil SCEP e for atribuído a um dispositivo que não tenha um número IMEI, o perfil não será instalado.

   - **Período de validade do certificado**:

     Você pode inserir um valor inferior ao período de validade no modelo de certificado, mas não superior. Se você configurou o modelo de certificado para [dar suporte a um valor personalizado que pode ser definido no console do Intune](certificates-scep-configure.md#modify-the-validity-period-of-the-certificate-template), use essa configuração para especificar o tempo restante antes que o certificado expire.

     Por exemplo, se o período de validade do certificado em um modelo de certificado for de dois anos, você poderá inserir um valor de um ano, mas não de cinco anos. O valor também tem que ser inferior ao período de validade restante do certificado da AC emissora.

   - **KSP (provedor de armazenamento de chaves)** :

     *(Aplica-se ao:  Windows 8.1 e posterior e Windows 10 e posterior)*

     Especifique o local de armazenamento da chave para o certificado. Escolha um dos seguintes valores:

     - **Registrar no KSP do TPM (Trusted Platform Module) se existir; caso contrário, no KSP de Software**
     - **Registrar no KSP do TPM (Trusted Platform Module); caso contrário, falha**
     - **Registrar no Passport; caso contrário, falha (Windows 10 e posterior)**
     - **Registrar no Software KSP**

   - **Uso de chave**:

     Selecione as opções de uso de chave para o certificado:

     - **Assinatura digital**: Permita a troca de chaves apenas quando uma assinatura digital ajuda a proteger a chave.
     - **Criptografia de chave**: Permita a troca de chaves apenas quando a chave estiver criptografada.

   - **Tamanho da chave (bits)** :

     Selecione o número de bits contidos na chave.

   - **Algoritmo de hash**:

     *(Aplica-se ao Android, Android Enterprise, Windows Phone 8.1, Windows 8.1 e posterior e Windows 10 e posterior)*

     Selecione um dos tipos de algoritmo de hash disponíveis para uso com esse certificado. Selecione o nível mais alto de segurança que dá suporte aos dispositivos de conexão.

   - **Certificado Raiz**:

     Selecione o *perfil de certificado confiável* configurado anteriormente e atribuído aos usuários e dispositivos aplicáveis nesse perfil de Certificado SCEP. O perfil de certificado confiável é usado para provisionar usuários e dispositivos com o Certificado de Autoridade de Certificação raiz confiável. Para obter informações sobre o perfil de certificado confiável, confira [Exportar o Certificado de Autoridade de Certificação raiz confiável](certificates-configure.md#export-the-trusted-root-ca-certificate) e [Criar perfis de certificado confiável](certificates-configure.md#create-trusted-certificate-profiles) em *Usar certificados para autenticação no Intune*. Se você tiver uma autoridade de certificação raiz e uma autoridade de certificação emissora, selecione o perfil de certificado raiz confiável associado à autoridade de certificação emissora.

   - **Uso estendido de chave**:

     Adicione valores para a finalidade desejada do certificado. Na maioria dos casos, o certificado exige a *autenticação de cliente*, de modo que o usuário ou o dispositivo possa se autenticar em um servidor. Adicione mais usos de chave, conforme necessário.

   - **Limite de renovação (%)** :

     Insira o percentual do tempo de vida restante do certificado antes da renovação das solicitações de dispositivo do certificado. Por exemplo, se você inserir 20, haverá uma tentativa de renovação do certificado quando o certificado estiver 80% expirado. As tentativas de renovação continuarão até que a renovação seja bem-sucedida. A renovação gera um novo certificado, o que resulta em um novo par de chaves pública/privada.

   - **URLs de servidor SCEP**:

     Insira uma ou mais URLs para os servidores NDES que emitem certificados por meio do protocolo SCEP. Por exemplo, insira algo como *https://ndes.contoso.com/certsrv/mscep/mscep.dll* . Adicione outras URLs do SCEP para balanceamento de carga, conforme necessário, pois as URLs são enviadas por push aleatoriamente para o dispositivo com o perfil. Se um dos servidores do SCEP não estiver disponível, a solicitação do SCEP falhará e será possível que, em futuros check-ins do dispositivo, a solicitação de certificado seja feita no mesmo servidor que está inativo.

8. Selecione **OK** e, em seguida, **Criar**. O perfil é criado e exibido na lista *Configuração de dispositivo – Perfis*.

### <a name="avoid-certificate-signing-requests-with-escaped-special-characters"></a>Evitar solicitações de assinatura de certificado com caracteres especiais de escape

Há um problema conhecido em solicitações de certificado SCEP e PKCS que incluem um Nome de Entidade (CN) com um ou mais dos caracteres especiais a seguir como um caractere de escape. Os nomes de entidades que incluem um dos caracteres especiais como um caractere de escape resultam em um CSR com um nome de entidade incorreto. Um nome de entidade incorreto resulta em falha na validação do desafio SCEP do Intune e na não emissão do certificado.

Os caracteres especiais são:
- \+
- ,
- ;
- =

Quando o nome da entidade incluir um dos caracteres especiais, use uma das seguintes opções para contornar essa limitação:

- Encapsule com aspas o valor de CN que contém o caractere especial.  
- Remova o caractere especial do valor de CN.

**Por exemplo**, você tem um nome de entidade que aparece como *Usuário de teste (TestCompany, LLC)* .  Um CSR que inclui um CN que tem a vírgula entre *TestCompany* e *LLC* apresenta um problema.  O problema pode ser evitado com o uso de aspas em todo o CN ou com a remoção da vírgula entre *TestCompany* e *LLC*:

- **Adicione aspas**: *CN =* "Usuário de teste (TestCompany, LLC)”,OU=UserAccounts,DC=corp,DC=contoso,DC=com*
- **Remova a vírgula**: *CN=Usuário de teste (TestCompany LLC),OU=UserAccounts,DC=corp,DC=contoso,DC=com*

 No entanto, as tentativas de retirar a vírgula usando um caractere de barra invertida falharão com um erro nos logs do CRP:
 
- **Vírgula com escape**: *CN=Usuário de teste (TestCompany\\, LLC),OU=UserAccounts,DC=corp,DC=contoso,DC=com*

O erro é semelhante ao seguinte:

```
Subject Name in CSR CN="Test User (TESTCOMPANY\, LLC),OU=UserAccounts,DC=corp,DC=contoso,DC=com" and challenge CN=Test User (TESTCOMPANY\, LLC),OU=UserAccounts,DC=corp,DC=contoso,DC=com do not match  

  Exception: System.ArgumentException: Subject Name in CSR and challenge do not match

   at Microsoft.ConfigurationManager.CertRegPoint.ChallengeValidation.ValidationPhase3(PKCSDecodedObject pkcsObj, CertEnrollChallenge challenge, String templateName, Int32 skipSANCheck)

Exception:    at Microsoft.ConfigurationManager.CertRegPoint.ChallengeValidation.ValidationPhase3(PKCSDecodedObject pkcsObj, CertEnrollChallenge challenge, String templateName, Int32 skipSANCheck)

   at Microsoft.ConfigurationManager.CertRegPoint.Controllers.CertificateController.VerifyRequest(VerifyChallengeParams value
```

## <a name="assign-the-certificate-profile"></a>Atribuir o perfil de certificado

Atribua perfis de Certificado SCEP da mesma maneira que você [implanta perfis de dispositivo](../configuration/device-profile-assign.md) para outras finalidades. No entanto, considere o seguinte antes de continuar:

- Quando você atribui perfis de Certificado SCEP a grupos, o arquivo do Certificado de Autoridade de Certificação raiz confiável (conforme especificado no *perfil do certificado confiável*) é instalado no dispositivo. O dispositivo usa o perfil de Certificado SCEP para criar uma solicitação de certificado para esse Certificado de Autoridade de Certificação raiz confiável.

- O perfil de Certificado SCEP é instalado somente em dispositivos que executam a plataforma especificada durante a criação do perfil de certificado.

- Você pode atribuir perfis de certificado para coleções de usuários ou coleções de dispositivos.

- Para publicar um certificado em um dispositivo rapidamente depois que o dispositivo for registrado, atribua o perfil de certificado a um grupo de usuários em vez de um grupo de dispositivos. Se você atribuir um grupo de dispositivos, um registro de dispositivo completo será necessário para que o dispositivo receba políticas.

- Se você usar o cogerenciamento para o Intune e o Configuration Manager, no Configuration Manager, [defina o controle deslizante da carga de trabalho](https://docs.microsoft.com/configmgr/comanage/how-to-switch-workloads) para as Políticas de Acesso ao Recurso como **Intune** ou **Piloto do Intune**. Essa configuração permite que os clientes do Windows 10 iniciem o processo de solicitar o certificado.

- Embora você crie e atribua o perfil de certificado confiável e o perfil de Certificado SCEP separadamente, ambos precisam ser atribuídos. Sem os dois instalados em um dispositivo, a política de certificação SCEP falhará. Verifique se todos os perfis de certificado raiz confiável também são implantados nos mesmos grupos do perfil SCEP.

> [!NOTE]
> Em dispositivos iOS/iPadOS, quando um perfil de certificado SCEP é associado a um perfil adicional, como um perfil Wi-Fi ou VPN, o dispositivo recebe um certificado para cada um dos perfis adicionais. Isso resulta em um dispositivo iOS/iPadOS tendo vários certificados entregues pela solicitação de certificado SCEP.  Se desejar obter um único certificado, use Certificados PKCS em vez de Certificados SCEP.  Isso se deve às diferenças em como os Certificados SCEP e os Certificados PKCS são entregues aos dispositivos.

## <a name="next-steps"></a>Próximas etapas

[Atribuir perfis](../configuration/device-profile-assign.md)

[Solucionar problemas de implantação de perfis de certificado SCEP](../protect/troubleshoot-scep-certificate-profiles.md)