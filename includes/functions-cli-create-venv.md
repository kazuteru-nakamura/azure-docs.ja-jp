---
author: ggailey777
ms.service: azure-functions
ms.topic: include
ms.date: 03/30/2020
ms.author: glenga
ms.openlocfilehash: 44969063765099d350e21abfbd07792891443911
ms.sourcegitcommit: 58faa9fcbd62f3ac37ff0a65ab9357a01051a64f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "80673204"
---
::: zone pivot="programming-language-python"  
## <a name="create-and-activate-a-virtual-environment"></a><a name="create-venv"></a>仮想環境を作成してアクティブにする

適切なフォルダーで次のコマンドを実行し、`.venv` という名前の仮想環境を作成してアクティブにします。 必ず、Azure Functions でサポートされている Python 3.8、3.7、または 3.6 を使用してください。

# <a name="bash"></a>[bash](#tab/bash)

```bash
python -m venv .venv
```

```bash
source .venv/bin/activate
```

お使いの Linux ディストリビューションに Python の venv パッケージがインストールされていなかった場合は、次のコマンドを実行します。

```bash
sudo apt-get install python3-venv
```

# <a name="powershell"></a>[PowerShell](#tab/powershell)

```powershell
py -m venv .venv
```

```powershell
.venv\scripts\activate
```

# <a name="cmd"></a>[Cmd](#tab/cmd)

```cmd
py -m venv .venv
```

```cmd
.venv\scripts\activate
```

---

以降のコマンドはすべて、このアクティブ化された仮想環境で実行します (仮想環境を終了するには、`deactivate` を実行します)。
::: zone-end