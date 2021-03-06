---
title: SQL オンデマンド (プレビュー) のセルフヘルプ
description: このセクションには、SQL オンデマンド (プレビュー) に関する問題のトラブルシューティングに役立つ情報が含まれています。
services: synapse analytics
author: vvasic-msft
ms.service: synapse-analytics
ms.topic: overview
ms.subservice: ''
ms.date: 04/15/2020
ms.author: vvasic
ms.reviewer: jrasnick
ms.openlocfilehash: e2c262915c928cf487cb84aeb3423d67e7a96e97
ms.sourcegitcommit: b80aafd2c71d7366838811e92bd234ddbab507b6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "81421196"
---
# <a name="self-help-for-sql-on-demand-preview"></a>SQL オンデマンド (プレビュー) のセルフヘルプ

この記事には、Azure Synapse Analytics の SQL オンデマンド (プレビュー) でよく発生する問題のトラブルシューティング方法に関する情報が含まれています。

## <a name="sql-on-demand-is-grayed-out-in-synapse-studio"></a>Synapse Studio で SQL オンデマンドがグレー表示される

Synapse Studio が SQL オンデマンドへの接続を確立できない場合、SQL オンデマンドがグレー表示されるか、状態が "オフライン" と表示されます。 通常、この問題は次のいずれかの場合に発生します。

1) Azure Synapse バックエンドとの通信がネットワークによって妨げられている。 最も頻繁なケースは、ポート 1443 がブロックされているケースです。 SQL オンデマンドを動作させるには、このポートのブロックを解除します。 これ以外の問題が原因で SQL オンデマンドが動作しなくなることがあります。[詳細については、完全なトラブルシューティング ガイドを参照してください](../troubleshoot/troubleshoot-synapse-studio.md)。
2) SQL オンデマンドにログインするアクセス許可がない。 ユーザーがアクセスできるようにするには、Azure Synapse ワークスペース管理者がワークスペース管理者または SQL 管理者ロールにユーザーを追加する必要があります。 [詳細については、アクセス制御に関する完全なガイドを参照してください](access-control.md)。

## <a name="query-fails-because-file-cannot-be-opened"></a>ファイルを開くことができないため、クエリが失敗する

"File cannot be opened because it does not exist or it is used by another process (ファイルが存在しないか、別のプロセスで使用されているため、開くことができません)" というエラーでクエリが失敗したときに、ファイルが存在し、かつ別のプロセスで使用されていないことが確認されている場合は、SQL オンデマンドがファイルにアクセスできないことを意味します。 この問題は通常、ファイルにアクセスする権限が Azure Active Directory ID にないために発生します。 SQL オンデマンドでは、既定で、Azure Active Directory ID を使用してファイルへのアクセスを試みます。 この問題を解決するには、ファイルにアクセスするための適切な権限を持っている必要があります。 最も簡単な方法は、クエリの対象となるストレージ アカウントに対する "ストレージ BLOB データ共同作成者" ロールを自分に付与することです。 [詳細については、ストレージの Azure Active Directory アクセス制御に関する完全なガイドを参照してください](../../storage/common/storage-auth-aad-rbac-portal.md?toc=/azure/synapse-analytics/toc.json&bc=/azure/synapse-analytics/breadcrumb/toc.json)。 

## <a name="query-fails-because-it-cannot-be-executed-due-to-current-resource-constraints"></a>現在のリソース制約によりクエリを実行できないため、クエリが失敗する 

"This query cannot be executed due to current resource constraints (現在のリソース制約のため、このクエリを実行できません)" というエラー メッセージでクエリが失敗する場合、リソースの制約により、SQL OD が現時点でクエリを実行できないことを意味します。 

- 適切なサイズのデータ型が使用されていることを確認してください。 また、文字列型の列の場合は既定で VARCHAR (8000) になるため、Parquet ファイルのスキーマを指定します。 

- 対象のクエリが CSV ファイルをターゲットとしている場合は、[統計を作成する](develop-tables-statistics.md#statistics-in-sql-on-demand-preview)ことを検討してください。 

- クエリを最適化するには、[SQL オンデマンドのパフォーマンスのベスト プラクティス](best-practices-sql-on-demand.md)に関するページを参照してください。  

## <a name="next-steps"></a>次のステップ

SQL オンデマンドの使用方法について詳しくは、次の記事をご覧ください。

- [単一の CSV ファイルに対するクエリを実行する](query-single-csv-file.md)

- [フォルダーと複数の CSV ファイルに対するクエリを実行する](query-folders-multiple-csv-files.md)

- [特定のファイルに対するクエリを実行する](query-specific-files.md)

- [Parquet ファイルに対するクエリを実行する](query-parquet-files.md)

- [Parquet の入れ子にされた型に対するクエリを実行する](query-parquet-nested-types.md)

- [JSON ファイルに対するクエリを実行する](query-json-files.md)

- [ビューの作成と使用](create-use-views.md)

- [外部テーブルの作成と使用](create-use-external-tables.md)

- [クエリ結果をストレージに格納する](create-external-table-as-select.md)
