---
author: ggailey777
ms.author: glenga
ms.date: 7/24/2019
ms.topic: include
ms.service: azure-functions
ms.openlocfilehash: 1928a8238cd73087e3c199675574dd1395f4d76d
ms.sourcegitcommit: 2ec4b3d0bad7dc0071400c2a2264399e4fe34897
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2020
ms.locfileid: "68881321"
---
#### <a name="built-in-log-streaming"></a>組み込みのログ ストリーミング

次の例のように、`logstream` オプションを使用して、Azure 内で実行されている特定の関数アプリのストリーミング ログの受信を開始します。

```bash
func azure functionapp logstream <FunctionAppName>
```

#### <a name="live-metrics-stream"></a>ライブ メトリック ストリーム

また、次の例に示すように、`--browser` オプションを含めることによって、関数アプリの [Live Metrics Stream](../articles/azure-monitor/app/live-stream.md) を新しいブラウザー ウィンドウに表示することもできます。

```bash
func azure functionapp logstream <FunctionAppName> --browser
```
