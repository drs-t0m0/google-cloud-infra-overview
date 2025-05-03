# API Gateway 解説

Google Cloud API Gatewayは、Google Cloudのフルマネージドなサービスで、APIへのアクセスを一元的に管理、保護、監視することができます。API Gatewayを利用することで、バックエンドサービスの複雑さを隠蔽し、クライアントに対してシンプルで一貫性のあるAPIを提供できます。

**主な機能:**

* **APIの公開と管理:** REST APIやHTTP APIを定義し、公開できます。OpenAPI仕様（Swagger）を使用したAPI定義のインポートも可能です。
* **認証と認可:** APIキー、JWT（JSON Web Tokens）、Google CloudのIAM（Identity and Access Management）と連携した認証・認可機能を提供し、APIへの不正アクセスを防ぎます。
* **トラフィック管理:** レート制限や割り当て（Quota）を設定することで、APIの安定性を維持し、予期しないトラフィックの急増からバックエンドサービスを保護します。
* **セキュリティ:** TLSによる暗号化、APIキーによるアクセス制限、IPアドレスによるアクセス制限など、APIのセキュリティを強化する機能を提供します。
* **モニタリングとロギング:** APIの利用状況、レイテンシ、エラー率などのメトリクスをCloud Monitoringで監視できます。Cloud Loggingと連携して、APIリクエストとレスポンスの詳細なログを記録できます。
* **APIのルーティング:** 受信したリクエストを適切なバックエンドサービスにルーティングします。
* **リクエストとレスポンスの変換:** クライアントからのリクエストやバックエンドからのレスポンスを、必要に応じて変換できます。
* **APIのバージョン管理:** 複数のAPIバージョンを同時に管理できます。
* **サーバーレス連携:** Cloud FunctionsやCloud Runなどのサーバーレスコンピューティングサービスとの連携が容易です。

**料金:**

API Gatewayの料金は、主に以下の要素に基づいて課金されます。

* **API呼び出し回数:** API Gatewayを経由したAPIの呼び出し回数に応じて課金されます。通常、月間の呼び出し回数が多いほど、1回あたりの料金が低くなる従量課金制です。
* **データ転送量:** API Gatewayを経由して送受信されるデータ量に応じて課金されます。Google Cloudへのデータ転送は無料ですが、Google Cloudから外部へのデータ転送には料金が発生します。

詳細な料金体系については、[Google Cloud API Gatewayの料金ページ](https://cloud.google.com/api-gateway/pricing?hl=ja)をご確認ください。

**類似サービスとの比較:**

Google Cloudには、API管理に関連する類似のサービスとして、Cloud EndpointsやApigee API Platformがあります。

* **Cloud Endpoints:** 主にAPIのセキュリティと基本的な管理機能に特化しており、API Gatewayよりも軽量で、よりバックエンドサービスに近い位置で動作します。
* **Apigee API Platform:** エンタープライズ向けの包括的なAPI管理プラットフォームであり、高度なポリシー管理、収益化、開発者ポータルなどの機能を提供します。

API Gatewayは、Cloud EndpointsとApigeeの中間的な位置づけで、サーバーレス環境との親和性が高く、比較的容易に導入できる点が特徴です。

**利用シナリオ:**

* **マイクロサービスアーキテクチャ:** 複数のマイクロサービスを統合し、クライアントに統一されたAPIを提供します。
* **モバイルアプリケーションのバックエンド:** モバイルアプリが必要とするAPIを集約し、効率的なデータアクセスを実現します。
* **パートナー連携:** 外部のパートナー企業に対してセキュアにAPIを公開します。
* **APIの近代化:** レガシーシステムをAPI Gatewayでラップし、最新のAPIとして公開します。

API Gatewayを利用することで、API開発者はバックエンドサービスの構築に集中でき、APIの管理、セキュリティ、監視といった共通の課題をAPI Gatewayに任せることができます。

## 参考

- https://cloud.google.com/api-gateway/docs/about-api-gateway?hl=ja
- https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/api_gateway_api
