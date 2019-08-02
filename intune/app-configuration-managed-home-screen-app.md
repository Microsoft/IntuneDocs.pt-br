---
title: Configurar o aplicativo de Tela Inicial Gerenciada da Microsoft
titleSuffix: Microsoft Intune
description: Saiba como configurar o aplicativo de Tela Inicial Gerenciada da Microsoft.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/24/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 865c7f03-f525-4dfa-b3a8-d088a9106502
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 758230d3d2f1dd1cb42532cce9fe1ff530000a16
ms.sourcegitcommit: d2ac912b834c4840de9cc92ba1815b6ecfbfb52b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/25/2019
ms.locfileid: "68482853"
---
# <a name="configure-the-microsoft-managed-home-screen-app-for-android-enterprise"></a>Aplicativo de Tela Inicial Gerenciada da Microsoft para o Android Enterprise

A Tela Inicial Gerenciada é o aplicativo usado para dispositivos corporativos de Android Enterprise dedicados registrados por meio do Intune e em execução no modo de quiosque de vários aplicativos. Para esses dispositivos, a Tela Inicial Gerenciada atua como inicializador para que outros aplicativos aprovados sejam executados sobre ele. A Tela Inicial Gerenciada fornece aos administradores de TI a capacidade de personalizar seus dispositivos e restringir os recursos que o usuário final pode acessar. 

## <a name="when-to-configure-the-microsoft-managed-home-screen-app"></a>Quando configurar o aplicativo de Tela Inicial Gerenciada da Microsoft

Normalmente, se as configurações estiverem disponíveis para você por meio da configuração de dispositivo, defina as configurações lá. Fazer isso lhe poupará tempo, minimizará os erros e dará a você uma melhor experiência de suporte do Intune. No entanto, algumas das configurações da Tela Inicial Gerenciada só estão disponíveis atualmente por meio da folha **Políticas de configuração de aplicativos** no console do Intune. Use este documento para saber como definir as configurações diferentes usando o designer de configuração ou um script JSON. 

