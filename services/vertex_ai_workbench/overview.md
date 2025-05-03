# Vertex AI Workbench 解説

Vertex AI Workbenchは、Google CloudのVertex AIプラットフォームの一部として提供される、フルマネージドなJupyterLab環境です。データサイエンティストや機械学習エンジニアが、データ探索、モデル開発、実験、デプロイなどの機械学習ワークフローを効率的に行うための機能を提供します。

### 主な機能

  * **統合された環境:** BigQuery、Cloud StorageなどのGoogle Cloudのデータサービスや、Vertex AIの各種機能（Training、Pipelinesなど）と深く統合されており、データへのアクセスや機械学習ワークフローの実行が容易です。
  * **柔軟なインスタンス:**
      * **Vertex AI Workbenchインスタンス:** マネージドノートブックの使いやすさと、ユーザー管理ノートブックのカスタマイズ性を兼ね備えた新しいオプションです。
      * **マネージドノートブック (非推奨):** Googleによって管理される環境で、インフラの管理が不要で、すぐに機械学習の開発を開始できます。自動シャットダウンなどの機能により、コスト効率も優れています。
      * **ユーザー管理ノートブック (非推奨):** 環境を細かくカスタマイズしたいユーザー向けのオプションです。
  * **多様なカーネル:** TensorFlow、PyTorch、Spark、Rなど、主要な機械学習フレームワークに対応したカーネルがプリインストールされており、必要に応じて追加のライブラリをインストールすることも可能です。
  * **コラボレーション:** GitHubとの連携により、ノートブックを共有したり、バージョン管理を行ったりすることが容易です。
  * **自動化:** ノートブックのコード実行をスケジュール設定し、定期的なモデルの更新やバッチ処理などを自動化できます。
  * **可視化:** BigQueryとの連携により、JupyterLab内から直接クエリを実行し、結果を可視化することができます。

### 料金

Vertex AI Workbenchの料金は、使用するコンピューティングリソース（CPU、GPU、メモリ）とディスク容量に基づいて時間単位で課金されます。

  * **インスタンス費用:** 選択するマシンタイプによって異なります。例えば、N1シリーズのCPUインスタンスやGPU搭載インスタンスなどがあります。
  * **管理費用:** マネージドノートブックの場合、インスタンスの管理に関する費用が別途発生する場合があります。

詳細な料金については、[Vertex AIの料金まとめ - Zenn](https://zenn.dev/pluck/articles/2a12575a69e9ca)や[Google Cloud Vertex AI Pricing Review 2025: Plans & Costs - Tekpon](https://tekpon.com/software/google-cloud-vertex-ai/pricing/)などの情報源をご参照ください。また、[Vertex AI Workbench pricing details](https://www.google.com/search?q=https://cloud.google.com/vertex-ai-notebooks%23pricing)も参考になります。

### 類似サービスとの比較

  * **Google Colaboratory:** 無償で利用できるJupyter Notebook環境ですが、実行時間やリソースに制限があります。Vertex AI Workbenchは、より本格的な機械学習開発や大規模なデータ処理に適しています。
  * **Amazon SageMaker Studio:** AWSの機械学習プラットフォームであるSageMakerのJupyterLabベースのIDEです。Vertex AI Workbenchと同様に、データ統合や機械学習ワークフローの効率化を支援します。
  * **Azure Machine Learning Notebooks:** Azureの機械学習サービスのJupyter Notebook環境です。Azureの各種サービスとの連携が強みです。

Vertex AI Workbenchの強みは、Google Cloudの他のサービスとのシームレスな連携、柔軟なインスタンスオプション、そしてエンタープライズレベルの機能（セキュリティ、コラボレーション、自動化など）です。

### 利用シナリオ

  * **データ探索と分析:** BigQueryやCloud Storage上のデータに対して、インタラクティブにクエリを実行したり、可視化したりすることで、データの理解を深めます。
  * **モデル開発と実験:** TensorFlowやPyTorchなどのフレームワークを用いて、様々なモデルを構築し、実験管理ツールと連携しながら性能を評価します。
  * **大規模データ処理:** Dataprocクラスタ上でノートブックを実行することで、分散処理を活用した効率的なデータ処理を行います。
  * **機械学習パイプラインの構築:** Vertex AI Pipelinesと連携し、ノートブックをパイプラインのステップとして組み込むことで、機械学習ワークフロー全体を自動化します。
  * **共同研究と開発:** GitHub連携を通じて、チームメンバーとノートブックを共有し、共同で作業を進めます。

Vertex AI Workbenchは、Google Cloud上で機械学習プロジェクトを進める上で、非常に強力なツールとなります。

## 参考

- https://cloud.google.com/vertex-ai/docs/workbench/introduction?hl=ja
- https://cloud.google.com/vertex-ai/docs/workbench/instances/introduction?hl=ja
- https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/workbench_instance
