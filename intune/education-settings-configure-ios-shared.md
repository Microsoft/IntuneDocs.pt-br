---
title: "Configurações de dispositivo compartilhado do Intune para o aplicativo Classroom iOS"
titlesuffix: Azure portal
description: "Conheça as configurações do Intune que você pode usar para controlar as configurações do aplicativo Sala de aula em dispositivos iOS."
keywords: 
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1381a5ce-c743-40e9-8a10-4c218085bb5f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 044f3aaa81a2bb02662bec3d20ea51a2339b91a6
ms.sourcegitcommit: 2c7794848777e73d6a9502b4e1000f0b07ac96bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2018
---
# <a name="how-to-configure-intune-education-settings-for-shared-ipad-devices"></a>Como definir as configurações de educação do Intune para dispositivos iPad compartilhados

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

O Intune dá suporte ao aplicativo Sala de Aula do iOS que ajuda os professores a orientarem o aprendizado e a controlarem os dispositivos dos alunos na sala de aula. Além disso, para o aplicativo Classroom, a Apple dá suporte à capacidade dos dispositivos iPad dos alunos serem configurados de modo que vários alunos podem compartilhar um único dispositivo. Este documento orienta a alcançar essa meta com o Intune.

Para obter informações sobre como configurar dispositivos iPad dedicados (1:1) para usar o aplicativo Classroom, consulte [Como definir as configurações do Intune para o aplicativo Classroom iOS](education-settings-configure-ios.md).

## <a name="before-you-start"></a>Antes de começar

Os pré-requisitos para usar os recursos do iPad compartilhado são:

