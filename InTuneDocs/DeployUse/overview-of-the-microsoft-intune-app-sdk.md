---
# required metadata

title: Visão geral do SDK do Microsoft Intune App | Microsoft Intune
description:
keywords:
author: Msmbaldwin
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ef1751bb-3a2f-4662-a922-38c076869eb3

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Visão geral do SDK de Aplicativos do Microsoft Intune
O SDK do Intune App está disponível para as plataformas Android e iOS, e habilita os recursos de gerenciamento de aplicativos móveis com o Microsoft Intune. Além disso, buscamos sempre reduzir a quantidade de alterações de código necessárias por parte do desenvolvedor. Você descobrirá que é possível habilitar a maioria dos recursos do SDK sem alterar o comportamento do seu aplicativo. Para o usuário final avançado e a experiência do administrador de TI, você pode usar nossas APIs para personalizar o comportamento do seu aplicativo para recursos que exigem a participação do seu aplicativo. 

Depois de habilitar seu aplicativo, os administradores de TI podem implantar políticas para aplicativos gerenciados pelo Intune e aproveitar esses recursos para proteger seus dados corporativos.

# Recursos
## Controlar a capacidade dos usuários de mover documentos corporativos
Os administradores de TI podem controlar a realocação de arquivos de documentos corporativos em aplicativos gerenciados pelo Intune. Por exemplo, eles podem implantar uma política que desabilita que aplicativos de backup de arquivo realizem backup de dados corporativos para a nuvem.  

## Configurar restrições da área de transferência
Os administradores de TI podem configurar o comportamento da área de transferência em aplicativos gerenciados pelo Intune. Por exemplo, eles podem implantar uma política para que os usuários finais não usem a área de transferência para recortar/copiar de um aplicativo gerenciado pelo Intune e colem em um aplicativo não gerenciado.

## Configurar restrições de captura de tela
Os administradores de TI podem impedir que os usuários realizem captura de tela se um aplicativo gerenciado pelo Intune for exibido. Aplicar essa restrição impede a captura e a divulgação do conteúdo corporativo confidencial. Esse recurso só está disponível para dispositivos Android. 

## Impor criptografia em dados salvos
Os administradores de TI podem impor uma política que garante que os dados salvos no dispositivo pelo aplicativo sejam criptografados.

## Apagar dados corporativos remotamente
Os administradores de TI podem apagar remotamente dados corporativos de um aplicativo gerenciado pelo Intune quando o registro do dispositivo é cancelado no Microsoft Intune. Esse recurso é baseado em identidade e excluirá apenas os arquivos relacionados à identidade corporativa do usuário final. Para fazer isso, o recurso requer a participação do aplicativo. O aplicativo pode especificar a identidade para o qual o apagamento deve ocorrer com base nas configurações do usuário. Na ausência dessas configurações de usuário especificadas no aplicativo, o comportamento padrão é apagar o diretório do aplicativo e notificar o usuário final que o acesso aos recursos da empresa foi removido. 

## Impor o uso de um navegador gerenciado
Os administradores de TI podem impor o uso de um navegador gerenciado ao abrir links em aplicativos gerenciados pelo Intune. Usar o navegador gerenciado pelo Microsoft Intune ajuda a garantir que os links que aparecem nos emails (que estão em um cliente de email gerenciado pelo Intune) sejam mantidos dentro do domínio dos aplicativos gerenciados pelo Intune.

## Impor uma política PIN
Os administradores de TI podem impor uma política PIN quando um aplicativo gerenciado pelo Intune é iniciado. Essa política ajuda a garantir que os usuários finais que registraram seus dispositivos com o Microsoft Intune são as mesmas pessoas que estão abrindo os aplicativos. Quando os usuários finais configuram seus PINs, o SDK do Intune App usa o Active Directory do Azure para verificar as credenciais de usuários finais em relação às credenciais de registro do dispositivo. 

## Os usuários devem inserir credenciais para poderem abrir os aplicativos
Os administradores de TI podem exigir que os usuários digitem suas credenciais para poderem abrir um aplicativo gerenciado pelo Intune. O SDK do Intune App usa o Active Directory do Azure para fornecer uma experiência de logon único, em que as credenciais, uma vez inseridas, são reutilizadas para logons subsequentes. Também há suporte para autenticação de soluções de gerenciamento de identidade [federada com o Azure Active Directory](https://msdn.microsoft.com/en-us/library/azure/jj679342.aspx). 

## Verificar a integridade e conformidade do dispositivo
Os administradores de TI podem realizar uma verificação de integridade do dispositivo e sua conformidade com políticas corporativas antes que os usuários finais possam acessar aplicativos gerenciados pelo Intune. Na plataforma iOS, esta política verifica se o dispositivo foi desbloqueado com jailbreak. Na plataforma Android, esta política verifica se o dispositivo apresenta raiz.  




<!--HONumber=May16_HO1-->


