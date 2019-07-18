---

copyright:
  years: 2017, 2019
lastupdated: "2019-06-05"

keywords: centralized security, security management, alerts, security risk, insights, threat detection

subcollection: security-advisor

---

{:new_window: target="_blank"}
{:external: target="_blank" .external}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:codeblock: .codeblock}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}
{:download: .download}

# {{site.data.keyword.security-advisor_short}} の概要
{: #about}

{{site.data.keyword.security-advisor_long}} を使用すると、一元化されたダッシュボードにより、集中化セキュリティー管理を行うことができます。問題に対するアラートをセキュリティー管理者に出したり、セキュリティー管理者がクラウドのアプリケーションとワークロードに関連したセキュリティー問題を理解し、優先順位を付け、管理し、解決できるようにガイドしたりします。
{: shortdesc}

## サービスを使用する利点
{: #about-benefits}

![{{site.data.keyword.security-advisor_short}} アーキテクチャー](images/sa-benefits.png)


<dl>
  <dt>セキュリティー・リスクと態勢</dt>
    <dd>ニュース記事では新たなデータ漏えいやハッキングについて繰り返し伝えられており、アプリケーション・セキュリティーは依然として重要です。 開発には必ずセキュリティー・リスクがつきものであり、攻撃を予測することは難しいものの、攻撃を防ぐ方法の 1 つはクラウド・デプロイメントを入念にモニターすることです。 例えば、リスクは、使用中のコンテナー・イメージ内の脆弱性、クラウド・サービスやアプリケーションの停止を引き起こす証明書の期限切れ、評価の低いことが知られている不審なクライアントやサーバーと使用しているクラスターとの間の対話などに関連しています。</dd>
  <dt>集中化セキュリティー管理</dt>
    <dd>すべての {{site.data.keyword.cloud_notm}} セキュリティー・サービスと統合済みのパートナー・サービスの統合ビューを表示できます。 {{site.data.keyword.cloud_notm}} カタログから別のサービスを選択してサブスクライブできます。</dd>
  <dt>脅威の検出</dt>
    <dd>{{site.data.keyword.security-advisor_short}} は、IBM X-Force、その他の {{site.data.keyword.cloud_notm}} サービス、パートナー・ソリューションにより収集される情報を活用して、リスクや脅威をセキュリティー上の問題になる前に検出します。 またこのサービスは、脆弱性データやネットワーク・アクティビティー・データに加えて分析も提供します。</dd>
</dl>


## 仕組み
{: #how-it-works}

大規模にセキュリティー保守を行えるように、{{site.data.keyword.security-advisor_short}} は {{site.data.keyword.cloud_notm}} 上のマイクロ・サービスとして設計されています。 中核のマイクロ・サービスとして Findings API が提供されています。Findings API は、{{site.data.keyword.cloud_notm}} サービスとパートナー・サービスがサービス・ダッシュボードにセキュリティーの検出事項を送信するメカニズムを実装します。
{: shortdesc}

このサービスは、以下から検出事項を受け取ります。
* 証明書マネージャーや脆弱性アドバイザーなどの、事前統合済みの {{site.data.keyword.cloud_notm}} サービス
* Network Insights
* Activity Insights
* NeuVector や Twistlock などの IBM ビジネス・パートナー
* その他のセキュリティー・ツールとのカスタム統合

以下の画像を確認して、{{site.data.keyword.security-advisor_short}} の各コンポーネントがどのように組み合わせられているかを参照してください。

![{{site.data.keyword.security-advisor_short}} アーキテクチャー](images/how-it-works.png)



{{site.data.keyword.security-advisor_short}} は、セキュリティー管理者にとって最も有用です。 この役割を果たす役職名は多数あります。 ユーザーの例については、以下の表を確認してください。

<table>
  <tr>
    <th colspan=2><img src="images/idea.png" alt="電球アイコン"/> セキュリティー管理者</th>
  </tr>
  <tr>
    <td>CIO</td>
    <td>CIO またはエンタープライズ・アーキテクチャー・チームは、会社全体の高水準のセキュリティーとコンプライアンスのポリシーを定義します。</td>
  </tr>
  <tr>
    <td>CISO</td>
    <td>CISO は、自分たちの制御下のシステムに対する、CIO が設定したポリシーの実施方法を決めます。 ここには、デプロイされるミドルウェア、サーバー、またはアーキテクチャーが含まれます。 CISO は、組織のセキュリティー・ガバナンスやセキュリティー・ポリシーを定義します。 セキュリティー・リスクをモニターし、ISO や GDPR などのコンプライアンス規格に合うように制御を定義します。 また、チームが使用するツールも決めます。</td>
  </tr>
  <tr>
    <td>セキュリティー・フォーカル</td>
    <td>CISO を支援し、必要なセキュリティー検査を実行し、リスクや問題の可能性を調査します。 </td>
  </tr>
</table>

会社の規模に応じて、上記の役割を 1 人で実行する場合もあれば複数人で実行する場合もあります。 しかし、オファリングは 1 人の CISO またはセキュリティー・フォーカルの日常の要件に対応するように作成されています。


### Findings API
{: #api}

このサービスには、API でフラグを立てられる、事前統合済みの検出事項が付属しており、すぐに使用可能です。
{: shortdesc}

{{site.data.keyword.security-advisor_short}} の Findings API は、[Grafeas](https://grafeas.io/){: external} 成果物メタデータ API 仕様に従って、重要なメタデータの保管、照会、取得を実行します。 検出事項はセキュリティー・サービスやツールで報告されます。

デフォルトでは、{{site.data.keyword.security-advisor_short}} はすべての {{site.data.keyword.cloud_notm}} アカウントで有効になっています。 したがって、このサービスのインスタンスをプロビジョンする必要はありません。 {{site.data.keyword.security-advisor_short}} のインスタンスは、ダッシュボードの初期アクセス時か、初めて検出事項を報告する際に自動的に作成されます。 このサービスでは、アカウントごとに 90 日間で 18,000 個の検出事項 (1 日あたり約 200 個) まで可能です。 90 日の終わりに、検出事項はパージされます。 検出事項の限度はモニターされ、90 日より前にアカウントがこの限度に達すると、FIFO (先入れ先出し) モデルによって検出事項の合計が 50% に減らされます。 このサービスがアカウント削除通知を受け取ると、そのアカウントに関連した検出事項がすべてパージされます。 API を使用してアカウントに関する検出事項をすべて取得し、将来の利用や監査の目的で格納することができます。


## 主要な概念
{: #concepts}

{{site.data.keyword.security-advisor_short}} で作業する際に使用できるさまざまな概念について説明します。
{: shortdesc}

<dl>
  <dt>検出事項</dt>
    <dd>検出事項とは、ロー・イベントを処理すると作成される優先度の高いセキュリティー上の問題です。 検出事項は、問題について「誰が、何を、いつ、どこで」を明確にするために欠かせない重要な情報で構成されます。 セキュリティー管理者は、{{site.data.keyword.security-advisor_short}} の検出事項を基に、検出された状態に優先順位を付けて対処することができます。</br> 検出事項は少数で、小さいサイズですが、直ちに対処する必要がある重要な知見が含まれています。 例えば、サーバーがマルウェアに感染していたり、証明書の期限切れが迫っていたりする場合などが該当します。</dd>
  <dt>重要リスク指標 (KRI)</dt>
    <dd>重要リスク指標 (KRI) は、検出事項のリスクをセキュリティー・フォーカルに示すのに使用する指標です。 KRI は、エンタープライズ・クラウド・リソースのさまざまな領域で増えつつあるリスク・エクスポージャーの早期シグナルをセキュリティー・フォーカルに提供します。 サービスやワークロードの特定のセキュリティー制御について、検出事項の値がパフォーマンスの許容範囲外である場合に、KRI がトリガーされます。</dd>
  <dt>注記</dt>
    <dd>特定のタイプの検出事項は、注記として定義されます。 Grafeas はメタデータ情報を注記とオカレンスに分けます。 注記は特定のタイプのメタデータの概要です。 さまざまなプロバイダーが送信する検出事項のタイプごとに別個の注記を作成できます。</dd>
  <dt>オカレンス</dt>
    <dd>オカレンスは、プロバイダー固有の詳しい注記です。 オカレンスには、脆弱性の詳細、対処手順、その他の一般情報が含まれます。</dd>
  <dt>カード</dt>
    <dd>サービス・ダッシュボードで検出事項を視覚化するのに使用するメタデータは、注記の一種の <code>CARD</code> として定義されます。 {{site.data.keyword.security-advisor_short}} は、カードについて、以下の 3 つのタイプの KRI エレメントをサポートしています。 <ul><li>数値</li><li>明細</li><li>時系列</li></ul></dd>
  <dt>プロバイダー</dt>
    <dd>プロバイダーは、検出事項 (注記) のタイプを定義してから、検出事項のオカレンスをサービスに送信するツールまたはサービスです。</dd>
  <dt>サービス CRN</dt>
    <dd>サービス CRN は、検出事項に関係する {{site.data.keyword.cloud_notm}} サービスを示すものです。 例えば、証明書の有効期限の検出事項には、その検出事項を報告している Certificate Manager サービス・インスタンスのサービス・インスタンス ID または CRN が組み込まれます。</dd>
  <dt>リソース CRN</dt>
    <dd>リソース CRN は、検出事項に関係する具体的なリソースを示すものです。 ネットワーク分析で検出事項が報告される際には、Kubernetes クラスター CRN が組み込まれて、影響のあるクラスターやリソースが特定されます。</dd>
</dl>


## 高可用性と災害復旧
{: #ha-dr}

{{site.data.keyword.security-advisor_short}} は、可用性の高い、複数地域にまたがるサービスです。
{: shortdesc}

{{site.data.keyword.security-advisor_short}} は、現在ダラスとロンドンの両方の地域でサポートされています。 サポートされている各地域で、このサービスはいくつかの[アベイラビリティー・ゾーン](https://www.ibm.com/cloud/blog/announcements/improving-app-availability-multizone-clusters){: external}で実行されます。 {{site.data.keyword.security-advisor_short}} には、地域の災害復旧が備わっています。 このサービスは、3 時間以内に高速リストアできるバックアップ・データベースを保持します。 直前の 24 時間を除くすべてのサービス・データが提供されます。
