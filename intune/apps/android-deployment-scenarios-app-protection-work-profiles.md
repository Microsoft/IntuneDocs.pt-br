---
title: Políticas de proteção de aplicativo e perfis de trabalho no Microsoft Intune – Azure | Microsoft Docs
description: Veja as diferenças e os prós e contras ao decidir usar políticas de proteção de aplicativo ou perfis de trabalho para dispositivos pessoais ou BYOD Android Enterprise no Microsoft Intune. Compare as diferenças e os recursos obtidos com as políticas de proteção de aplicativo sem registro (APP-WE) e os perfis de trabalho do Android Enterprise.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/13/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: d0b4f8d5124924d013e7ac131dafc947a95c7b65
ms.sourcegitcommit: 78cebd3571fed72a3a99e9d33770ef3d932ae8ca
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74059789"
---
# <a name="application-protection-policies-and-work-profiles-on-android-enterprise-devices-in-intune"></a>Políticas de proteção de aplicativo e de trabalho em dispositivos Android Enterprise no Intune

Em muitas organizações, os administradores enfrentam o desafio de proteger recursos e dados em dispositivos diferentes. Um desafio é proteger os recursos para usuários com dispositivos pessoais com Android Enterprise, também conhecido como BYOD (Traga seu próprio dispositivo). O Microsoft Intune dá suporte a dois cenários de implantação do Android BYOD (Traga seu próprio dispositivo):

- Políticas de proteção de aplicativo sem registro (APP-WE)
- Perfis de trabalho Android Enterprise

O APP-WE e os cenários de implantação do perfil de trabalho do Android incluem os seguintes recursos principais importantes para ambientes de BYOD:

1. **Proteção e segregação de dados gerenciados pela organização**: Ambas as soluções protegem dados da organização por meio da imposição de controles de DLP (prevenção contra perda de dados) em dados gerenciados pela organização. Essas proteções impedem vazamentos acidentais de dados protegidos, como o compartilhamento acidental por parte de um usuário final com um aplicativo ou conta pessoal. Elas também servem para garantir que um dispositivo acessando os dados esteja íntegro e não comprometido.

2. **Privacidade do usuário**: Perfis de trabalho APP-WE e do Android Enterprise separam o conteúdo de usuários finais no dispositivo dos dados gerenciados pelo administrador de MDM (gerenciamento de dispositivo móvel). Nos dois cenários, os administradores de TI impõem políticas, como autenticação apenas com PIN em aplicativos ou identidades gerenciadas pela organização. Os administradores de TI não consegue ler, acessar ou apagar os dados de propriedade ou controlados por usuários finais.

Sua escolha de perfis de trabalho APP-WE ou Android Enterprise para sua implantação BYOD depende de seus requisitos e das necessidades da empresa. O objetivo deste artigo é fornecer orientação para ajudar você a decidir.

## <a name="about-intune-app-protection-policies"></a>Sobre as políticas de proteção de aplicativo do Intune

APP (Políticas de proteção de aplicativo) do Intune são políticas de proteção de dados destinadas a usuários. As políticas aplicam a proteção contra perda de dados no nível do aplicativo. APP do Intune exige que os desenvolvedores de aplicativos habilitem recursos de APP nos aplicativos que eles criam.

Os aplicativos Android individuais são habilitados para APP de algumas maneiras:

1. **Integrado nativamente a aplicativos da Microsoft**: Aplicativos do Microsoft Office para Android, e uma seleção de outros aplicativos da Microsoft, vêm com APP do Intune. Esses aplicativos do Office, como Word, OneDrive, Outlook e assim por diante, não precisam de mais personalização para aplicar as políticas. Esses aplicativos podem ser instalados pelos usuários finais diretamente da Google Play Store.

2. **Integrado em compilações de aplicativo de desenvolvedores usando o SDK do Intune**: Os desenvolvedores de aplicativos podem integrar o SDK do Intune em seu código-fonte e recompilar seus aplicativos para dar suporte a recursos de política de APP do Intune.

3. **Encapsulado usando a ferramenta de disposição de aplicativo do Intune**: Alguns clientes compilam aplicativos Android (arquivo .APK) sem acesso ao código-fonte. Sem o código-fonte, o desenvolvedor não pode fazer a integração com o SDK do Intune. Sem o SDK, ele não pode habilitar seus aplicativos para políticas de APP. O desenvolvedor deve modificar ou recodificar o aplicativo para dar suporte a políticas de APP.

    Para ajudar, o Intune inclui a **Ferramenta de Encapsulamento da Aplicativo** para aplicativos existentes do Android (APKs) e cria um aplicativo que reconhece as políticas de APP.

    Para saber mais sobre essa ferramenta, confira [Preparar aplicativos de linha de negócios para políticas de proteção de aplicativo](../developer/apps-prepare-mobile-application-management.md).

