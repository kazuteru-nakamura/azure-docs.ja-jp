---
title: Azure Service Fabric CLI- sfctl mesh service
description: Azure Service Fabric のコマンド ライン インターフェイスである sfctl について説明します。 アプリケーション リソースに対するサービスの詳細を取得するためのコマンドの一覧が含まれます。
author: jeffj6123
ms.topic: reference
ms.date: 1/16/2020
ms.author: jejarry
ms.openlocfilehash: 2b9f16062b02d7a1a3403d396643a7989b8976b7
ms.sourcegitcommit: 2ec4b3d0bad7dc0071400c2a2264399e4fe34897
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2020
ms.locfileid: "76905928"
---
# <a name="sfctl-mesh-service"></a>sfctl mesh service
サービスの詳細を取得し、アプリケーション リソースのサービスを一覧表示します。

## <a name="commands"></a>コマンド

|command|説明|
| --- | --- |
| list | すべてのサービスのリソースを一覧表示します。 |
| show | 指定した名前のサービスのリソースを取得します。 |

## <a name="sfctl-mesh-service-list"></a>sfctl mesh service list
すべてのサービスのリソースを一覧表示します。

アプリケーション リソースのすべてのサービスに関する情報を取得します。 この情報には、サービスの説明とその他のプロパティが含まれます。

### <a name="arguments"></a>引数

|引数|説明|
| --- | --- |
| --app-name --application-name [必須] | アプリケーションの名前です。 |

### <a name="global-arguments"></a>グローバル引数

|引数|説明|
| --- | --- |
| --debug | すべてのデバッグ ログを表示するようにログの詳細レベルを上げます。 |
| --help -h | このヘルプ メッセージを表示して終了します。 |
| --output -o | 出力形式。  使用可能な値\: json、jsonc、table、tsv。  既定値\: json。 |
| --query | JMESPath クエリ文字列。 詳細と例については、http\://jmespath.org/ を参照してください。 |
| --verbose | ログの詳細レベルを上げます。 詳細なデバッグ ログを表示するには --debug を使います。 |

## <a name="sfctl-mesh-service-show"></a>sfctl mesh service show
指定した名前のサービスのリソースを取得します。

指定した名前のサービス リソースに関する情報を取得します。 この情報には、サービスの説明とその他のプロパティが含まれます。

### <a name="arguments"></a>引数

|引数|説明|
| --- | --- |
| --app-name --application-name [必須] | アプリケーションの名前です。 |
| --name -n                     [必須] | サービスの名前。 |

### <a name="global-arguments"></a>グローバル引数

|引数|説明|
| --- | --- |
| --debug | すべてのデバッグ ログを表示するようにログの詳細レベルを上げます。 |
| --help -h | このヘルプ メッセージを表示して終了します。 |
| --output -o | 出力形式。  使用可能な値\: json、jsonc、table、tsv。  既定値\: json。 |
| --query | JMESPath クエリ文字列。 詳細と例については、http\://jmespath.org/ を参照してください。 |
| --verbose | ログの詳細レベルを上げます。 詳細なデバッグ ログを表示するには --debug を使います。 |


## <a name="next-steps"></a>次のステップ
- Service Fabric CLI を[セットアップ](service-fabric-cli.md)します。
- [サンプル スクリプト](/azure/service-fabric/scripts/sfctl-upgrade-application)を使用して、Service Fabric CLI の使用方法を学習します。