- Instale o [Apple School Manager](apple-school-manager-set-up-ios.md) e o [SDS (School Data Sync)](https://support.office.com/article/Apple-School-Manager-integration-with-Intune-for-Education-and-School-Data-Sync-974bd1f9-2c7a-45cb-9447-b58166108617).
- Como parte da instalação do Apple School Manager, configure as [IDs da Apple gerenciadas](http://help.apple.com/schoolmanager/#/tes78b477c81) para os alunos. [Saiba mais sobre as IDs da Apple gerenciadas](https://support.apple.com/HT205918).
- Crie um perfil de registro para os números de série de dispositivo sincronizados do Apple School Manager.

## <a name="step-1---import-your-school-data-into-azure-active-directory"></a>Etapa 1 - Importar os dados da escola para o Azure Active Directory

Use o SDS (School Data Sync) da Microsoft para importar registros escolares de um SIS (Sistema de Informações do Aluno) para o Azure Active Directory (Azure AD).
O SDS sincroniza as informações de seu SIS e as armazena no Azure AD. O Azure AD é um sistema de gerenciamento da Microsoft que ajuda você a organizar usuários e dispositivos. Depois, use esses dados para ajudar com o gerenciamento de seus alunos e salas de aula. [Saiba mais sobre como implantar o SDS](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91).

### <a name="how-to-import-data-using-sds"></a>Como importar dados usando o SDS

Importe as informações no SDS usando um dos seguintes métodos:

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
3. Na folha **Intune**, escolha **Configurar dispositivos**.
4. Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.
5. Na folha de perfis, escolha **Criar Perfil**.
6. Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de educação do iOS.
7. Na lista suspensa **Plataforma**, escolha **iOS**.
8. Na lista suspensa **Tipos de perfil**, escolha **Educação**.
9. Escolha **Configurações** > **Definir**.

Depois, você precisa de certificados para estabelecer uma relação de confiança entre os iPads de professores e alunos. Os certificados são usados para autenticar conexões perfeita e silenciosamente entre os dispositivos sem precisar inserir nomes de usuário e senhas.

>[!Important]
>Os certificados de professor e de aluno que você usa devem ser emitidos por ACs (autoridades de certificação) diferentes. Você deve criar duas novas CAs subordinadas conectadas à sua infraestrutura de certificados; uma para professores e outra para alunos.

Perfis de educação iOS dão suporte somente a certificados PFX. Não há suporte para certificados SCEP.

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
- **Nome do modelo de certificado** – Insira o nome de um modelo de certificado que foi adicionado a uma AC emissora.
- **Limite de renovação (%)** – Especifique o percentual do tempo de vida do certificado restante antes da renovação das solicitações de dispositivo do certificado.
- **Período de validade do certificado** – especifique a quantidade de tempo restante antes da expiração do certificado. Você pode especificar um valor inferior ao período de validade do modelo de certificado especificado, mas não superior. Por exemplo, se o período de validade do certificado em um modelo de certificado for de dois anos, você pode especificar um valor de um ano, mas não de cinco anos. O valor também deve ser inferior ao período de validade restante do certificado da CA emissora.

Quando você terminar de configurar os certificados de professor, clique em **OK**.

### <a name="configure-student-certificates"></a>Configurar certificados de aluno

1. Na **folha Educação**, escolha **Certificados de aluno**.
2. Na folha **Certificados de aluno**, na lista **Tipos de certificados de dispositivo de aluno**, escolha **iPad compartilhado**.

#### <a name="configure-student-root-certificate"></a>Configurar certificados raiz de aluno

Em **Certificado raiz do dispositivo**, escolha o botão Procurar para selecionar o certificado raiz de aluno com a extensão .cer (DER ou codificado em Base64) ou .P7B (com ou sem cadeia completa).

#### <a name="configure-device-pkcs12-certificate"></a>Configurar certificado de dispositivo PKCS#12

Em **Certificado PKCS#12 de aluno**, configure os seguintes valores:

- **Formato de nome da entidade** – O Intune prefixa automaticamente o nome comum do certificado com líder para o certificado de professor e membro para o certificado de dispositivo.
- **Autoridade de certificação** - uma AC (Autoridade de Certificação) Corporativa que é executada em uma edição Enterprise do Windows Server 2008 R2 ou posterior. Não há suporte para ACs autônomas.
- **Nome da autoridade de certificação** - insira o nome do sua autoridade de certificação.
- **Nome do modelo de certificado** – insira o nome de um modelo de certificado que foi adicionado a uma CA emissora.
- **Limite de renovação (%)** – Especifique o percentual do tempo de vida do certificado restante antes da renovação das solicitações de dispositivo do certificado.
- **Período de validade do certificado** – especifique a quantidade de tempo restante antes da expiração do certificado. Você pode especificar um valor inferior ao período de validade do modelo de certificado especificado, mas não superior. Por exemplo, se o período de validade do certificado em um modelo de certificado for de dois anos, você pode especificar um valor de um ano, mas não de cinco anos. O valor também deve ser inferior ao período de validade restante do certificado da CA emissora.

Ao terminar de configurar os certificados, clique em **OK**.

### <a name="complete-certificate-setup"></a>Concluir a instalação do certificado

1. Na folha **Educação**, escolha **OK**.
2. Na folha **Criar Perfil**, escolha **Criar**.

O perfil é criado e exibido na folha da lista de perfis.

## <a name="step-3---create-a-device-category"></a>Etapa 3 – Criar uma categoria de dispositivo

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Outros** > **Intune**.
3. Na folha **Intune**, escolha **Registro de dispositivo**.
4. Na folha **Registro – Visão Geral**, escolha **Categorias de Dispositivo**.
5. Na folha **Registro – Categorias de Dispositivo**, escolha **Criar**.
6. Na folha **Criar categoria de dispositivo**, insira um **Nome** e uma **Descrição** para a categoria.
7. Na folha **Criar categoria de dispositivo**, escolha **Criar**.

A categoria do dispositivo é criada na folha **Registro – Categorias de dispositivo**.

## <a name="step-4--create-a-dynamic-group"></a>Etapa 4 – Criar um grupo dinâmico

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Outros** > **Intune**.
3. Na folha **Intune**, escolha **Grupos**.
4. Na folha **Usuários e Grupos – Todos os Grupos**, escolha **Novo Grupo**.
5. Na folha **Grupo**, insira um **Nome** e uma **Descrição** para o grupo.
6. Na lista suspensa **Tipo de Associação**, escolha **Dispositivo Dinâmico**.
7. Escolha **Membros de dispositivo dinâmico** para criar as regras de associação.
8. Na folha **Regras de associação dinâmica**:
1. Selecione **deviceCategory** na lista suspensa **Onde adicionar dispositivos**.
2. Escolha **É igual a**
3. Insira a categoria do dispositivo que você criou na caixa de texto em branco
9. Na folha **Regras de associação dinâmica**, escolha **Adicionar consulta**.
10. Na folha **Grupo**, escolha **Criar**.

O grupo dinâmico é criado na folha **Usuários e Grupos – Todos os Grupos**.

## <a name="step-5--assign-a-device-to-a-category-carts"></a>Etapa 5 – Atribuir um dispositivo a uma categoria (Carrinhos)

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Outros** > **Intune**.
3. Na folha **Intune**, escolha **Dispositivos**.
4. Na folha **Dispositivos**, escolha **Todos os dispositivos**.
5. Na folha **Dispositivos – Todos os dispositivos**, escolha um dispositivo.
6. Na folha do dispositivo, escolha **Propriedades**.
7. Na folha de propriedades do dispositivo, digite a categoria do dispositivo na caixa de texto **Categoria de dispositivo**.
8. Na folha do dispositivo, escolha **Salvar**.

O dispositivo agora está associado à categoria de dispositivo. Repita esse processo para todos os dispositivos que você deseja associar à categoria de dispositivo que você criou.

## <a name="step-6--create-classroom-profiles"></a>Etapa 6 – Criar perfis de sala de aula

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Outros** > **Intune**.
3. Na folha **Intune**, escolha **Configurar dispositivos**.
4. Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis de Carrinho**.
5. Na folha de perfis, escolha **Criar Perfil**.
6. Na folha **Criar Associação**, insira um **Nome** e **Descrição**.
7. Escolha **Selecionar Classes** > **Configurar** para associar grupos ao Perfil do Carrinho.
8. Escolha as classes a serem incluídas no Perfil do Carrinho e escolha **Selecionar**. 
9. Escolha **Selecionar Carrinhos** > **Configurar** para associar grupos ao Perfil do Carrinho.
10. Escolha os grupos que devem ser incluídos no Perfil do Carrinho e escolha **Selecionar**.
11. Na folha **Criar Associação**, escolha **Salvar** para salvar o Perfil do Carrinho.

O perfil é criado e exibido na folha da lista de perfis.

## <a name="step-7---assign-the-cart-profile-to-classes"></a>Etapa 7 – Atribuir o Perfil do Carrinho às Classes

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Outros** > **Intune**.
3. Na folha **Intune**, escolha **Configurar dispositivos**.
4. Na folha **Configurações do Dispositivo**, escolha **Monitorar** > **Status de atribuição**.
5. Na folha **Status de atribuição**, selecione o **Perfil do Carrinho** que você criou.
6. Na folha **Perfil do Carrinho**, escolha **Atribuições** e, em seguida, em **Incluir**, escolha **Selecionar grupos a serem incluídos**.
7. Selecione as classes para as quais você deseja direcionar o perfil do carrinho (não selecione um grupo) e escolha **Selecionar**. 
8. Quando você terminar, escolha **Salvar**.

A atribuição é concluída e o Intune implanta o perfil do Classroom para os dispositivos de destino com base na atribuição de sala de aula.

## <a name="next-steps"></a>Próximas etapas

Agora os alunos podem compartilhar dispositivos entre si, escolher qualquer iPad em uma sala de aula, fazer logon com um PIN e personalizá-lo com seu conteúdo. Para obter mais informações sobre iPads compartilhados, consulte o [Site da Apple](https://www.apple.com/education/it/).
