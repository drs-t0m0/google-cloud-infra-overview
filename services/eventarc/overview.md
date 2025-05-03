# Eventarc 解説

### Eventarcの主な機能

Eventarcは、Google Cloud内外のさまざまなソースからのイベントを、Cloud Run、Cloud Functions、GKE、Workflowsなどの宛先に、信頼性高くルーティングするフルマネージドのサーバーレスサービスです。

* **多様なイベントソース:** Google Cloudサービス（Cloud Storage、Pub/Sub、Cloud Audit Logsなど）、SaaSプロバイダ、カスタムアプリケーションなど、幅広いソースからのイベントをサポートします。
* **柔軟なルーティング:** イベントの種類や属性に基づいて、特定の宛先にイベントをルーティングするトリガーを簡単に設定できます。
* **CloudEvents形式:** イベントは標準化されたCloudEvents形式で配信されるため、異なるシステム間での相互運用性が向上します。
* **サーバーレス:** インフラの管理は不要で、イベントの発生に応じて自動的にスケールします。
* **信頼性の高い配信:** 「少なくとも1回」のイベント配信を保証し、配信失敗時の再試行メカニズムを備えています。

### 料金

Eventarcの料金は、主に以下の要素に基づいて計算されます。

* **Eventarc Standard:**
    * 最初の50,000イベント/月は無料です。
    * Google Cloudソースからのイベント配信は無料です。
    * Pub/Subソースからのイベント配信も無料です。
    * その他のソースからのイベント配信は、プレビュー期間中は無料、その後は料金が発生する可能性があります。
    * イベントサイズが64KBを超える場合は、64KBごとに1イベントとして課金されます。
    * EventarcはPub/Subをトランスポート層として利用するため、Pub/Subの標準料金も適用されます。
* **Eventarc Advanced:**
    * イベントのパブリッシュとパイプラインの使用量に応じて課金されます。詳細な料金体系は[Eventarc pricing - Google Cloud](https://cloud.google.com/eventarc/pricing)をご確認ください。

### 類似サービスとの比較

* **Cloud Pub/Sub:** メッセージングミドルウェアであり、Pub/Subトピックとサブスクリプションを通じてメッセージを送受信します。EventarcはPub/Subを基盤としていますが、より高レベルな抽象化を提供し、多様なイベントソースとの統合や、Cloud Runなどのサーバーレスサービスへの直接的なイベントルーティングを容易にします。Pub/Subはより柔軟なメッセージングパターンや、きめ細かい制御が必要な場合に適しています。
* **Cloud Functions/Cloud RunのHTTPトリガー:** これらのサービスはHTTPリクエストによって直接起動できますが、EventarcはHTTPエンドポイントを公開することなく、さまざまなイベントに応じた処理を自動化できます。

### 利用シナリオ

Eventarcは、以下のようなイベント駆動型のアプリケーションやシステムの構築に役立ちます。

* **サーバーレスワークフローの自動化:** Cloud Storageへのファイルアップロードをトリガーに画像処理を実行したり、Cloud Buildの完了をトリガーにデプロイパイプラインを開始したりできます。
* **アプリケーション統合:** Google CloudサービスやサードパーティSaaS間のイベントに基づいて、疎結合な連携を実現できます。例えば、顧客管理システムで新しい顧客が作成されたときに、マーケティングツールに通知を送信できます。
* **リアルタイムデータ処理:** IoTデバイスからのデータストリームをEventarc経由で処理し、分析基盤に連携させることができます。
* **監査ログの活用:** Cloud Audit Logsのイベントをトリガーに、セキュリティ監視やコンプライアンス対応の処理を自動化できます。

Eventarcは、イベント駆動型アーキテクチャをより簡単に、スケーラブルに構築するための強力なツールです。

## 参考

- https://cloud.google.com/eventarc/docs?hl=ja
- https://cloud.google.com/eventarc/standard/docs/overview?hl=ja
- https://cloud.google.com/eventarc/advanced/docs/overview?hl=ja
- https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/eventarc_pipeline