Para ver uma lista de aplicativos habilitados com APP, confira [aplicativos gerenciados com um amplo conjunto de políticas de proteção de aplicativos móveis](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

## <a name="deployment-scenarios"></a>Cenários de implantação

Esta seção descreve as características importantes dos cenários de implantação de perfil de trabalho APP-WE e Android Enterprise.

### <a name="app-we"></a>APP-WE

Uma implantação APP-WE (políticas de proteção de aplicativo sem registro) define as políticas em aplicativos, não em dispositivos. Nesse cenário, os dispositivos normalmente não são registrados ou gerenciados por uma autoridade MDM, como o Intune. Para proteger aplicativos e o acesso aos dados organizacionais, os administradores usam aplicativos gerenciáveis por APP e aplicam políticas de proteção de dados nesses aplicativos.

Esse recurso aplica-se a:

- Android 4.4 e posterior

> [!TIP]
> Para saber mais, confira [O que são políticas de proteção de aplicativo?](app-protection-policy.md)

Os cenários APP-WE servem para usuários finais que desejam um volume de memória organizacional pequeno em seus dispositivos e não querem se registrar no MDM. Como administrador, você ainda precisa proteger seus dados. Esses dispositivos não são gerenciados. Por isso, as tarefas e os recursos de MDM, como WiFi, VPN de dispositivo e gerenciamento de certificados, não fazem parte deste cenário de implantação.

### <a name="android-enterprise-work-profiles"></a>Perfis de trabalho Android Enterprise

Os perfis de trabalho são o principal cenário de implantação do Android Enterprise e o único cenário destinado a casos de uso BYOD. O perfil de trabalho é uma partição separada criada no nível do sistema operacional Android e que pode ser gerenciada pelo Intune.

Esse recurso aplica-se a:

- Os dispositivos Android 5.0 e posteriores com os serviços Google Mobile

Um perfil de trabalho inclui os seguintes recursos:

- **Funcionalidade MDM tradicional**: Os principais recursos de MDM, como o gerenciamento de ciclo de vida do aplicativo usando o Google Play gerenciado, está disponível em qualquer cenário do Android Enterprise. O Google Play gerenciado fornece uma experiência robusta para instalar e atualizar aplicativos sem qualquer intervenção do usuário. A TI também pode enviar por push as definições de configuração de aplicativo para aplicativos organizacionais. Também não exige que os usuários finais permitam instalações de fontes desconhecidas. Outras atividades comuns de MDM, como a implantação de certificados, configuração de Wi-Fi/VPNs e configuração de senhas de dispositivos estão disponíveis com perfis de trabalho.

- **Limite de DLP no perfil de trabalho**: Como o APP-WE, a TI pode impor políticas de proteção de dados. Com um perfil de trabalho, as políticas de DLP são impostas no nível do perfil de trabalho, não no nível do aplicativo. Por exemplo, a proteção de copiar/colar é imposta pelas configurações de APP aplicadas a um aplicativo, ou imposta pelo perfil de trabalho. Quando o aplicativo é implantado em um perfil de trabalho, os administradores podem pausar a proteção copiar/colar no perfil de trabalho desativando essa política no nível APP.

## <a name="tips-to-optimize-the-work-profile-experience"></a>Dicas para otimizar a experiência do perfil de trabalho

### <a name="when-to-use-app-within-work-profiles"></a>Ao usar o APP em perfis de trabalho

O APP do Intune e perfis de trabalho são tecnologias complementares que podem ser usadas juntas ou separadamente. Em termos de arquitetura, as duas soluções impõem políticas em camadas diferentes: APP na camada individual do aplicativo, e o perfil de trabalho na camada de perfil. A implantação de aplicativos gerenciados com uma política de APP para um aplicativo em um perfil de trabalho é um cenário válido e com suporte. O uso de APP, perfis de trabalho ou uma combinação deles, depende de seus requisitos de DLP.

Os perfis de trabalho e APP complementam as próprias configurações, fornecendo cobertura adicional se um perfil não atender aos requisitos de proteção de dados da sua organização. Por exemplo, os perfis de trabalho não fornecem de forma nativa controles para restringir a gravação de um aplicativo em um local de armazenamento de nuvem não confiável. O APP inclui esse recurso. Você pode decidir que a DLP fornecida exclusivamente pelo perfil de trabalho é suficiente e optar por não usar o APP. Ou você pode exigir as proteções de uma combinação dos dois.

### <a name="suppress-app-policy-for-work-profiles"></a>Suprimir a política de APP para perfis de trabalho

Talvez seja necessário dar suporte a usuários individuais com vários dispositivos: dispositivos não gerenciados em um cenário de APP-WE e dispositivos gerenciados com perfis de trabalho.

Por exemplo, você exige que os usuários finais insiram um PIN ao abrir um aplicativo de trabalho. Dependendo do dispositivo, os recursos do PIN são manipulados pelo APP ou pelo perfil de trabalho. Para dispositivos APP-WE, o comportamento de PIN para inicialização é imposto pelo APP. Para dispositivos de perfil de trabalho, você pode usar um dispositivo ou PIN de perfil de trabalho imposto pelo sistema operacional. Para realizar esse cenário, defina as configurações de APP para que não seja aplicado *quando* um aplicativo for implantado em um perfil de trabalho. Se você não configurar dessa forma, o usuário final receberá a solicitação de um PIN do dispositivo, e novamente na camada APP.

### <a name="control-multi-identity-behavior-in-work-profiles"></a>Controlar o comportamento de várias identidade em perfis de trabalho

Os aplicativos do Office, como o Outlook e o OneDrive, têm o comportamento de "várias identidades". Dentro de uma instância do aplicativo, o usuário final pode adicionar conexões a várias contas distintas ou locais de armazenamento na nuvem. Dentro do aplicativo, os dados recuperados desses locais podem ser separados ou mesclados. E o usuário pode alternar o contexto entre identidades pessoais (user@outlook.com) e identidades organizacionais (user@contoso.com).

Ao usar perfis de trabalho, convém desabilitar esse comportamento de várias identidades. Quando você o desabilita, as instâncias com selo do aplicativo no perfil de trabalho só podem ser configuradas com uma identidade da organização. Use a definição de configuração de aplicativo Contas Permitidas para dar suporte a aplicativos Android do Office.

Para saber mais, confira [implantar as definições de configuração do aplicativo Outlook para iOS e Android](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune).

## <a name="when-to-use-intune-app"></a>Quando usar o APP do Intune

Há vários cenários de mobilidade empresarial nos quais usar o APP do Intune é a melhor recomendação.

### <a name="older-devices-running-android-44-51-are-being-used"></a>Os dispositivos mais antigos que executam o Android 4.4-5.1 estão sendo usados

Oficialmente, qualquer dispositivo Android 5.0 ou superior com os serviços do Google Mobile dá suporte a perfis de trabalho e é elegível para ser gerenciado dessa forma. No entanto, alguns dispositivos com Android 5.0 e 5.1 de alguns OEMs não dão suporte a perfis de trabalho.

Se estiver usando versões que não deem suporte a perfis de trabalho, e para garantir a DLP para dados da organização em dispositivos, use os recursos de APP do Intune.

### <a name="no-mdm-no-enrollment-google-services-are-unavailable"></a>Sem MDM, nenhum registro, os serviços do Google não estão disponíveis

Alguns clientes não querem qualquer forma de gerenciamento de dispositivos, incluindo o gerenciamento de perfil de trabalho, por motivos diferentes:

- Motivos legais e de responsabilidade
- Para manter a consistência da experiência do usuário
- O ambiente de dispositivo Android é altamente heterogêneo
- Não há conectividade com os serviços do Google, o que é necessário para o gerenciamento de perfis de trabalho.

Por exemplo, os clientes ou usuários na China não podem usar o gerenciamento de dispositivo Android, pois os serviços do Google são bloqueados. Nesse caso, use o APP do Intune para DLP.

## <a name="summary"></a>Resumo

Ao usar o Intune, os perfis de trabalho APP-WE e do Android Enterprise estão disponíveis para seu programa BYOD Android. A escolha de APP-WE ou de perfis de trabalho depende de seus requisitos de negócios e de uso. Resumindo, use perfis de trabalho se você precisar de atividades de MDM em dispositivos gerenciados, como implantação de certificado, push de aplicativo etc. Use o APP-WE se você não quiser ou não puder gerenciar dispositivos e estiver usando apenas aplicativos habilitados para APP do Intune.

## <a name="next-steps"></a>Próximas etapas
[Começar a usar as políticas de proteção de aplicativo](app-protection-policy.md) ou [registrar seus dispositivos](../enrollment/android-enroll.md).
