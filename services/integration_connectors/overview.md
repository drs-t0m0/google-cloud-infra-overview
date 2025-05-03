# Integration Connectors 解説

**Integration Connectors とは**

Integration Connectors は、Google Cloud の Application Integration サービスの一部であり、様々なデータソースやアプリケーションへの接続を容易にするための機能です。これにより、統合開発者は、プロトコル固有の知識やカスタムコードを記述することなく、Google Cloud サービスやサードパーティのビジネスアプリケーションに迅速かつ容易に接続できます。

**主な機能**

* **多様なコネクタ:** Google Cloud サービス（BigQuery、Pub/Sub、Cloud SQL など）や、Salesforce、SAP、ServiceNow、各種データベース、SaaS アプリケーションなど、幅広い種類のコネクタが用意されています。
* **標準化されたインターフェース:** 各コネクタは、ターゲットアプリケーションのネイティブプロトコル（JDBC など）を標準的な通信プロトコル（REST など）に変換し、データ形式も標準化します。
* **簡単な設定:** Google Cloud コンソールから、接続を一度設定するだけで、その後の統合で再利用できます。
* **データ検出:** コネクタがターゲットアプリケーションを検査し、利用可能なデータオブジェクトや操作の一覧を提供します。
* **イベントサブスクリプション:** コネクタのイベントリスナーを設定し、イベントをトリガーとして統合を実行できます。
* **認証:** 各コネクタは、ターゲットアプリケーションに合わせて、複数の認証方法をサポートしています。
* **エンドポイント設定:** 接続先のアプリケーションインスタンスの URL やテナント ID などを設定できます。
* **プライベートネットワーク接続:** VPC Service Controls に対応しており、クラウドプロジェクトからのデータ流出を防ぐことができます。

**料金**

Application Integration の料金体系に基づいて課金されます。主な課金要素は以下の通りです。

* **統合の実行:** 処理された統合の数に応じて課金されます（例: 1,000 回の実行ごとに $0.50）。
* **接続ノードの時間料金:**
    * 最初の 2 つの Google サービスへの接続ノードは無料です。
    * Google サービスの後続の各ノードは 1 時間あたり $0.35 です。
    * サードパーティアプリケーションコネクタの各ノードは 1 時間あたり $0.70 です。
    * 停止状態の接続に対しては課金されません。
* **データ処理量:** 接続を介して処理されるデータ量（リクエストとレスポンスのペイロードを含む）に応じて課金されます。毎月最初の 20 GiB までは無料、超過分は 1 GiB あたり $10 です。

プレビュー版のコネクタは無料で使用できます。

**類似サービスとの比較**

Integration Connectors と類似のサービスとしては、以下のようなものが挙げられます。

* **Zapier:** 様々な Web アプリケーション間の連携を自動化するiPaaS (Integration Platform as a Service) です。Integration Connectors と比較して、より幅広いアプリケーションに対応しており、ノーコードでの自動化に強みがあります。
* **Workato:** エンタープライズ向けの iPaaS で、高度なワークフロー自動化やAPI管理機能を提供します。Integration Connectors よりも高機能で、複雑な統合シナリオに対応できます。
* **MuleSoft Anypoint Platform:** API主導の接続性を実現するための統合プラットフォームです。APIの設計、開発、管理、セキュリティなど、包括的な機能を提供します。
* **AWS Glue:** サーバーレスのデータ統合サービスで、ETL (Extract, Transform, Load) ジョブを簡単に構築・実行できます。データ処理に特化しており、Integration Connectors とは用途が異なります。
* **Azure Logic Apps:** Microsoft Azure のサーバーレスロジック統合プラットフォームです。様々なサービスやアプリケーションとの連携を自動化できます。

Integration Connectors は、Google Cloud の Application Integration サービスに統合されており、Google Cloud 環境との親和性が高い点が特徴です。

**利用シナリオ**

Integration Connectors は、以下のような様々なシナリオで活用できます。

* **SaaS アプリケーションとの連携:** Salesforce の顧客データを BigQuery で分析したり、ServiceNow のインシデント情報を Slack に通知したりするなど、様々な SaaS アプリケーションと Google Cloud サービスを連携させることができます。
* **オンプレミスシステムとの連携:** FTP サーバーやオンプレミスデータベースと連携し、データを Google Cloud 上で処理したり、クラウドからオンプレミスシステムにデータを送信したりすることができます。
* **API 連携:** REST API や SOAP API を持つ様々なアプリケーションやサービスと連携し、データの取得や更新、処理の実行などを自動化できます。
* **イベント駆動型アーキテクチャ:** Cloud Pub/Sub などのメッセージングサービスと連携し、特定のイベントが発生した際に自動的に処理を実行するシステムを構築できます。
* **データパイプラインの構築:** Cloud Storage に格納されたデータを BigQuery にロードしたり、Dataflow で変換処理を行ったりするデータパイプラインの一部として、様々なデータソースからのデータ取得に利用できます。

Integration Connectors を活用することで、異なるシステム間のデータ連携やワークフロー自動化を効率的に実現し、ビジネスプロセスの改善や新たな価値の創出に貢献できます。

## 参考

- https://cloud.google.com/integration-connectors/docs/overview?hl=ja
- https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/integration_connectors_connection
