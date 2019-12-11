ペネトレーションテストについて
===
by [脆弱性診断士スキルマッププロジェクト](https://www.owasp.org/index.php/Pentester_Skillmap_Project_JP)


# はじめに

## 本ドキュメントの目的

コンピュータシステムに対して実施するセキュリティテストの1つとして「脆弱性診断」がよく知られています。「脆弱性診断」は[脆弱性診断士スキルマッププロジェクト](https://www.owasp.org/index.php/Pentester_Skillmap_Project_JP)でも紹介しているような脆弱性を発見するためのセキュリティテストの手法です。

一方で最近は「ペネトレーションテスト」を採用する組織や、ペネトレーションテストサービスを提供する事業者（テストベンダー）が増えてきました。

ただ、現状では「ペネトレーションテスト」という名称に共通認識がなく、テストベンダーによっては「脆弱性診断」のことを「ペネトレーションテスト」と呼んでいることもあり、テストを採用する組織が目的に合ったサービスを見分けることが難しくなっています。

本ドキュメントは「ペネトレーションテスト」の位置づけを明確にし、セキュリティテストを活用する組織が実施目的に合うサービスを選択できることを目的としています。

## ペネトレーションテストとは
「ペネトレーションテスト (Penetration Test / Testing）」とは、明確な意図を持った攻撃者にその目的が達成されてしまうかを検証するためのセキュリティテストの一種です。

ペネトレーションテストではその組織が持つすべてのシステム、もしくは指定されたシステム全体を対象として、実際の攻撃者が使用しているツールや脆弱性、ソーシャルエンジニアリングなどを利用して一定期間内に目的を達成できるかどうかの調査を行います。
テストを実施する際には遠隔操作を行う疑似マルウェアを用いたり、組織の内部ネットワークの端末やサーバーへの侵入を繰り返したり、Active Directoryなどのシステムへの攻撃を行い管理者権限を奪ったりすることもあります。

ペネトレーションテストはいわゆる脆弱性診断のようなWebアプリケーション単体やプラットフォーム単体のテストではなく、また網羅的に脆弱性の調査を行うわけではありません。

## 脆弱性診断士スキルマッププロジェクトについて
[日本セキュリティオペレーション事業者協議会](https://isog-j.org/)のセキュリティオペレーションガイドラインWG（WG1）と、OWASP Japan主催の共同ワーキンググループである 「[脆弱性診断士スキルマッププロジェクト](https://www.owasp.org/index.php/Pentester_Skillmap_Project_JP) （代表:上野宣）」では、脆弱性診断を行う個人の技術的な能力を具体的にすべく、脆弱性診断を行う技術者（以下、脆弱性診断士）のスキルマップと学習の指針となるシラバス、脆弱性診断を行うためのガイドライン、Webアプリケーションを安全に構築するために必要な要件定義書などを整備しています。


# 脆弱性診断とペネトレーションテストの違い
事業者がサービスとして提供している場合、「脆弱性診断」は、「セキュリティ診断」や「セキュリティ検査」、「脆弱性検査」などと同じサービス内容でもサービス事業者によっては呼称が異なることがあります。

## 目的
### 脆弱性診断
脆弱性やセキュリティ機能の不足を「網羅的に洗い出す」ことを目的とし、システムに内在するリスクをすべて洗い出します。

### ペネトレーションテスト
実際に「脆弱性を悪用する」ことで、明確な意図を持った攻撃者がその目的を達成することが可能であるかどうかを検証することを主眼とします。

----
## 手法
### 脆弱性診断
網羅的に脆弱性を洗い出すため、[ガイドライン](https://github.com/ueno1000/WebAppPentestGuidelines)等に従って定型的なテストケースに基づいた作業を行います。主に、脆弱性の有無を確認するために必要最低限の通信にとどめ、実際に被害が発生してしまうような調査を意図的に行うことはありません。

### ペネトレーションテスト
実際の攻撃者が使用しているツールや脆弱性の利用、ソーシャルエンジニアリングなど様々な手法を用いて一定期間内で目的を達成できるかの調査を行います。網羅的に脆弱性の調査を行うわけではありません。

ソーシャルエンジニアリングや物理面での調査などを実施するかどうかはテストベンダーによって異なり、実施手法は顧客と相談の上で決定します。また、外部からの侵入自体を試行する例や、侵入されたことを前提として内部からテストを実施する例もあります。


----
## 調査対象
### 脆弱性診断
システムを調査対象とし、指定されたWebアプリケーションやIPアドレスごとに作業をします。一般的に、調査対象と関連するシステムであっても、調査対象に指定されていないWebアプリケーションやIPアドレスに対しては、診断を行いません。

### ペネトレーションテスト
システム、人、組織、ルールを調査対象とし、その組織が持つすべてのシステム、もしくは指定されたシステム全体に対して作業をします。
新規に構築したシステムよりは、運用し始めて時間が経過しているシステムに対して実施することが効果的です。


----
## 結果・報告書
### 脆弱性診断
発見された脆弱性やセキュリティ機能の不足している一覧を、リスクの高いものから低いものまですべて報告書に記載します。

### ペネトレーションテスト
報告書へは、「目的達成までの侵入経路や行った攻撃シナリオ」や「シナリオ実行過程で使用した脆弱性や攻撃手法、セキュリティの問題」について記載します。

----
## ペネトレーションテストの費用感、期間の目安
脆弱性診断もペネトレーションテストも、対象とするシステムの規模や範囲、作業期間や掛ける労力によって費用が変わります。
一般的には、ペネトレーションテストの方が、より高度な技術が必要な分、脆弱性診断に比べて費用・期間ともに高コストになります。実施期間については1週間〜数ヶ月と、設定されたゴールや予算などによって大きく変わります。

年末から年度末にかけてはテストベンダーの繁忙期にあたります。実施希望時期が決まっている場合、早期に依頼することで、希望時期でのテスト実施が可能となります。

----
# ペネトレーションテスト実施の前提

## ペネトレーションテストを実施すべき組織
ペネトレーションテストはセキュリティシステム全体のテストであり、その運用状況なども含めたテストです。そのため、セキュリティ対策が十分でない組織よりも、セキュリティ対策のレベルがある程度成熟している組織が実施する方が効果が見込めます。
また、運用した結果顕在化する問題点もありますので、システム構築直後よりは一定期間運用したシステムを対象とした方が効果が見込めます。

自分たちの組織が下記に該当するようでしたらペネトレーションテストを実施すべきでしょう。
* セキュリティ対策のレベル
    * ウイルス対策ソフト、ファイアウォール以外のセキュリティ対策を導入している
    * 同業他社と同レベルのセキュリティ対策を実施している（参考：[組織の情報セキュリティ対策自己診断テスト　情報セキュリティ対策ベンチマーク：IPA 独立行政法人 情報処理推進機構](https://www.ipa.go.jp/security/benchmark/)）
    * 脆弱性診断を実施したことがある
* セキュリティ対策の運用状況
    * 十分なセキュリティ対策を実施している自信がある
    * 各種対策を導入しているが、役に立っていることをあまり実感していない
    * 組織のセキュリティ対策が機能しているか確認したい

## ペネトレーションテスト実施に関する注意事項
ペネトレーションテストでは実際の攻撃者と同様の攻撃を行います。攻撃者もペンテスター（ペネトレーションテストの実施者）もシステムや業務に影響がなるべく出ないような攻撃手法を選びますが、場合によってはシステムや業務への影響が避けられないこともあります。

テストによって各種システムなどにログが残る以外にも、下記のような影響が出ることがあります。

* テストに使用したツールなどが残存
* 監視機器や監視サービスからのアラート発報
* システム停止、高負荷
* システム上の情報や設定が変更される
* アカウントロック状態になる

ペネトレーションテストを受ける際には、これらの影響が出る可能性があることを考慮する必要があります。

## ペネトレーションテスト実施の頻度
ペネトレーションテストを実施すると、組織のセキュリティ対策の不備や運用の問題などさまざまな事項が判明します。そのため、実施後にはさまざまな改善を行う必要が生じます。
その改善策が十分機能しているかを確認するためにも、再びペネトレーションテストを実施する必要があります。また、改善した新たなセキュリティ対策がうまく運用されているかを確認するためにも**年に1度程度**のペネトレーションテストの実施が望ましいでしょう。


# ペネトレーションテスト実施時の検討事項

## 準備

ペネトレーションテストを実施する前に検討すべき点について説明します。

### ゴール設定（攻撃者・被害の想定）

ペネトレーションテストを受ける側は守るべき資産を把握しておくことが適切なゴールを設定する上では望ましいといえます。

対象が決まったら次に、攻撃者とその攻撃者が目的とする被害（ゴール）を想定します。例えば、以下のようなゴールがあります。

 * 外部公開サーバを踏み台とされ、内部システムの情報を奪取
 * マルウェアに感染したクライアント端末からのActive Directoryの管理者権限奪取
 * 特定サービスの本番系データベースからの情報奪取
 * 内部犯行による機密文書の外部への持出し

すべての想定ゴールを検証できることが理想ですが、こちらも期間やコストに影響するためシステムの重要度も勘案して、検証するゴールを選定してください。

### スコープ設定（対象システム）

テストの対象とするシステムの範囲を決めます。組織にあるすべてのシステムを対象範囲にするのか、あるいは一部のシステムに限定するのかを決定します。対象範囲を限定すればするほど、短期間・低コストで実施できますが、対象外のシステムの問題点は見つかりません。また、複数のシステムにまたがった問題点も見つからない可能性が高まります。

できるだけ広い範囲を対象とすることが望ましいですが、システムの重要度やコストも勘案し対象システムを決定してください。
なお、スコープにはパブリッククラウドなどのシステムも含める場合があります。

### レギュレーション

スコープとゴールの設定後、テストベンダーは実際にどのように疑似攻撃を行うかテストシナリオを検討し、円滑にテストができるよう計画を作成します。そのために必要な情報をテストベンダーに提供してください。例えば、以下のような情報です。

 * 対象システムのIPアドレスやドメインの範囲
 * 禁止事項
 * 異常発生時の緊急連絡先
 * ユーザーアカウント情報
 * 実施時間
 * プラットフォーム環境の情報（クラウド利用有無など）

特に、禁止事項は重要です。実際の攻撃に近いテストであるとはいえ、通常業務を阻害するような影響はできるだけ避けるべきです。あらかじめ悪影響が予想できる行為は禁止事項としてテストベンダーと共有しておくことで、このようなリスクを低減できます。

ただし、あまりにも禁止事項が厳しい場合、一部のテストを実施できなくなることがあります。例えばアカウントロックを禁止事項とした場合は、既に誰かが連続して認証に失敗していると意図せずアカウントロックしてしまう可能性があるため、事実上認証試行を禁止することになります。そのため、テストベンダーと事前によく協議してレギュレーションを合意してください。

テストは期間を限定して行うことが一般的です。一方、実際の攻撃者は期間の制約なく攻撃が可能です。この差を埋めるために、ある程度時間をかければ収集されてしまう情報（既知の脆弱性情報、システム構成、メールアドレスの一覧など）についてはあらかじめテスト担当者に提供してテストを効率化する場合があります。こちらもテストベンダーと協議し、必要に応じて情報を提供してください。

### バックアップなど

テストベンダーは、対象を意図的に破壊や停止させるテストは行いません（DoSがゴールの場合以外）。ただし、攻撃は通常とは異なる行為であるため予期しないことが起こる可能性があり、影響が起きないことを100%保証することはできません。万が一の場合に備え、システムの再起動や、バックアップからの復旧手順について事前に確認し備えておいてください。

本番システムではなく検証環境に対してテストを行うことも考えられます。その際は、できるだけ本番システムと同等の状態を再現することが望ましいです。例えば、対象システム内に保存されているそれまでのアクセスログや操作履歴、作業途中の一時ファイルなどが侵入の糸口になることが多々あります。これらを含め本番システムを可能な限り再現することで、検証環境に対してテストを行う効果が高まります。

## 実施中に行うこと

ベンダーのテストを見守り、何らかの不都合があった場合の調整を行います。リスクの高い疑似攻撃の実施可否を相談されたり、社内の運用チームからの問い合わせを受けることもあるでしょう。万が一業務に影響が出た場合、テストの中断や中止をするか判断してください。

## 実施後に行うこと

ペネトレーションテスト実施後は、その結果を評価し、問題点の改善計画を立て、対策を進めていきます。

### 脆弱性の対策

テストベンダーから報告される問題点は、主に次の２種類です。

#### システムの脆弱性

テスト対象システムに残存していたシステムの脆弱性です。例えば、脆弱性のあるバージョンのソフトウェアを使用している問題、設定ミス、Webアプリケーションの脆弱性などがこれにあたります。場合によっては未知の脆弱性が見つかることもあります。
前述の通り、システムの脆弱性すべてが網羅されて報告されるわけではなく、テストで設定したゴールにたどり着くために有用だった脆弱性が報告されます。加えて、ゴールとは関係しないものでも、テスト中に偶然見つけてしまった脆弱性も報告されることがあります。

#### 運用の脆弱性

継続して運用していたことで初めて生まれる、または見つかる脆弱性です。例えば、パスワードの使い回しや容易に推測が可能なパスワードを設定してしまった、機密情報が書かれた手順書や設定ファイルがアクセス制限や暗号化されずにサーバーに置かれてしまった、などです。

脆弱性が報告された場合、その内容を評価して対策が必要です。これらの脆弱性の対策は、従来の脆弱性診断で報告された問題への対処手順と同じです。まずは現状の脆弱な状態を解消する必要があります。それぞれの脆弱性に対して、危険度や対策コストから対応の要否と優先度を検討し、対策を行ってください。さらに、人が原因で生まれた運用の脆弱性には、人のミスをシステム的に検出・防止する仕組みの導入や、ユーザーの教育も検討する必要があるでしょう。

### サイバーレジリエンス能力の評価

ペネトレーションテストの効果はこれだけではありません。さらにもう１つ、最も重要な評価ポイントがあります。それが、サイバーレジリエンス能力の評価です。サイバーレジリエンス能力とは、侵入による組織への影響を最小化し早急に平常状態に戻せる能力です。

テストの実施によって、通常ではあり得ない攻撃パケットがネットワーク上を飛び交い、様々なサーバーや機器に攻撃の痕跡を示す不審なログが残るはずです。あなたの組織は、どの攻撃を検知できましたか？検知したのは攻撃が行われてどのくらい経ってからですか？被害の拡大を食い止める対応ができていましたか？組織にはこのような対応能力が必要です。

この能力を評価するには、個々のシステムの検出状況だけではなく、運用監視チームやCSIRTの対応状況まで含め、組織全体の対応に課題がないか検証すべきです。「侵入されないシステム」を作ることは重要ですが、「侵入された前提の対応」も重要度を増してきています。

* CSIRTの構築・運用についてはJPCERT/CCの[CSIRTマテリアル](https://www.jpcert.or.jp/csirt_material/)も参考になります。

# ケーススタディ

## 報告書に記載されるゴール達成までのシナリオ例

あらかじめ設定したゴールに対して、テストベンダーがゴールを達成できた場合、「目的達成までの侵入経路や行った攻撃シナリオ」や「シナリオ実行過程で使用した脆弱性や攻撃手法、セキュリティの問題」が報告書に記載されます。ここでは実際にテストで利用されたシナリオ例を紹介します。
なお調査時には、様々な攻撃手法によりゴールを達成可能か試行錯誤していますが、実施内容が全て報告書に記載されるわけではなく、ゴール達成に関連した手法のみが記載されることが一般的です。

### ゴール
マルウェアに感染したクライアント端末からActive Directoryの管理者権限を奪取すること

### 想定している攻撃者
インターネット上の攻撃者

### テストの起点
マルウェアに感染したことを想定した貸与されたクライアント端末

### スコープ
サーバーセグメント
クライアント端末セグメント

### 事前準備
Active Directoryのアカウント
クライアント端末

### シナリオ
1.貸与されたクライアント端末および貸与されたアカウントを用いて、次の情報収集を実施

- ドメインの管理者アカウントのユーザー名(Domain Adminに所属するアカウント)
- ドメインアカウントのユーザー名
- ログオンスクリプトなどのドメイン上の公開リソース
- クライアント端末上に存在するアカウントのユーザー名
- クライアント端末上のOS・アプリケーション・サービスの脆弱性

2.情報収集で得た権限設定に不備のあるアプリケーションを利用し、クライアント端末のローカル管理者権限を取得

3.取得したローカル管理者権限を利用し、クライアント端末上に残存する認証情報を調査し、次の箇所から管理用に利用されているドメインアカウントの認証情報を取得
- メモリ上の認証情報
- タスクスケジューラで登録されているスクリプトにハードコードされた認証情報

4.3の工程で取得した認証情報を用いて、ファイルサーバーへアクセスし、次のファイルを調査しドメインの管理者アカウントの認証情報を取得
- 認証情報管理台帳
- プログラムソース
- 運用手順書
- 管理用バッチファイル
- 作業ログ

5.取得した認証情報を用いてドメインコントローラーへドメインの管理者アカウントで侵入

----
## ペネトレーションテスト実施の事例
​
本事例では、年に一度、計3回のペネトレーションテストを実施した企業Aの事例を紹介します。
​
### 背景
企業Aは、約1000人の社員が働いています。拠点が複数に分かれており、各拠点でネットワークを分けていますが、一部ではつながっています。
​
自社のシステム担当部門が主にセキュリティ対策の検討や運用の一部を行っています。主要な拠点には自社の担当者を置き、外部からの攻撃に関するログ監視など一部の運用業務については、外部の業者に委託しています。
​
以前に外部から攻撃を受けて情報漏えいの被害が発生したことから、主担当者やその他社員のセキュリティ意識は非常に高いものでした。
​
### 1回目の実施内容検討
ペネトレーションテストを実施したいということで担当者から話を聞いたところ、企業Aではインターネットに公開されているサーバーを対象に、以前から脆弱性診断を実施しており、発見された脆弱性への対策も行われていました。そのため、今回は標的型攻撃への耐性を評価することを希望されていました。
​
そこで、社員の端末が感染した前提で重要情報の持出しができるかどうかを確認するため、社内ネットワークからペネトレーションテストを実施することになりました。
​
テストは、複数ある拠点のうち、最も主要な拠点の端末が感染した前提で実施しました。
​
### 1回目のテスト結果
実施した結果、以下の問題が検出されました。
​
 * 1-1. C2サーバーから端末を遠隔操作可能
 * 1-2. 複数台の端末において、ビルトインアドミニストレータの認証情報が共通
 * 1-3. ドメイン管理者アカウントの認証情報が取得可能
 * 1-4. C2サーバーへ重要情報の持出しが可能
​
テスト結果は、標的型攻撃に対する改善が必要な状況でした。1-3については早急に対策を行いましたが、その他の問題についてはすぐに対策することが難しく、軽減策等を検討することになりました。
​
なお、報告会には別拠点のシステム担当者も参加しており、同様の問題点があれば対策を行うという話でした。
​
### 2回目の実施内容検討
翌年、担当者から話を聞いたところ、「インターネットに公開しているサーバーは侵入されない想定だが、もし、侵入された場合には、どのような被害が発生し、それを検知できるのかを知りたい。」ということでした。
​
そこで、公開しているサーバーに侵入された前提で、社内ネットワークから重要情報の持出しができるかどうかをチェックするペネトレーションテストを実施することになりました。
​
テストは、個人情報を取り扱うWebサーバーが侵入された前提で実施しました。
​
### 2回目のテスト結果
実施した結果、以下の問題が検出されました。
​
 * 2-1. Webサーバーを遠隔操作可能
 * 2-2. 他サーバーへログインするための認証情報が取得可能
 * 2-3. アクセスすることを想定していないネットワークにアクセスが可能
​
テスト結果は、Webサーバーに侵入された場合に遠隔操作が行われ、他サーバーにも侵入されることで重要情報が持出し可能という状況でした。そして、それを検知することができない状況でした。
​
メンテナンス時に利用する認証情報をサーバー上に配置していたことが問題2-2の原因でしたが、他サーバーへの攻撃が容易になってしまうため、認証情報を配置しないようにしました。問題2-3の原因はアクセス制御の不備だったので早急に対応することになりました。
また、これらの攻撃を検知できるように、検知設定の見直しを行いました。
​
### 3回目の実施内容検討
さらに翌年、担当者から話を聞いたところ、「以前検出された問題点が適切に対策されたのか、その対策が全社にも行われたのかを確認したい。」との要望があり、再度社内ネットワークからのペネトレーションテストを実施したいということでした。
​
そこで、1回目にテストを実施した際と同じ拠点に加え、2番目に主要な拠点からもテストを実施することになりました。
​
### 3回目のテスト結果
実施した結果、1回目と同じ拠点からのテストでは、以下の問題が検出されました。
​
 * 3-1. C2サーバーから端末を遠隔操作可能
 * 3-2. C2サーバーへ重要情報の持出しが可能
​
3-1と3-2について確認したところ、緩和策が取られており、問題無いという判断でした。その他問題については対策されていました。
​
2番目に主要な拠点からのテストでは、以下の問題が検出されました。
​
 * 3-1. C2サーバーから端末を遠隔操作可能
 * 3-2. C2サーバーへ重要情報の持出しが可能
 * 3-3. ローカル管理者のパスワードが取得可能
​
1回目の実施結果を基に対策されているため、最も主要な拠点とほぼ同じ結果となりました。
しかしながら、運用の不備により、ローカル管理者のパスワードが漏えいしてしまう可能性がありました。そのため、早急にこの問題について対策を行いました。
​
### ポイント
本事例は、目的がはっきりしており、ペネトレーションテストを非常に有効活用していました。その結果、高いレベルで対策が行われている状態となりました。
​
本事例のポイントは、以下であると考えます。
​
 * 自組織でどのようなテストが必要であるかを認識できていたこと
 * 前回の指摘についての対策が適切であったこと
 * 視点を変えたテストを実施することで、新たなリスクが見えたこと
 * 前回結果が組織全体の改善へとつながったこと


# TLPTについて

TLPT(Threat-Led Penetration Test)は、「脅威ベースのペネトレーションテスト」と訳されており、高度なセキュリティが求められる業界における実効性の高いペネトレーションテストの活用方式として、注目を集めています。

従来のペネトレーションテストでは、汎用的な脅威による脅威シナリオ(インターネットから特定のサーバに侵入できるかなど)を想定しテストを行い、主にシステムや運用の問題点を評価することを目的としています。それに対してTLPTはサイバーレジリエンス能力を評価し、高めていくことを目的とします。Red Teamの現実的な攻撃に対して、Blue Teamやシステム担当だけではなく、CSIRTや経営層を含めた組織全体のインシデントレスポンスをテストし、攻撃被害からの復旧や事業の継続が適切にできるかどうかを評価します。

金融機関向けには、関連するドキュメントが金融庁から公開されています。
- 諸外国の脅威ベースのペネトレーションテスト(TLPT)に関する報告書公表について
https://www.fsa.go.jp/common/about/research/20180516.html

- 「脅威ベースのペネトレーションテスト」及び「サードパーティのサイバーリスクマネジメント」に関するG7の基礎的要素の公表について
https://www.fsa.go.jp/inter/etc/20181015/20181015.html

TLPTで求められる具体的な実施内容は、『「脅威ベースのペネトレーションテスト」及び「サードパーティのサイバーリスクマネジメント」に関するG7の基礎的要素の公表について』において「TLPTのG7基礎的要素」として以下が定義されています。

1. スコープ設定とリスクマネジメント
2. リソース確保
3. 脅威情報
4. ペネトレーションテスト
5. 完了および改善
6. 類型化したデータ
※仮訳より引用

1.スコープ設定とリスクマネジメント
テストの対象となる範囲を定義します。ベンダーなどを含む重要な役割やサービスの担当者やプロセス、技術も明確にし、テスト実施によるリスクを踏まえて、リスクを適切に管理する必要があります。

2.リソース確保
適切なテストを実施するために、Threat Intelligence ProviderやPenetration Test Providerの選定は実績などを参考にして慎重に行う必要があります。

3.脅威情報
脅威情報の収集・分析を行い、脅威シナリオなどを作成します。

4.ペネトレーションテスト
脅威シナリオに基づきRed Teamが実践的なテストを実施します。Blue Teamは、Red Teamの攻撃を検知・ブロックします。White Teamは、Red TeamおよびBlue Teamへの調整を行い、適切にテストが実行できるようにリスクコントロールを行います。

5.完了および改善
Blue Teamでの検知・ブロック結果なども含めてペネトレーションテストの結果を分析し、サイバーレジリエンス能力を高めるための改善策を作成します。

6.類型化したデータ
業界全体のサイバーレジリエンス能力の改善に貢献するために、各機関の間で類型化したデータを共有します。