> [!NOTE]
> No momento, é possível e aconselhável permitir aplicativos e links da Web fixados por meio de **Aplicativos Cliente** e da **Configuração do Dispositivo**. Para obter a lista completa das configurações disponíveis na **Configuração do dispositivo** que afetam a Tela Inicial Gerenciada, confira as [Configurações do dispositivo dedicado](device-restrictions-android-for-work.md#dedicated-device-settings).  

Primeiro, navegue até o console do Intune no portal do Azure e acesse **Aplicativos cliente** > **Políticas de configuração de aplicativos**. Adicione uma política de configuração para **Dispositivos gerenciados** em execução no **Android** e escolha **Tela Inicial Gerenciada** como o aplicativo associado. Clique em **Definições de configuração** para definir as diferentes configurações de Tela Inicial Gerenciada disponíveis. 

## <a name="choosing-a-configuration-settings-format"></a>Como escolher um formato de definições de configuração

Há dois métodos que você pode usar para definir as configurações da Tela Inicial Gerenciada:

- O **Designer de configuração** permite que você defina as configurações com uma interface do usuário fácil de usar, que permite ativar e desativar recursos e definir valores. Nesse método, há algumas chaves de configuração desabilitadas com o tipo de valor `BundleArray`. Essas chaves de configuração só podem ser configuradas inserindo dados JSON. 
- **Dados JSON** permitem que você defina todas as chaves de configuração possíveis usando um script JSON. 

Se adicionar propriedades com o designer de configuração, você poderá converter automaticamente essas propriedades em JSON, selecionando **Inserir dados JSON** na lista suspensa **Formato das configurações**.

![Captura de tela das opções de formato das configurações](./media/app-configuration-managed-home-screen-app/app-configuration-managed-home-screen-app_01.png)

## <a name="using-configuration-designer"></a>Como usar o designer de configuração

O designer de configuração permite que você selecione configurações preenchidas previamente e seus valores associados. 

![Captura de tela de configurações adicionais](./media/app-configuration-managed-home-screen-app/app-configuration-managed-home-screen-app_02.png)

A tabela a seguir lista as chaves de configuração, tipos de valor, valores padrão e descrições disponíveis na Tela Inicial Gerenciada. A descrição fornece o comportamento esperado do dispositivo com base nos valores selecionados. Chaves de configuração que estão desabilitadas no designer de configuração não estão listadas na tabela.

| Chave de configuração | Tipo de valor | Valor padrão | Descrição |
|---------------------------------------------------------------------------------------------------------------------------|-------------|------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Definir tamanho da grade | cadeia de caracteres | Automático | Permite que você defina o tamanho da grade para que aplicativos sejam posicionados na Tela Inicial Gerenciada. Você pode definir o número de linhas e colunas de aplicativo para definir o tamanho da grade no seguinte formato: `columns;rows`. Se você definir o tamanho da grade, o número máximo de aplicativos que serão mostrados em uma linha na tela inicial será o número de linhas definido por você e o número máximo de aplicativos que serão mostrados em uma coluna na tela inicial será o número de colunas que você definir. |
| Enable Screen Header | bool | TRUE | Habilita o cabeçalho superior para diferentes exibições que a tela inicial gerenciada oferece, tais como o feed ou cartões de feed. Se você habilitar essa configuração, os usuários do dispositivo verão o cabeçalho. |
| Habilitar a barra de status do dispositivo | bool | TRUE | Habilita a barra de status na tela inicial (barra superior que exibe as conexões atuais, tais como Wi-Fi etc.). Se você habilitar essa chave de configuração, o usuário final será capaz de ver os ícones exibidos nas barras de status que representam conexões e aplicativos ativos. |
| Enable notifications badge | bool | FALSE | Habilita o selo de notificação para ícones de aplicativo que mostra o número de novas notificações no aplicativo. Se você habilitar essa configuração, os usuários finais verão selos de notificação em aplicativos que têm notificações não lidas. Se você mantiver essa chave de configuração desabilitada, o usuário final não verá nenhuma notificação com selo para aplicativos que possam ter notificações não lidas. |
| Lock Home Screen | bool | TRUE | Remove a capacidade de mover os ícones do aplicativo na tela inicial do usuário final. Se você habilitar essa chave de configuração, os ícones de aplicativo na tela inicial serão bloqueados e o usuário final não será capaz de arrastar e soltar para posições de grade diferentes da tela inicial. Se transformado em `false`, os usuários finais poderão mover ícones de weblink e de aplicativo da Tela Inicial Gerenciada.  |
| Set device wall paper | cadeia de caracteres | Padrão | Permite que você defina um papel de parede de sua preferência, inserindo a URL da imagem que você deseja definir como um papel de parede. |
| Set app icon size | integer | 2 | Permite que você defina o tamanho do ícone para aplicativos exibidos na tela inicial. Você pode escolher os valores a seguir nessa configuração para diferentes tamanhos – 0 (menor), 1 (pequeno), 2 (regular), 3 (grande) e 4 (maior). |
| Set app folder icon | integer | 0 | Permite que você defina a aparência das pastas de aplicativo na tela inicial. Você pode escolher a aparência entre os seguintes valores: Quadrado Escuro(0); Círculo Escuro(1); Quadrado Claro(2); Círculo Claro(3). |
| Enable gestures | bool | FALSE | Habilite a capacidade do usuário final de atribuir ações para gestos diferentes, tais como passar o dedo para cima e para baixo. Se você desabilitar essa chave de configuração, os usuários finais só poderão passar o dedo para a direita se houver uma segunda página e voltar para a home page. |
| Enable vertical scrolling | bool | FALSE | Habilita a rolagem vertical na tela inicial gerenciada. Se você habilitar essa chave de configuração, o usuário final só será capaz de navegar até diferentes páginas verticalmente e não mais passando o dedo horizontalmente. |
| Set home screen theme | cadeia de caracteres | Theme.Light.Blue | Permite que você escolha o tema para a tela inicial de um conjunto predefinido de temas com cores diferentes. Você pode escolher os temas a seguir, inserindo o valor da cadeia de caracteres no formato a seguir.   Theme.Light.Green. Em que light pode ser substituído por dark para um tema escuro e Green pode ser substituído por Blue, Yellow, Pink, Red, Orange e Purple (azul, amarelo, rosa, vermelho, laranja e roxo, respectivamente). |
| Enable dock | bool | FALSE | Habilita a seção de encaixe de aplicativos na parte inferior da tela inicial com aplicativos persistentes exibidos e um ponto de entrada para todos os aplicativos instalados. Se você habilitar essa chave de configuração, o usuário final será capaz de acessar os aplicativos no painel de encaixe e acessar a seção Todos os aplicativos para ir para a lista com todos os aplicativos instalados nos dispositivos, independentemente de estarem ou não na lista de permissões. |
| Set screen orientation | integer | 1 | Permite que você defina a orientação da tela inicial para o modo retrato, paisagem ou permitir rotação automática. Você pode definir a orientação digitando os valores 1 (retrato), 2 (paisagem) ou 3 (rotação automática). |
| Enable home screen feed | bool | FALSE | Habilita o feed da tela inicial, que pode ser visto passando o dedo para esquerda da tela inicial. Este feed exibe um tipo diferente de conteúdo, por exemplo, notícias, calendário, aplicativos usados frequentemente, cartão de Assistente de voz Cortana etc. Se você habilitar essa opção, o usuário final será capaz de navegar para o feed passando o dedo para a esquerda na tela inicial. |
| Enable overview mode | bool | FALSE | Permite que os usuários finais adicionem ou removam páginas diferentes na tela inicial que podem ser acessadas passando o dedo para a direita na tela padrão. Se você habilitar essa opção, o usuário final será capaz de adicionar páginas à direita da página padrão da tela inicial, também podendo alterar a página padrão e acessar as configurações na Tela Inicial Gerenciada. |
| Enable device telemetry | bool | FALSE | Habilita toda a telemetria que está sendo capturada para a tela inicial gerenciada. Se você habilitar essa opção, a Microsoft poderá capturar a telemetria de uso do dispositivo, tal como o número de vezes que um determinado aplicativo é iniciado neste dispositivo. |
| Definir aplicativos para a lista de permissões | bundleArray | FALSE | Permite definir o conjunto de aplicativos visíveis na tela inicial entre os aplicativos instalados no dispositivo. Você pode definir os aplicativos inserindo o nome do pacote dos aplicativos que você deseja tornar visíveis, por exemplo, com.microsoft.emmx torna as configurações acessíveis na tela inicial. Os aplicativos da lista de permissões nesta seção já devem estar instalados no dispositivo para que fiquem visíveis na tela inicial. |
| Set pinned web links | bundleArray | FALSE | Permite que você fixe sites como ícones de início rápido na tela inicial. Com essa configuração, você pode definir a URL e adicioná-la à tela inicial para o usuário final iniciar no navegador com um único toque. |
| Enable search bar | bool | FALSE | Habilita a barra de pesquisa na tela inicial. Se você habilitar essa opção, os usuários do dispositivo verão a barra de pesquisa na tela inicial, que poderão usar para pesquisar tudo o que desejam na Web. |
| Disable settings app | bool | FALSE | Desabilita a página de configurações da Tela Inicial Gerenciada. Se você desabilitar essa opção, o usuário final do dispositivo não poderá acessar as configurações da Tela Inicial Gerenciada. |
| Enable screen saver | bool | FALSE | Para habilitar o modo de proteção de tela ou não. Se definido como true, você poderá configurar **screen_saver_image**, **screen_saver_show_time**, **inactive_time_to_show_screen_saver** e **media_detect_ screen_saver**. |
| Screen saver image | cadeia de caracteres |   | Defina a URL da imagem da proteção de tela. Se nenhuma URL for definida, os dispositivos mostrarão a imagem da proteção de tela padrão quando a proteção de tela for ativada. A imagem padrão mostra o ícone do aplicativo Tela Inicial Gerenciada.  |
| Screen saver show time | integer | 0 | Dá a opção de definir o tempo em segundos pelo qual a proteção de tela será exibida pelo dispositivo durante o modo de proteção de tela. Se definido como 0, a proteção de tela será exibida no modo de proteção de tela por tempo indeterminado até que o dispositivo se torne ativo.  |
| Inactive time to enable screen saver | integer | 30 | O número de segundos que o dispositivo fica inativo antes de disparar a proteção de tela. Se definido como 0, o dispositivo nunca entrará no modo de proteção de tela. |
| Media detect before showing screen saver | bool | TRUE | Escolha se a tela do dispositivo deverá mostrar a proteção de tela quando houver áudio/vídeo em execução no dispositivo. Se definido como true, o dispositivo não iniciará o protetor de tela ao reproduzir áudio/vídeo, independentemente do valor em **inactive_time_to_show_scree_saver**. Se definido como false, a tela exibirá a proteção de tela de acordo com o valor definido em **inactive_time_to_show_screen_saver**.   |
| Enable virtual home button | bool | FALSE | Defina essa configuração para `True` a fim de permitir que o usuário final tenha acesso a um botão início da Tela Inicial Gerenciada que retornará o usuário a essa tela, saindo da tarefa atual em que ele esteja.  |
| Type of virtual home button | cadeia de caracteres | swipe_up | Use **swipe_up** para acessar o botão início com um gesto de passar o dedo para cima. Use **float** para acessar um botão início permanente e persistente que pode ser movido pela tela pelo usuário final. |
| Battery and Signal Strength indicator bar | bool | verdadeiro  | Definir essa configuração para `True` mostra a barra do indicador de bateria e de força do sinal. |
| Exit lock task mode password | cadeia de caracteres |   | Insira um código de 4 a 6 dígitos a usar para sair temporariamente do modo de bloqueio de tarefas para solução de problemas. |
| Mostrar configuração de Wi-Fi | bool | FALSE | Definir essa configuração para `True` permite ao usuário final ativar ou desativar o Wi-Fi ou se conectar a diferentes redes Wi-Fi.  |
| Show Bluetooth setting | bool | FALSE | Definir essa configuração para `True` permite ao usuário final ativar ou desativar o Bluetooth ou se conectar a diferentes dispositivos com capacidade para Bluetooth.   |
| Aplicativos na pasta são ordenados por nome | bool | TRUE | Definir essa configuração como `False` permite que os itens em uma pasta sejam exibidos na ordem especificada. Caso contrário, eles serão exibidos na pasta em ordem alfabética.   |
| Ordem de aplicativos habilitada | bool | FALSE | Definir essa configuração como `True` permite habilitar a capacidade de definir a ordem dos aplicativos, weblinks e pastas na Tela Inicial Gerenciada. Quando habilitada, define a ordem com **app_order**. O usuário final pode ativar ou desativar o Bluetooth e pode se conectar a diferentes dispositivos com capacidade para Bluetooth.   |
| Ordem dos aplicativos | bundleArray | FALSE | Permite especificar a ordem dos aplicativos, weblinks e pastas na Tela Inicial Gerenciada. Para usar essa configuração, a opção **Bloquear Tela Inicial** deve estar habilitada, **Definir tamanho da grade** deve estar definida e a **Ordem dos aplicativos habilitada** deve estar definida como `True`.   |

## <a name="enter-json-data"></a>Inserir dados JSON

Insira dados JSON para configurar todas as configurações disponíveis para a Tela Inicial Gerenciada, bem como as configurações desabilitadas no **Designer de configuração**.

![Captura de tela de dados JSON adicionados](./media/app-configuration-managed-home-screen-app/app-configuration-managed-home-screen-app_03.png)

Além da lista de definições configuráveis listadas na tabela do **Designer de configuração** (acima), a tabela a seguir fornece as chaves de configuração que você só pode configurar por meio de dados JSON.

|    Chave de configuração    |    Tipo de valor    |    Valor padrão    |    Descrição    |
|-------------------------------------------------|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Definir aplicativos para a lista de permissões    |    bundleArray    | <img alt="JSON - Example 1" src="./media/app-configuration-managed-home-screen-app/defaultvaluejson01.png" width="300"> |    Permite que você defina o conjunto de aplicativos visíveis na tela inicial entre os aplicativos instalados no dispositivo. Você pode definir os aplicativos inserindo o nome do pacote do aplicativo dos aplicativos que você deseja tornar visíveis, por exemplo, com.android.settings tornaria as configurações acessíveis na tela inicial. Os aplicativos da lista de permissões nesta seção já devem estar instalados no dispositivo para que fiquem visíveis na tela inicial.    |
|    Set pinned web links    |    bundleArray    | <img alt="JSON - Example 2" src="./media/app-configuration-managed-home-screen-app/defaultvaluejson02.png" width="300"> |    Permite que você fixe sites como ícones de início rápido na tela inicial. Com essa configuração, você pode definir a URL e adicioná-la à tela inicial para o usuário final iniciar no navegador com um único toque.    |
|    Create Managed Folder for grouping apps    |    bundleArray    | <img alt="JSON - Example 3" src="./media/app-configuration-managed-home-screen-app/defaultvaluejson03.png" width="300"> |    Permite que você crie e nomeie pastas e agrupe aplicativos dentro dessas pastas. Os usuários finais não poderão mover pastas, renomear as pastas ou mover os aplicativos dentro das pastas.   As pastas serão exibidas na ordem criada e os aplicativos dentro das pastas serão exibidos em ordem alfabética.         Observação: todos os aplicativos que você deseja agrupar em pastas devem ser atribuídos como obrigatórios para o dispositivo e devem ter sido adicionados à Tela Inicial Gerenciada.     |

Este é um exemplo de script JSON com todas as chaves de configuração disponíveis incluídas:

```json
{
    "kind": "androidenterprise#managedConfiguration",
    "productId": "com.microsoft.launcher.enterprise",
    "managedProperty": [
        {
            "key": "keep_page_header",
            "valueBool": true
        },
        {
            "key": "keep_status_bar",
            "valueBool": true
        },
        {
            "key": "show_notification_badge",
            "valueBool": false
        },
        {
            "key": "lock_home_screen",
            "valueBool": true
        },
        {
            "key": "wallpaper",
            "valueString": "default"
        },
        {
            "key": "icon_size",
            "valueInteger": 2
        },
        {
            "key": "app_folder_icon",
            "valueInteger": 0
        },
        {
            "key": "gesture_on",
            "valueBool": false
        },
        {
            "key": "vertical_scrolling",
            "valueBool": false
        },
        {
            "key": "theme",
            "valueString": "Theme.Light.Blue"
        },
        {
            "key": "dock_enable",
            "valueBool": false
        },
        {
            "key": "screen_orientation",
            "valueInteger": 1
        },
        {
            "key": "feed_enable",
            "valueBool": false
        },
        {
            "key": "allow_overview_mode",
            "valueBool": false
        },
        {
            "key": "enable_telemetry",
            "valueBool": false
        },
        {
            "key": "applications",
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "package",
                            "valueString": “app package name here”
                        }
                    ]
                }
            ]
        },
        {
            "key": "weblinks",
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "link",
                            "valueString": “link here”
                        },
                        {
                            "key": "label",
                            "valueString": “weblink label here”
                        }
                    ]
                }
            ]
        },
        {
            "key": "search_bar",
            "valueBool": false
        },
        {
            "key": "hide_settings",
            "valueBool": false
        },
        {
            "key": "show_virtual_home",
            "valueBool": false
        },
        {
            "key": "virtual_home_type",
            "valueString": "swipe_up"
        },
        {
            "key": "show_virtual_status_bar",
            "valueBool": true
        },
        {
            "key": "exit_lock_task_mode_code",
            "valueString": ""
        },
        {
            "key": "show_wifi_setting",
            "valueBool": false
        },
        {
            "key": "show_bluetooth_setting",
            "valueBool": false
        },
        {
            "key": "grid_size",
            "valueString": "4;5"
        },
        {
            "key": "app_order_enabled",
            "valueBool": true
        },
        {
            "key": "apps_in_folder_ordered_by_name",
            "valueBool": true
        },
        {
            "key": "app_orders",
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "package",
                            "valueString": "com.Microsoft.emmx"
                        },
                        {
                            "key": "type",
                            "valueString": "application"
                        },
                        {
                            "key": "container",
                            "valueInteger": 1
                        },
                        {
                            "key": "position",
                            "valueInteger": 1
                        }
                    ]
                },
                {
                    "managedProperty": [
                        {
                            "key": "folder_name",
                            "valueString": "Work"
                        },
                        {
                            "key": "type",
                            "valueString": "managed_folder"
                        },
                        {
                            "key": "container",
                            "valueInteger": 1
                        },
                        {
                            "key": "position",
                            "valueInteger": 2
                        }
                    ]
                },
                {
                    "managedProperty": [
                        {
                            "key": "package",
                            "valueString": "com.microsoft.launcher.enterprise"
                        },
                        {
                            "key": "type",
                            "valueString": "application"
                        },
                        {
                            "key": "class",
                            "valueString": "com.microsoft.launcher.launcher"
                        },
                        {
                            "key": "container",
                            "valueInteger": 1
                        },
                        {
                            "key": "position",
                            "valueInteger": 3
                        }
                    ]
                }
            ]
        },
        {
            "key": "managed_folders",
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "folder_name",
                            "valueString": "Folder name here"
                        },
                        {
                            "key": "applications",
                            "valueBundleArray": [
                                {
                                    "managedProperty": [
                                        {
                                            "key": "package",
                                            "valueString": "com.microsoft.emmx"
                                        }
                                    ]
                                },
                                {
                                    "managedProperty": [
                                        {
                                            "key": "package",
                                            "valueString": "com.microsoft.bing"
                                        }
                                    ]
                                },
                                {
                                    "managedProperty": [
                                        {
                                            "key": "link",
                                            "valueString": "https://microsoft.com/"
                                        }
                                    ]
                                }
                            ]
                        }
                    ]
                },
                {
                    "managedProperty": [
                        {
                            "key": "folder_name",
                            "valueString": "Example folder name 2"
                        },
                        {
                            "key": "applications",
                            "valueBundleArray": [
                                {
                                    "managedProperty": [
                                        {
                                            "key": "package",
                                            "valueString": "com.microsoft.office.word"
                                        }
                                    ]
                                }
                            ]
                        }
                    ]
                }
            ]
        }
    ]
}
```

## <a name="googles-android-device-policy-app"></a>Aplicativo Política do Dispositivo Android do Google
O aplicativo Tela Inicial Gerenciada agora fornece acesso ao aplicativo Política do Dispositivo Android do Google. O aplicativo Tela Inicial Gerenciada é um inicializador personalizado usado para dispositivos registrados no Intune como dispositivos dedicados do AE (Android Enterprise) que usam o modo de quiosque de vários aplicativos. Você pode acessar o aplicativo Política do Dispositivo Android ou orientar os usuários ao aplicativo Política do Dispositivo Android, para fins de suporte e de depuração. Essa capacidade de inicialização está disponível no momento em que o dispositivo é registrado e bloqueado na Tela Inicial Gerenciada. Nenhuma instalação adicional é necessária para usar essa funcionalidade.

## <a name="managed-home-screen-debug-screen"></a>Tela de depuração da Tela Inicial Gerenciada
Você pode acessar a tela de depuração da Tela Inicial Gerenciada clicando no botão **voltar** até que a tela de depuração seja exibida (clique no botão **voltar** 15 vezes ou mais). Nessa tela de depuração, você poderá iniciar o aplicativo Android Device Policy, exibir e carregar logs ou pausar temporariamente o modo de quiosque para atualizar o dispositivo. Para obter mais informações sobre como pausar o modo de quiosque, confira o item **Sair do modo de quiosque** nas [configurações do dispositivo dedicado](device-restrictions-android-for-work.md#dedicated-device-settings) do Android Enterprise.

## <a name="next-steps"></a>Próximas etapas

- Para obter mais informações sobre dispositivos Android Enterprise dedicados, consulte [Configurar o registro do Intune para dispositivos Android Enterprise dedicados](android-kiosk-enroll.md).
