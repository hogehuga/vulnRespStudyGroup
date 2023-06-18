- source: https://www.cisa.gov/news-events/directives/emergency-directive-22-03
- translate: https://github.com/hogehuga/vulnRespStudyGroup
- lastupdate: 2023/06/18 JST

# 緊急指令
2022年05月18日

## VMwareの脆弱性を軽減する

このページには、サイバーセキュリティ・インフラストラクチャ・セキュリティ庁の緊急指令22-03「VMwareの脆弱性の軽減」のWeb対応版が含まれています。

米国法典タイトル44のセクション3553(h)では、既知の、又は合理的に疑われる情報セキュリティの脅威/脆弱性、または政府機関の情報セキュリティに対する重大な脅威を示す事件に対応して、国土安全保障長官に次の権限を与えています。情報システム（機関に代わって別の組織が使用または運用するシステムを含む）の運用に関して、収集/処理/保管/送信/配布するための法的措置を講じるよう、機関の長に緊急命令を発行する。情報セキュリティの脅威から情報システムを保護又は軽減する目的で、政府機関の情報を維持したり、その他の方法で政府機関の情報を維持したりします。[44USC§3553(h)(1)–(2)](http://uscode.house.gov/view.xhtml?req=(title:44%20section:3553%20edition:prelim)%20OR%20(granuleid:USC-prelim-title44-section3553)&f=treesort&edition=prelim&num=0&jumpTo=true)

2002年国土安全保障法第2205条第3項（修正版）では、この権限がサイバーセキュリティ・インフラセキュリティ庁長官に委任されています。[6USC§655(3)](http://uscode.house.gov/view.xhtml?req=(title:6%20section:655%20edition:prelim)%20OR%20(granuleid:USC-prelim-title6-section655)&f=treesort&edition=prelim&num=0&jumpTo=true)

連邦政府機関はこれらの指令に従う必要があります。[44USC§3554(a)(1)(B)(v)](http://uscode.house.gov/view.xhtml?req=(title:44%20section:3554%20edition:prelim)%20OR%20(granuleid:USC-prelim-title44-section3554)&f=treesort&edition=prelim&num=0&jumpTo=true)

これらの指令は、法的に定義された「国家安全保障システム」にも、国防総省や情報機関が運営するシステムにも適用されません。[44USC§3553(d)、(e)(2)、(e)(3)、(h)(1)(B)](http://uscode.house.gov/view.xhtml?req=(title:44%20section:3553%20edition:prelim)%20OR%20(granuleid:USC-prelim-title44-section3553)&f=treesort&edition=prelim&num=0&jumpTo=true)

## 背景

Advanced Persistent Threat(APT)アクターを含む脅威アクターは、次のVMware製品の脆弱性(CVE2022-22954およびCVE2022-22960)を悪用しています
:VMware Workspace ONE Access(Access)、VMware Identity Manager(vIDM)、VMwarev Realize Automation(vRA)、VMware Cloud Foundation、およびvRealize Suite Lifecycle Manager。
VMwareはこれらの脆弱性に対処するアップデートを2022年04月06日にリリースしましたが、攻撃者はアップデートをリバース　エンジニアリングし、アップデートのリリースから48時間以内にパッチが適用されていない影響を受けるVMware製品の悪用を開始することができました。

2022年05月18日、VMwareは2つの新しい脆弱性（CVE-2022-22972およびCVE-2022-22973）に対するアップデートをリリースしました。上記に基づいて、CISAは、脅威アクターが、同じ影響を受けるVMware製品内で新たにリリースされた脆弱性を悪用する機能が迅速に開発されることを想定しています。上記の脆弱性を悪用すると、攻撃者がサーバー側のテンプレートインジェクションをトリガーし、リモートでコードを実行される可能性があります(CVE-2022-22954)。権限を「root」に昇格します(CVE-2022-22960およびCVE-2022-22973)。認証を必要とせずに管理アクセスを取得できます(CVE-2022-22972)。

CISAは、これらの脆弱性は連邦文民行政府機関（Federal Civillian Executive Branch:FCEB）に容認できないリスクをもたらしており、緊急措置が必要であると判断しました。この判断は、実際の脅威アクターによる確認されたCVE-2022-22954およびCVE-2022-22960の悪用、CVE-2022-22972およびCVE-2022-22973の将来の悪用の可能性、影響を受けるソフトウェアが連邦企業内に蔓延していること、政府機関の情報システムが侵害される可能性が高い事、を基にしています。

CISAの拘束力のある運用指令[22-01](https://www.cisa.gov/news-events/directives/binding-operational-directive-22-01)および[19-02](https://www.cisa.gov/news-events/directives/binding-operational-directive-19-02)の要件は引き続き有効であることに注意してください。CVE2022-22954とCVE2022-22960は、それぞれ2022年04月14日と04月15日に、CISAの既知の悪用された脆弱性のカタログ（Catalog of Known Exploited Vulnerabilities:Catalog of KEVs）に追加されました。CISAは悪用の監視を継続し、[既知の悪用された脆弱性](https://www.cisa.gov/known-exploited-vulnerabilities)で定義されているしきい値を満たしたKEVをBOD22-01カタログに追加します。

## 必要なアクション

すべての連邦文民行政府機関は、次の措置を完了する必要があります。

**2022年05月23日 月曜日 午後05:00 EDTまでに:**

1. 影響を受けるVMware 製品[VMware Workspace ONE Access (Access)、VMware Identity Manager (vIDM)、VMware vRealize Automation (vRA)、VMware Cloud Foundation、および vRealize Suite Lifecycle Manager]の政府機関ネットワーク上のすべてのインスタンスを列挙します。
2. 上記の必要なアクション(1)に列挙されている、影響を受けるVMware製品のすべてのインスタンスについては、次のとおりです。
    1. https://www.vmware.com/security/advisories/VMSA-2022-0014.html で入手できるVMwareセキュリティlアドバイザリ VMSA-2022-0014 に従ってアップデートを展開します。
    2. または、アップデートを適用できるようになるまで、連邦機関のネットワークから削除してください。

製品がベンダーによってサポートされていない（サービス終了、製品寿命など）ためにアップデートが利用できない場合は、サポートされていない製品を連邦機関のネットワークから直ちに削除する必要があります。

3. さらに、インターネットからアクセス可能な、影響を受けるVMware製品のすべてのインスタンスについては、次のとおりです。
    1. 侵害を想定し、直ちに運用ネットワークから切断し、脅威探索活動（注:"condact threat hunt":脅威の兆候を発見し、対処する事を示している）を実施します。
    2. ステップ 3a(注：本翻訳では 3.1 相当) で特定された異常を直ちに CISA（central@cisa.dhs.gov）に報告してください。

政府機関は、異常が検出されずに脅威探索活動が完了し、アップデートが適用された後にのみ、これらの製品をネットワークに再接続できます。

**2022年05月24日 火曜日 午後12:00 EDTまでに:**

4. 以下に提供されているテンプレートを使用して、必須アクション 1 に列挙されているすべてのインスタンスのステータスをCyber​​Scopeにレポートします。
   - [緊急指令22-03 CyberScopeレポートテンプレート](https://www.cisa.gov/sites/default/files/2023-02/ED_22-03_CyberScope_Reporting_Template.xlsx) (XLSX, 883.57KB)

これらの必要なアクションは、政府機関の情報を収集/処理/保存/送信/配布/またはその他の方法で維持する、政府機関に代わって別の主体によって使用または運用される情報システムを含む、あらゆる情報システム内の政府機関の資産に適用されます。

サードパーティ環境でホストされている連邦情報システムの場合、各政府機関は、それらの環境（FedRAMP認定またはその他）でホストされている情報システムのインベントリを維持し、この指令に関連するステータスの最新情報を取得し、この指令への準拠を保証する責任があります。政府機関は、FedRAMPプログラム オフィスを通じて、FedRAMP認定クラウド サービス プロバイダー向けのこれらのアップデートを入手し、FedRAMP認定されていないサービス プロバイダーと直接連携する必要があります。

この指令に指定されている他のすべての規定は引き続き適用されます。

## CISAの行動

1. CISAは引き続きパートナーと協力して、これらの脆弱性に関連する積極的な悪用を監視し、必要に応じて政府機関に通知し、追加のガイダンスを提供します。
2. CISAは、この指令を遵守するのに十分な内部能力を持たない政府機関に技術支援を提供します。
3. CISAは2022年06月30日までに、国土安全保障長官、国家サイバー局長、行政管理予算局長、および連邦最高情報セキュリティ責任者に、省庁間の状況と未解決の問題を特定した報告書を提出する予定です。

## 期間

この緊急指令は、影響を受けるソフトウェアを運用しているすべての政府機関がこの指令に基づいて必要な措置をすべて実行したとCISAが判断するか、他の適切な措置によって指令が終了するまで有効です。

## 追加情報

以下については、CISAの[指令](https://www.cisa.gov/news-events/directives)ページにアクセスするか、以下にお問い合わせください。

- 一般情報、支援、および報告 –  [Cyber​​Directives@cisa.dhs.gov](maillto:CyberDirectives@cisa.dhs.gov)
- 潜在的な侵害の兆候を[報告する](https://www.cisa.gov/report)

