---
title: "Configurações do Intune para o aplicativo Sala de aula do iOS"
titleSuffix: Intune on Azure
description: "Conheça as configurações do Intune que você pode usar para controlar as configurações do aplicativo Sala de aula em dispositivos iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1381a5ce-c743-40e9-8a10-4c218085bb5f
ms.reviewer: derriw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4188c3951c9cb864b77bde52a5d19f022f17c11c
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# Como definir as configurações do Intune para o aplicativo Sala de Aula para iOS
<a id="how-to-configure-intune-settings-for-the-ios-classroom-app" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## Introdução
<a id="introduction" class="xliff"></a>
[Sala de aula](https://itunes.apple.com/app/id1085319084) é um aplicativo que ajuda os professores a orientar o aprendizado e controlar os dispositivos dos alunos na sala de aula. Por exemplo, com o aplicativo, um professor pode:

- Abrir aplicativos nos dispositivos de alunos
- Bloquear e desbloquear a tela do iPad
- Exibir a tela do iPad de um aluno
- Navegue os iPads dos alunos até um favorito ou capítulo de um livro
- Exibir a tela do iPad de um aluno em uma Apple TV

Use o perfil de dispositivo **Educação** do Intune iOS e as informações neste tópico para ajudar a configurar o aplicativo Classroom, bem como os dispositivos nos quais você vai usá-lo.

## Antes de começar
<a id="before-you-start" class="xliff"></a>

Considere o seguinte antes de começar as configurações:

- Os iPads de professores e alunos devem ser registrados no Intune
- Verifique se o aplicativo [Sala de Aula da Apple](https://itunes.apple.com/us/app/classroom/id1085319084?mt=8) está instalado no dispositivo do professor. Instale o aplicativo manualmente ou use o [Gerenciamento de aplicativo do Intune](app-management.md).
- Você deve configurar certificados para autenticar conexões entre os dispositivos de professores e de alunos (consulte a Etapa 2)
- Os iPads de professores e alunos devem estar na mesma rede Wi-Fi e ter o Bluetooth habilitado
- O aplicativo Sala de Aula é executado em iPads supervisionados com o iOS 9.3 ou posterior
- Nesta versão, o Intune dá suporte ao gerenciamento de um cenário 1:1 em que cada aluno tem seu próprio iPad dedicado


## Etapa 1 - Importar os dados da escola para o Azure Active Directory
<a id="step-1---import-your-school-data-into-azure-active-directory" class="xliff"></a>

Use o SDS (School Data Sync) da Microsoft para importar registros escolares de um SIS (Sistema de Informações do Aluno) para o Azure Active Directory (Azure AD).
O SDS sincroniza as informações de seu SIS e as armazena no Azure AD. O Azure AD é um sistema de gerenciamento da Microsoft que ajuda você a organizar usuários e dispositivos. Depois, use esses dados para ajudar com o gerenciamento de seus alunos e salas de aula. [Saiba mais sobre como implantar o SDS](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91).

### Como importar dados usando o SDS
<a id="how-to-import-data-using-sds" class="xliff"></a>

Importe as informações no SDS usando um dos seguintes métodos:

- [Arquivos CSV](https://support.office.com/article/Follow-these-steps-71d5fe4a-aa51-4f35-9b53-348898a390a1) - exporte e compile manualmente os arquivos de valores separados por vírgulas (.csv)
- [API do PowerSchool](https://support.office.com/article/Follow-these-steps-851b5edc-558f-43a9-9122-b2d63458cb8f) - um provedor de SIS que simplifica a sincronização com o Azure AD
- [API Inteligente](https://support.office.com/article/Follow-these-steps-f3d92fde-3ad0-48f3-80a1-1ad0ac4a3fae) - uma solução de gerenciamento de identidade sincronizada diretamente com o Azure AD
- [OneRoster](https://support.office.com/article/Follow-these-steps-f43cbb2a-b502-497d-a8b1-783dc05a57ab) - um formato CSV que você pode exportar e converter para sincronizar com o Azure AD

### Saiba mais
<a id="find-out-more" class="xliff"></a>

- [Saiba mais sobre a experiência completa de sincronizar dados de escola locais com o Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)
- [Saiba mais sobre a sincronização do Microsoft School Data](https://sds.microsoft.com/)
- [Saiba mais sobre licenciamento no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)

## Etapa 2 - Criar e atribuir um perfil de Educação do iOS no Intune
<a id="step-2---create-and-assign-an-ios-education-profile-in-intune" class="xliff"></a>

### Definir as configurações gerais
<a id="configure-general-settings" class="xliff"></a>

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3.  Na folha **Intune**, escolha **Configurar dispositivos**.
4.  Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.
5.  Na folha de perfis, escolha **Criar Perfil**.
6.  Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de educação do iOS.
7.  Na lista suspensa **Plataforma**, escolha **iOS**.
8.  Na lista suspensa **Tipos de perfil**, escolha **Educação**.
9.  Escolha **Configurações** > **Definir**.


Depois, você precisa de certificados para estabelecer uma relação de confiança entre os iPads de professores e alunos. Os certificados são usados para autenticar conexões perfeita e silenciosamente entre os dispositivos sem precisar inserir nomes de usuário e senhas.

>[!IMPORTANT]
>Os certificados de professores e alunos que você usa devem ser emitidos por CAs (autoridades de certificação) diferentes. Você deve criar duas novas CAs subordinadas conectadas à sua infraestrutura de certificados; uma para professores e outra para alunos.

Perfis de educação iOS dão suporte somente a certificados PFX. Não há suporte para certificados SCEP.

Os certificados que você cria devem oferecer suporte à autenticação de servidor, além da autenticação de usuário.

### Configurar certificados de professor
<a id="configure-teacher-certificates" class="xliff"></a>

Na folha **Educação**, escolha **Certificados de professor**.

#### Configurar o certificado raiz do professor
<a id="configure-teacher-root-certificate" class="xliff"></a>

Em **Certificado raiz do professor**, escolha o botão Procurar para selecionar o certificado raiz de professor com a extensão .cer (DER ou codificado em Base64), ou .P7B (com ou sem cadeia completa).

#### Configurar o certificado PKCS#12 de professor
<a id="configure-teacher-pkcs12-certificate" class="xliff"></a>

Em **Certificado PKCS#12 de professor**, configure os seguintes valores:

- **Formato de nome da entidade** – o Intune prefixa automaticamente o nome comum de certificado com **leader**, para o certificado de professores, e **member**, para o certificado de alunos.
- **Autoridade de certificação** - uma AC (Autoridade de Certificação) Corporativa que é executada em uma edição Enterprise do Windows Server 2008 R2 ou posterior. Não há suporte para ACs autônomas. 
- **Nome da autoridade de certificação** - insira o nome do sua autoridade de certificação.
- **Nome do modelo de certificado** – insira o nome de um modelo de certificado que foi adicionado a uma CA emissora. 
- **Limite de renovação (%)** – Especifique o percentual do tempo de vida do certificado restante antes da renovação das solicitações de dispositivo do certificado.
- **Período de validade do certificado** – especifique a quantidade de tempo restante antes da expiração do certificado.
Você pode especificar um valor inferior ao período de validade do modelo de certificado especificado, mas não superior. Por exemplo, se o período de validade do certificado em um modelo de certificado for de dois anos, você pode especificar um valor de um ano, mas não de cinco anos. O valor também deve ser inferior ao período de validade restante do certificado da CA emissora.

Quando você terminar de configurar os certificados, clique em **OK**.

### Configurar certificados de aluno
<a id="configure-student-certificates" class="xliff"></a>

1.  Na folha **Educação**, escolha **Certificados de aluno**.
2.  Na folha **Certificados de aluno**, na lista de tipos **Certificados de dispositivo do aluno**, escolha **1:1**.

#### Configurar certificados raiz de aluno
<a id="configure-student-root-certificate" class="xliff"></a>

Em **Certificado raiz de aluno**, escolha o botão Procurar para selecionar o certificado raiz de aluno com a extensão .cer (DER ou codificado em Base64), ou .P7B (com ou sem cadeia completa).

#### Configurar certificado PKCS#12 de aluno
<a id="configure-student-pkcs12-certificate" class="xliff"></a>

Em **Certificado PKCS#12 de aluno**, configure os seguintes valores:

- **Formato de nome da entidade** – o Intune prefixa automaticamente o nome comum de certificado com **leader**, para o certificado de professores, e **member**, para o certificado de alunos.
- **Autoridade de certificação** - uma AC (Autoridade de Certificação) Corporativa que é executada em uma edição Enterprise do Windows Server 2008 R2 ou posterior. Não há suporte para ACs autônomas. 
- **Nome da autoridade de certificação** - insira o nome do sua autoridade de certificação.
- **Nome do modelo de certificado** – insira o nome de um modelo de certificado que foi adicionado a uma CA emissora. 
- **Limite de renovação (%)** – Especifique o percentual do tempo de vida do certificado restante antes da renovação das solicitações de dispositivo do certificado.
- **Período de validade do certificado** – especifique a quantidade de tempo restante antes da expiração do certificado.
Você pode especificar um valor inferior ao período de validade do modelo de certificado especificado, mas não superior. Por exemplo, se o período de validade do certificado em um modelo de certificado for de dois anos, você pode especificar um valor de um ano, mas não de cinco anos. O valor também deve ser inferior ao período de validade restante do certificado da CA emissora.

Ao terminar de configurar os certificados, clique em **OK**.

## Concluir
<a id="finish-up" class="xliff"></a>

1.  Na folha **Educação**, escolha OK.
2.  Na folha **Criar Perfil**, escolha **Criar**.
    
O perfil é criado e exibido na folha da lista de perfis.

Atribua o perfil aos dispositivos dos alunos, nos grupos de sala de aula criados durante a sincronização dos dados de estudante com o Microsoft Azure AD (confira [Como atribuir perfis do dispositivo](device-profile-assign.md)).

## Próximas etapas
<a id="next-steps" class="xliff"></a>

Agora, quando um professor usar o aplicativo Sala de Aula, ele terá controle total sobre os dispositivos dos alunos.

Para saber mais sobre o aplicativo Sala de Aula, veja [Ajuda do Sala de Aula](https://help.apple.com/classroom/ipad/2.0/) no site da Apple.

Se você quiser configurar dispositivos iPad compartilhado para alunos, consulte [Como definir as configurações educacionais do Intune para dispositivos iPad compartilhados](education-settings-configure-ios-shared.md).
