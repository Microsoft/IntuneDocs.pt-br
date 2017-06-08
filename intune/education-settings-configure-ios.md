---
title: "Configurações do Intune para o aplicativo Sala de Aula para iOS | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Versão de visualização do Intune Azure: conheça as configurações do Intune que você pode usar para controlar as configurações do aplicativo Sala de Aula em dispositivos iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1381a5ce-c743-40e9-8a10-4c218085bb5f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 6f24636687291ff55686277c3f24b2774cfb32f4
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---


# <a name="how-to-configure-intune-settings-for-the-ios-classroom-app"></a>Como definir as configurações do Intune para o aplicativo Sala de Aula para iOS

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

## <a name="introduction"></a>Introdução
[Sala de aula](https://itunes.apple.com/app/id1085319084) é um aplicativo que ajuda os professores a orientar o aprendizado e controlar os dispositivos dos alunos na sala de aula. Por exemplo, com o aplicativo, um professor pode:

- Abrir aplicativos nos dispositivos de alunos
- Bloquear e desbloquear a tela do iPad
- Exibir a tela do iPad de um aluno
- Navegue os iPads dos alunos até um favorito ou capítulo de um livro
- Exibir a tela do iPad de um aluno em uma Apple TV

Use o perfil de dispositivo **Educação** do iOS no Intune e as informações neste tópico como auxílio para a configuração do aplicativo Sala de Aula e dos dispositivos nos quais você vai usá-lo.

## <a name="before-you-start"></a>Antes de começar

Considere o seguinte antes de começar as configurações:

- Os iPads de professores e alunos devem ser registrados no Intune
- Verifique se o aplicativo [Sala de Aula da Apple](https://itunes.apple.com/us/app/classroom/id1085319084?mt=8) está instalado no dispositivo do professor. Faça isso manualmente ou use [Gerenciamento de aplicativo do Intune](app-management.md).
- Você deve configurar certificados para autenticar conexões entre os dispositivos de professores e de alunos (consulte a Etapa 2)
- Os iPads de professores e alunos devem estar na mesma rede Wi-Fi e ter o Bluetooth habilitado
- O aplicativo Sala de Aula é executado em iPads supervisionados com o iOS 9.3 ou posterior
- Nesta versão, o Intune dá suporte ao gerenciamento de um cenário 1:1 em que cada aluno tem seu próprio iPad dedicado


## <a name="step-1---import-your-school-data-into-azure-active-directory"></a>Etapa 1 - Importar os dados da escola para o Azure Active Directory

Use o SDS (School Data Sync) da Microsoft para importar registros escolares de um SIS (Sistema de Informações do Aluno) para o Azure Active Directory (Azure AD).
O SDS sincroniza as informações de seu SIS e as armazena no Azure AD. O Azure AD é um sistema de gerenciamento da Microsoft que ajuda você a organizar usuários e dispositivos. Depois, use esses dados para ajudar com o gerenciamento de seus alunos e salas de aula. [Saiba mais sobre como implantar o SDS](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91).

### <a name="how-to-import-data-using-sds"></a>Como importar dados usando o SDS?

Importe informações no SDS usando uma das seguintes opções:

- [Arquivos CSV](https://support.office.com/article/Follow-these-steps-71d5fe4a-aa51-4f35-9b53-348898a390a1) - exporte e compile manualmente os arquivos de valores separados por vírgulas (.csv)
- [API do PowerSchool](https://support.office.com/article/Follow-these-steps-851b5edc-558f-43a9-9122-b2d63458cb8f) - um provedor de SIS que simplifica a sincronização com o Azure AD
- [API Inteligente](https://support.office.com/article/Follow-these-steps-f3d92fde-3ad0-48f3-80a1-1ad0ac4a3fae) - uma solução de gerenciamento de identidade sincronizada diretamente com o Azure AD
- [OneRoster](https://support.office.com/article/Follow-these-steps-f43cbb2a-b502-497d-a8b1-783dc05a57ab) - um formato CSV que você pode exportar e converter para sincronizar com o Azure AD

### <a name="find-out-more"></a>Saiba mais

- [Saiba mais sobre a experiência completa de sincronizar dados de escola locais com o Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)
- [Saiba mais sobre a sincronização do Microsoft School Data](https://sds.microsoft.com/)
- [Saiba mais sobre licenciamento no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)

## <a name="step-2---create-and-assign-an-ios-education-profile-in-intune"></a>Etapa 2 - Criar e atribuir um perfil de Educação do iOS no Intune

### <a name="configure-general-settings"></a>Definir as configurações gerais

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Outros** > **Intune**.
3.    Na folha **Intune**, escolha **Configurar dispositivos**.
4.    Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.
5.    Na folha de perfis, escolha **Criar Perfil**.
6.    Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de educação do iOS.
7.    Na lista suspensa **Plataforma**, escolha **iOS**.
8.    Na lista suspensa **Tipo de perfil**, escolha **Educação**.
9.    Escolha **Configurações** > **Definir**.


Depois, você precisa de certificados para estabelecer uma relação de confiança entre os iPads de professores e alunos. Os certificados são usados para autenticar conexões perfeita e silenciosamente entre os dispositivos sem precisar inserir nomes de usuário e senhas.

>[!IMPORTANT]
>Os certificados de professores e alunos que você usa devem ser emitidos por CAs (autoridades de certificação) diferentes. Você deve criar duas novas CAs subordinadas conectadas à sua infraestrutura de certificados; uma para professores e outra para alunos.

Os perfis de educação do iOS oferecem suporte apenas aos certificados PFX, e não há suporte para certificados SCEP.

Os certificados que você cria devem oferecer suporte à autenticação de servidor, além da autenticação de usuário.

### <a name="configure-teacher-certificates"></a>Configurar certificados de professor

Na folha **Educação**, escolha **Certificados de professor**.

#### <a name="configure-teacher-root-certificate"></a>Configurar o certificado raiz do professor

Em **Certificado raiz do professor**, escolha o botão Procurar para selecionar o certificado raiz de professor com a extensão .cer (DER ou codificado em Base64), ou .P7B (com ou sem cadeia completa).

#### <a name="configure-teacher-pkcs12-certificate"></a>Configurar o certificado PKCS#12 de professor

Em **Certificado PKCS#12 de professor**, configure os seguintes valores:

- **Formato de nome da entidade** – o Intune prefixa automaticamente o nome comum de certificado com **leader**, para o certificado de professores, e **member**, para o certificado de alunos.
- **Autoridade de certificação** - uma AC (Autoridade de Certificação) Corporativa que é executada em uma edição Enterprise do Windows Server 2008 R2 ou posterior. Não há suporte para ACs autônomas. 
- **Nome da autoridade de certificação** - insira o nome do sua autoridade de certificação.
- **Nome do modelo de certificado** – insira o nome de um modelo de certificado que foi adicionado a uma CA emissora. 
- **Limite de renovação (%)** – Especifique o percentual do tempo de vida do certificado restante antes da renovação das solicitações de dispositivo do certificado.
- **Período de validade do certificado** – especifique a quantidade de tempo restante antes da expiração do certificado.
Você pode especificar um valor inferior ao período de validade do modelo de certificado especificado, mas não superior. Por exemplo, se o período de validade do certificado em um modelo de certificado for de dois anos, você pode especificar um valor de um ano, mas não de cinco anos. O valor também deve ser inferior ao período de validade restante do certificado da CA emissora.

Quando você terminar de configurar os certificados, clique em **OK**.

### <a name="configure-student-certificates"></a>Configurar certificados de aluno

1.    Na folha **Educação**, escolha **Certificados de aluno**.
2.    Na folha **Certificados de aluno**, na lista de tipos **Certificados de dispositivo do aluno**, escolha **1:1**.

#### <a name="configure-student-root-certificate"></a>Configurar certificados raiz de aluno

Em **Certificado raiz de aluno**, escolha o botão Procurar para selecionar o certificado raiz de aluno com a extensão .cer (DER ou codificado em Base64), ou .P7B (com ou sem cadeia completa).

#### <a name="configure-student-pkcs12-certificate"></a>Configurar certificado PKCS#12 de aluno

Em **Certificado PKCS#12 de aluno**, configure os seguintes valores:

- **Formato de nome da entidade** – o Intune prefixa automaticamente o nome comum de certificado com **leader**, para o certificado de professores, e **member**, para o certificado de alunos.
- **Autoridade de certificação** - uma AC (Autoridade de Certificação) Corporativa que é executada em uma edição Enterprise do Windows Server 2008 R2 ou posterior. Não há suporte para ACs autônomas. 
- **Nome da autoridade de certificação** - insira o nome do sua autoridade de certificação.
- **Nome do modelo de certificado** – insira o nome de um modelo de certificado que foi adicionado a uma CA emissora. 
- **Limite de renovação (%)** – Especifique o percentual do tempo de vida do certificado restante antes da renovação das solicitações de dispositivo do certificado.
- **Período de validade do certificado** – especifique a quantidade de tempo restante antes da expiração do certificado.
Você pode especificar um valor inferior ao período de validade do modelo de certificado especificado, mas não superior. Por exemplo, se o período de validade do certificado em um modelo de certificado for de dois anos, você pode especificar um valor de um ano, mas não de cinco anos. O valor também deve ser inferior ao período de validade restante do certificado da CA emissora.

Ao terminar de configurar os certificados, clique em **OK**.

## <a name="finish-up"></a>Concluir

1.    Na folha **Educação**, escolha OK.
2.    Na folha **Criar Perfil**, escolha **Criar**.
    
O perfil será criado e aparecerá na folha da lista de perfis.

Atribua o perfil aos dispositivos dos alunos, nos grupos de sala de aula criados durante a sincronização dos dados de estudante com o Microsoft Azure AD (confira [Como atribuir perfis do dispositivo](device-profile-assign.md)).

## <a name="next-steps"></a>Próximas etapas

Agora, quando um professor usar o aplicativo Sala de Aula, ele terá controle total sobre os dispositivos dos alunos.

Para saber mais sobre o aplicativo Sala de Aula, veja [Ajuda do Sala de Aula](https://help.apple.com/classroom/ipad/2.0/) no site da Apple.
