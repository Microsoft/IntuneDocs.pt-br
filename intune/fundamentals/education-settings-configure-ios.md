---
title: Configurações do Intune para o aplicativo Sala de aula do iOS
titleSuffix: Microsoft Intune
description: Conheça as configurações do Intune que você pode usar para controlar as configurações do aplicativo Sala de aula em dispositivos iOS.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 11/14/2019
ms.topic: archived
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 1381a5ce-c743-40e9-8a10-4c218085bb5f
ms.reviewer: derriw
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0dd9a97fdafff784bab2eae1d466855082fd397a
ms.sourcegitcommit: 737ad6c675deedfc6009f792023ff95981b06582
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2019
ms.locfileid: "74117831"
---
# <a name="how-to-configure-intune-settings-for-the-ios-classroom-app"></a>Como definir as configurações do Intune para o aplicativo Sala de Aula para iOS

> [!NOTE]
> Atualmente, o Intune não dá suporte à configuração do aplicativo sala de aula. Este artigo é aplicável somente para usuários com perfis de educação para iOS existentes no Intune.  

## <a name="introduction"></a>Introdução
[Sala de aula](https://itunes.apple.com/app/id1085319084) é um aplicativo que ajuda os professores a orientar o aprendizado e controlar os dispositivos dos alunos na sala de aula. Por exemplo, o aplicativo permite aos professores:

- Abrir aplicativos nos dispositivos de alunos
- Bloquear e desbloquear a tela do iPad
- Exibir a tela do iPad de um aluno
- Navegue os iPads dos alunos até um favorito ou capítulo de um livro
- Exibir a tela do iPad de um aluno em uma Apple TV

Para configurar a sala de aula em seu dispositivo, você precisará criar e configurar um perfil de dispositivo de educação no Intune iOS.

## <a name="before-you-start"></a>Antes de começar

Considere o seguinte antes de começar as configurações:

- Os iPads de professores e alunos devem ser registrados no Intune.
- Verifique se o aplicativo [Sala de Aula da Apple](https://itunes.apple.com/us/app/classroom/id1085319084?mt=8) está instalado no dispositivo do professor. Instale o aplicativo manualmente ou use o [Gerenciamento de aplicativo do Intune](../apps/app-management.md).
- Você deve configurar certificados para autenticar conexões entre os dispositivos de professores e de alunos (veja a Etapa 2, Criar e atribuir um perfil de Educação do iOS no Intune).
- Os iPads de professores e alunos devem estar na mesma rede Wi-Fi e ter o Bluetooth habilitado.
- O aplicativo Sala de Aula é executado em iPads supervisionados com o iOS 9.3 ou posterior.
- Nesta versão, o Intune dá suporte ao gerenciamento de um cenário 1:1 em que cada aluno tem seu próprio iPad dedicado.


## <a name="step-1---import-your-school-data-into-azure-active-directory"></a>Etapa 1 - Importar os dados da escola para o Azure Active Directory

Use o SDS (School Data Sync) da Microsoft para importar registros escolares de um SIS (Sistema de Informações do Aluno) para o Azure Active Directory (Azure AD).
O SDS sincroniza as informações de seu SIS e as armazena no Azure AD. O Azure AD é um sistema de gerenciamento da Microsoft que ajuda você a organizar usuários e dispositivos. Depois, use esses dados para ajudar com o gerenciamento de seus alunos e salas de aula. [Saiba mais sobre como implantar o SDS](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91).

### <a name="how-to-import-data-using-sds"></a>Como importar dados usando o SDS

Importe as informações no SDS usando um dos seguintes métodos:

- [Arquivos CSV](https://support.office.com/article/Follow-these-steps-71d5fe4a-aa51-4f35-9b53-348898a390a1) - exporte e compile manualmente os arquivos de valores separados por vírgulas (.csv)
- [API do PowerSchool](https://support.office.com/article/Follow-these-steps-851b5edc-558f-43a9-9122-b2d63458cb8f) - um provedor de SIS que simplifica a sincronização com o Azure AD
- [OneRoster](https://support.office.com/article/Follow-these-steps-f43cbb2a-b502-497d-a8b1-783dc05a57ab) - um formato CSV que você pode exportar e converter para sincronizar com o Azure AD

### <a name="find-out-more"></a>Saiba mais

- [Saiba mais sobre a experiência completa de sincronizar dados de escola locais com o Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)
- [Saiba mais sobre a sincronização do Microsoft School Data](https://sds.microsoft.com/)
- [Saiba mais sobre licenciamento no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)

## <a name="step-2---create-and-assign-an-ios-education-profile-in-intune"></a>Etapa 2 - Criar e atribuir um perfil de Educação do iOS no Intune

### <a name="configure-general-settings"></a>Definir as configurações gerais

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. No painel **Intune**, escolha **Configuração do dispositivo**.
2. No painel **Configuração do dispositivo**, na seção **Gerenciar**, escolha **Perfis**.
5. No painel de perfis, escolha **Criar perfil**.
6. No painel **Criar perfil**, insira um **Nome** e uma **Descrição** para o perfil de educação do iOS.
7. Na lista suspensa **Plataforma**, escolha **iOS**.
8. Na lista suspensa **Tipos de perfil**, escolha **Educação**.
9. Escolha **Configurações** > **Definir**.


Na próxima seção, você criará certificados para estabelecer uma relação de confiança entre os iPads de professores e alunos. Os certificados são usados para autenticar conexões perfeita e silenciosamente entre os dispositivos sem precisar inserir nomes de usuário e senhas.

>[!IMPORTANT]
>Os certificados de professores e alunos que você usa devem ser emitidos por CAs (autoridades de certificação) diferentes. Você deve criar duas novas CAs subordinadas conectadas à sua infraestrutura de certificados; uma para professores e outra para alunos.

Perfis de educação iOS dão suporte somente a certificados PFX. Não há suporte para certificados SCEP.

Os certificados criados devem oferecer suporte à autenticação de servidor e da autenticação de usuário.

### <a name="configure-teacher-certificates"></a>Configurar certificados de professor

No painel **Educação**, escolha **Certificados de professor**.

#### <a name="configure-teacher-root-certificate"></a>Configurar o certificado raiz do professor

Em **Certificado raiz do professor**, escolha o botão Procurar. Selecione o certificado raiz com:
- Extensão .cer (DER ou codificado na Base64) 
- Extensão .P7B (com ou sem cadeia completa)

#### <a name="configure-teacher-pkcs12-certificate"></a>Configurar o certificado PKCS#12 de professor

Em **Certificado PKCS#12 de professor**, configure os seguintes valores:

- **Nome da entidade** - o Intune automaticamente inclui prefixos de nomes comuns para certificados de professor com **líder**. Os nomes comuns para certificados de aluno são prefixados com **membro**.
- **Autoridade de certificação** - uma AC (Autoridade de Certificação) Corporativa que é executada em uma edição Enterprise do Windows Server 2008 R2 ou posterior. Não há suporte para ACs autônomas. 
- **Nome da autoridade de certificação** - insira o nome do sua autoridade de certificação.
- **Nome do modelo de certificado** – insira o nome de um modelo de certificado que foi adicionado a uma CA emissora. 
- **Limite de renovação (%)** – Especifique o percentual do tempo de vida do certificado restante antes da renovação das solicitações de dispositivo do certificado.
- **Período de validade do certificado** – especifique a quantidade de tempo restante antes da expiração do certificado.
Você pode especificar um valor inferior ao período de validade do modelo de certificado especificado, mas não superior. Por exemplo, se o período de validade do certificado em um modelo de certificado for de dois anos, você pode especificar um valor de um ano, mas não de cinco anos. O valor também deve ser inferior ao período de validade restante do certificado da CA emissora.

Ao terminar de configurar os certificados, clique em **OK**.

### <a name="configure-student-certificates"></a>Configurar certificados de aluno

1. No painel **Educação**, escolha **Certificados de aluno**.
2. No painel **Certificados de aluno**, na lista de tipos **Certificados de dispositivo do aluno**, escolha **1:1**.

#### <a name="configure-student-root-certificate"></a>Configurar certificados raiz de aluno

Em **Certificado raiz de aluno**, escolha o botão Procurar. Selecione o certificado raiz com:
- Extensão .cer (DER ou codificado na Base64) 
- Extensão .P7B (com ou sem cadeia completa)

#### <a name="configure-student-pkcs12-certificate"></a>Configurar certificado PKCS#12 de aluno

Em **Certificado PKCS#12 de aluno**, configure os seguintes valores:

- **Nome da entidade** - o Intune automaticamente inclui prefixos de nomes comuns para certificados de professor com **líder**. Os nomes comuns para certificados de aluno são prefixados com **membro**.
- **Autoridade de certificação** - uma AC (Autoridade de Certificação) Corporativa que é executada em uma edição Enterprise do Windows Server 2008 R2 ou posterior. Não há suporte para ACs autônomas. 
- **Nome da autoridade de certificação** - insira o nome do sua autoridade de certificação.
- **Nome do modelo de certificado** – insira o nome de um modelo de certificado que foi adicionado a uma CA emissora. 
- **Limite de renovação (%)** – Especifique o percentual do tempo de vida do certificado restante antes da renovação das solicitações de dispositivo do certificado.
- **Período de validade do certificado** – especifique a quantidade de tempo restante antes da expiração do certificado.
Você pode especificar um valor inferior ao período de validade do modelo de certificado especificado, mas não superior. Por exemplo, se o período de validade do certificado em um modelo de certificado for de dois anos, você pode especificar um valor de um ano, mas não de cinco anos. O valor também deve ser inferior ao período de validade restante do certificado da CA emissora.

Ao terminar de configurar os certificados, clique em **OK**.

## <a name="finish-up"></a>Concluir

1. No painel **Educação**, escolha OK.
2. No painel **Criar perfil**, escolha **Criar**.

O perfil é criado e aparece no painel da lista de perfis.

Atribua o perfil aos dispositivos dos alunos, nos grupos de sala de aula criados durante a sincronização dos dados de estudante com o Microsoft Azure AD (confira [Como atribuir perfis do dispositivo](../configuration/device-profile-assign.md)).

## <a name="next-steps"></a>Próximas etapas

Agora, quando um professor usar o aplicativo Sala de Aula, ele terá controle total sobre os dispositivos dos alunos.

Para saber mais sobre o aplicativo Sala de Aula, veja [Ajuda do Sala de Aula](https://help.apple.com/classroom/ipad/2.0/) no site da Apple.

Se você quiser configurar dispositivos iPad compartilhado para alunos, consulte [Como definir as configurações educacionais do Intune para dispositivos iPad compartilhados](education-settings-configure-ios-shared.md).
