# Cloud Interconnect 解説

## Cloud Interconnectの主な機能

Cloud Interconnectは、オンプレミス環境とGoogle Cloud VPC（Virtual Private Cloud）ネットワークの間で、高帯域幅かつ低遅延の専用線接続を提供するサービスです。主な機能は以下の通りです。

* **専用接続:** パブリックインターネットを経由しない、物理的な専用線またはサービスプロバイダ経由の論理的な専用接続を確立します。
* **高帯域幅:** 10 Gbpsまたは100 Gbpsの物理回線を利用でき、複数の回線を束ねてより高い帯域幅を実現することも可能です（Dedicated Interconnectの場合）。Partner Interconnectでは、50 Mbpsから50 Gbpsまでの柔軟な帯域幅オプションが利用できます。
* **低遅延:** 専用線接続により、パブリックインターネットの変動要因を排除し、安定した低遅延の通信を実現します。
* **プライベートIPアドレス通信:** RFC 1918で定義されたプライベートIPアドレス空間を使用して、オンプレミスとGoogle Cloud間で直接通信できます。
* **柔軟な接続オプション:**
    * **Dedicated Interconnect:** お客様のオンプレミスネットワークとGoogle Cloudのネットワークを直接接続するための物理的な専用回線を提供します。お客様がGoogle Cloudの接続拠点に機器を設置する必要があります。
    * **Partner Interconnect:** Google Cloudのパートナープロバイダのネットワークを経由して、お客様のオンプレミスネットワークとGoogle Cloudのネットワークを接続します。お客様はパートナープロバイダとの接続のみを管理します。
    * **Cross-Cloud Interconnect:** Google Cloudと他のクラウドプロバイダ（AWS、Azureなど）の間で、高帯域幅かつ低遅延の専用線接続を提供します。
* **冗長構成:** 高可用性を実現するために、冗長化された接続構成を組むことが推奨されます。
* **VLANアタッチメント:** Cloud Interconnect接続上で、複数のVPCネットワークに接続するためのVLANアタッチメントを作成できます。

## 料金

Cloud Interconnectの料金は、主に以下の要素に基づいて計算されます。

* **Cloud Interconnect接続のポート料金:** Dedicated InterconnectおよびCross-Cloud Interconnectの物理ポートに対して、時間単位の料金が発生します。Partner Interconnectの場合は、VLANアタッチメントの容量に応じた時間単位の料金となります。
* **VLANアタッチメント料金:** VLANアタッチメントに対して、時間単位の料金が発生します。容量によって料金が異なる場合があります。
* **データ転送料金:** Google Cloud VPCネットワークからCloud Interconnect接続を経由して外部に送信されるデータに対して、GB単位の料金が発生します。送信元リージョンと送信先リージョンによって料金が異なります。

**料金例（Dedicated Interconnect）**

* 10 Gbps回線: $2.328/時間
* 100 Gbps回線: $23.28/時間
* 1 Gbps VLANアタッチメント: $0.10/時間
* 北米リージョンから北米リージョンへのデータ転送: $0.020/GiB

**料金例（Partner Interconnect）**

* 1 Gbps VLANアタッチメント: $0.2778/時間
* データ転送料金はDedicated Interconnectと同様です。

**料金例（Cross-Cloud Interconnect）**

* 10 Gbps回線: $5.60/時間
* 100 Gbps回線: $30/時間
* VLANアタッチメント料金はDedicated Interconnectと同様です。
* データ転送料金は、関連するGoogle Cloudリージョンの標準データ転送料金が適用されます。

最新の正確な料金については、[Google Cloudのネットワーク接続料金ページ](https://cloud.google.com/network-connectivity/pricing)をご確認ください。

## 類似サービスとの比較

Google Cloudには、ネットワーク接続に関する類似のサービスがあります。

* **Cloud VPN:** パブリックインターネット上にIPsec VPNトンネルを確立し、オンプレミス環境とVPCネットワーク間で安全な接続を提供します。Cloud Interconnectと比較して、帯域幅や遅延の保証はありませんが、手軽に導入できます。
* **Direct Peering:** Googleのネットワークとお客様のネットワークを直接接続するサービスですが、特定の技術要件を満たす必要があります。Cloud Interconnectよりも複雑な構成となる場合があります。
* **Carrier Peering:** 通信事業者を経由してお客様のネットワークとGoogleのネットワークを接続するサービスです。Direct Peeringと同様に、特定の要件があります。

Cloud Interconnectは、これらのサービスと比較して、**より高い帯域幅、より低い遅延、およびより安定した接続**を提供することを目的としています。特に、ミッションクリティカルなアプリケーションや大量のデータ転送が必要な場合に適しています。Cross-Cloud Interconnectは、マルチクラウド環境におけるセキュアで高パフォーマンスな接続を実現します。

## 利用シナリオ

Cloud Interconnectは、以下のようなシナリオで活用できます。

* **ハイブリッドクラウド環境の構築:** オンプレミスで稼働しているシステムを段階的にGoogle Cloudへ移行する際に、両環境間の高速かつ安定した接続を確立します。
* **ディザスタリカバリ（DR）:** オンプレミス環境の障害時に備え、Google Cloud上にDR環境を構築し、Cloud Interconnectで両環境を接続します。
* **ビッグデータ分析:** オンプレミスに蓄積された大量のデータをGoogle Cloudのデータ分析サービスに高速に転送し、分析処理を行います。
* **高性能コンピューティング（HPC）:** オンプレミスのHPC環境とGoogle CloudのHPCサービスを低遅延で接続し、計算処理を連携させます。
* **メディアコンテンツ配信:** オンプレミスのメディアサーバーとGoogle CloudのCDN（Content Delivery Network）を接続し、低遅延で高品質なコンテンツ配信を実現します。
* **マルチクラウド連携:** 複数のクラウドプロバイダのサービスを組み合わせて利用する際に、Cross-Cloud Interconnectを用いてクラウド間を高速かつセキュアに接続します。

Cloud Interconnectは、お客様のネットワーク要件や利用シナリオに応じて、最適な接続オプションを選択し、柔軟なハイブリッドクラウド環境やマルチクラウド環境の構築を支援します。

## 参考

- https://cloud.google.com/network-connectivity/docs/interconnect/concepts/overview?hl=ja
- https://cloud.google.com/network-connectivity/docs/interconnect/concepts/dedicated-overview?hl=ja
- https://cloud.google.com/network-connectivity/docs/interconnect/concepts/partner-overview?hl=ja
- https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_interconnect

