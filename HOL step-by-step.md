![Microsoft Cloud Workshop](images/ms-cloud-workshop.png)

management and security Hands-on lab  
October 2022

<br />

### Contents

- [Exercise 1: Azure ロールの割り当て](#exercise-1-azure-ロールの割り当て)

  - [Task 1: サブスクリプションへのセキュリティ管理者の追加](#task-1-サブスクリプションへのセキュリティ管理者の追加)

  - [Task 2: リソース グループへの仮想マシンの管理者ログインの追加](#task-2-リソース-グループへの仮想マシンの管理者ログインの追加)

- [Exercise 2: 正常性アラートの構成](#exercise-2-正常性アラートの構成)

  - [Task 1: サブスクリプションへのセキュリティ管理者の追加](#task-1-サービス正常性アラートの構成)

  - [Task 2: リソース正常性アラートの構成](#task-2-リソース正常性アラートの構成)

- [Exercise 3: Azure リソースの保護](#exercise-3-azure-policy-による管理ガバナンスの実装)

  - [Task 1: Microsoft Defender for Cloud の有効化](#task-1-microsoft-defender-for-cloud-の有効化)

- [Exercise 4: Azure Policy による管理ガバナンスの実装](#exercise-4-azure-policy-による管理ガバナンスの実装)

  - [Task 1: Microsoft Defender for servers の評価ポリシーの作成](#task-1-microsoft-defender-for-servers-の評価ポリシーの作成)

  - [Task 2: 展開できる仮想マシン SKU の設定ポリシーの作成](#task-2-展開できる仮想マシン-sku-の設定ポリシーの作成)

- [Exercise 5: 仮想マシンの展開とネットワークの構成](#exercise-5-仮想マシンの展開とネットワークの構成)

  - [Task 1: 仮想マシンの展開](#task-1-仮想マシンの展開)

  - [Task 2: 仮想マシンのディザスター リカバリー構成](#task-2-仮想マシンのディザスター-リカバリー構成)

  - [Task 3: 仮想ネットワーク ピアリングの構成](#task-3-仮想ネットワーク-ピアリングの構成)

- [Exercise 6: 仮想マシンの構成](#exercise-6-仮想マシンの構成)

  - [Task 1: 仮想マシンの監視設定](#task-1-仮想マシンの監視設定)

  - [Task 2: Microsoft Defender for Endpoint のインストール](#task-2-microsoft-defender-for-endpoint-のインストール)

  - [Task 3: 更新プログラムの管理](#task-3-更新プログラムの管理)

  - [Task 4: 仮想マシンの Windows Firewall の構成](#task-4-仮想マシンの-windows-firewall-の構成)

  - [Task 5: 仮想マシンの操作（ファイル作成、ブラウジング、ログオン失敗）](#task-5-仮想マシンの操作ファイル作成ブラウジングログオン失敗)

- [## Exercise 7: ネットワーク診断の設定と監視](#exercise-7-ネットワーク診断の設定と監視)

  - [Task 1: NSG フロー ログの収集](#task-1-nsg-フロー-ログの収集)

  - [Task 2: 接続モニターの作成](#task-2-接続モニターの作成)

  - [Task 3: NSG 診断による通信状況の確認](#task-3-nsg-診断による通信状況の確認)

- [Exercise 8: テスト フェールオーバーの実行](#exercise-8-テスト-フェールオーバーの実行)

  - [Task 1: テスト用の仮想ネットワークの作成](#task-1-テスト用の仮想ネットワークの作成)

  - [Task 2: テスト フェールオーバーの実行](#task-2-テスト-フェールオーバーの実行)

  - [Task 3: テスト フェールオーバーのクリーンアップ](#task-3-テスト-フェールオーバーのクリーンアップ)

- [Exercise 9: 仮想マシンの監視](#exercise-9-仮想マシンの監視)

  - [Task 1: 仮想マシンの分析情報の確認](#task-1-仮想マシンの分析情報の確認)

  - [Task 2: ログ クエリによるデータ分析とアラート作成](#task-2-ログ-クエリによるデータ分析とアラート作成)

<br />
<hr />

## 使用する環境

<img src="images/azure-resources.png" />

<br />
<hr />

## Exercise 1: Azure ロールの割り当て

<img src="images/exercise-1.png" />

<br />

### Task 1: サブスクリプションへのセキュリティ管理者の追加

- Azure ポータルのトップ画面で **サブスクリプション** をクリック

  <img src="images/role-assignment-01.png" />

- サブスクリプションのリストから使用するサブスクリプションを選択

  <img src="images/role-assignment-02.png" />

- **アクセス制御 (IAM)** を選択し、「**＋ 追加**」 - 「**ロールの割り当ての追加**」をクリック

  <img src="images/role-assignment-03.png" />

- 検索ボックスに **セキュリティ** と入力

  <img src="images/role-assignment-04.png" />

- 抽出された結果から「**セキュリティ管理者**」を選択し「**次へ**」をクリック

  <img src="images/role-assignment-05.png" />

- アクセスの割り当て先に **マネージド ID** を選択し「**メンバーを選択する**」をクリック

  <img src="images/role-assignment-06.png" />

- **ユーザー割り当てマネージド ID** を選択し、表示されるマネージド ID をクリック

  選択したメンバーにマネージド ID が表示されていることを確認し「**選択**」をクリック

  <img src="images/role-assignment-07.png" />

  ※ マネージド ID は事前に使用する環境で作成済み

- メンバーに選択したマネージド ID が表示されていることを確認し「**次へ**」をクリック

  <img src="images/role-assignment-08.png" />

- 内容を確認し「**レビューと割り当て**」をクリック

  <img src="images/role-assignment-09.png" />

- **アクセス制御** 画面で「**ロールの割り当て**」タブを選択

  サブスクリプションの **セキュリティ管理者ロール** へユーザーが追加されていることを確認

  <img src="images/role-assignment-10.png" />

<br />

### Task 2: リソース グループへの仮想マシンの管理者ログインの追加

- リソース グループの管理ブレードを表示し「**アクセス制御 (IAM)**」を選択

  「**＋ 追加**」 - 「**ロールの割り当ての追加**」をクリック

  <img src="images/role-assignment-11.png" />

- 検索ボックスに **仮想マシン** と入力

  抽出された結果から「**仮想マシンの管理者ログイン**」を選択し「**次へ**」をクリック

  <img src="images/role-assignment-12.png" />

- アクセスの割り当て先に **ユーザー、グループ、またはサービス プリンシパル** を選択し「**メンバーを選択する**」をクリック

  <img src="images/role-assignment-13.png" />

- ロールに追加するユーザーを選択

  <img src="images/role-assignment-14.png" />

- 「**レビューと割り当て**」をクリックし、ロールへユーザーを追加

  <img src="images/role-assignment-15.png" />

- **アクセス制御** 画面で「**ロールの割り当て**」タブを選択

  リソース グループの **仮想マシンの管理者ログイン** ロールへユーザーが追加されていることを確認

  <img src="images/role-assignment-16.png" />

<br />

### 参考情報
- [Azure 組み込みロール](https://docs.microsoft.com/ja-jp/azure/role-based-access-control/built-in-roles)

- [セキュリティ管理者](https://docs.microsoft.com/ja-jp/azure/role-based-access-control/built-in-roles#security-admin)

- [仮想マシンの管理者ログイン](https://docs.microsoft.com/ja-jp/azure/role-based-access-control/built-in-roles#virtual-machine-administrator-login)

<br />
<hr />

## Exercise 2: 正常性アラートの構成

<img src="images/exercise-2.png" />

<br />

### Task 1: サービス正常性アラートの構成

- Azure ポータルのトップ画面から **検索バー** のテキストボックスに「**正常性**」と入力

- 表示される候補より「**サービス正常性アラートの作成**」を選択

  <img src="images/service-health-alert-01.png" />

- 「**＋ サービス正常性**」をクリック

  <img src="images/service-health-alert-02.png" />

- **アラートの対象** セクションで **サブスクリプション**、**サービス**、**リージョン** を選択

  <img src="images/service-health-alert-03.png" />

  ※ サブスクリプション、リージョンはワークショップで使用中のものを選択

  ※ サービスはすべて選択

- **Service Health の基準** セクションの **イベントの種類** で「**サービスの問題**」、「**計画メンテナンス**」を選択

  <img src="images/service-health-alert-04.png" />

- **アクション** セクションの **アクション グループの追加** をクリック

  <img src="images/service-health-alert-05.png" />

  - **アクション グループの選択** ペインで「**＋ アクション グループの作成**」をクリック

    <img src="images/select-action-group-01.png" />
  
  - 「**基本**」タブで必要項目を設定し「**次へ: 通知 >**」をクリック

    - **プロジェクトの詳細**

      - **サブスクリプション**： ワークショップで使用中のサブスクリプションを選択

      - **リソース グループ**： ワークショップで使用中のリソース グループを選択

      - **リージョン**： Global（既定）

    - **インスタンスの詳細**

      - **アクション グループ名**： ag-MCW（任意）

      - **表示名**： ag-MCW（任意） ※ アクション グループ名が 12 文字以上の場合は 12 文字までに省略

        <img src="images/action-group-01.png" />

  - 「**通知**」タブで必要項目を設定し「**次へ: アクション >**」をクリック

    - **通知の種類** で **電子メール/SMS/プッシュ/音声** を選択

    - **電子メール** を チェックし、任意のメール アドレスを入力

      <img src="images/action-group-02.png" />

    - 通知の **名前** に **e-mail** と入力

      <img src="images/action-group-03.png" />

  - 「**アクション**」タブは既定のまま（設定は行わず）「**次へ: タグ >**」をクリック

    <img src="images/action-group-04.png" />

  - 「**タグ**」タブは既定のまま（設定は行わず）「**確認および作成**」をクリック

    <img src="images/action-group-05.png" />

  - 設定項目を確認し「**作成**」をクリック

    <img src="images/action-group-06.png" />

- 作成したアクション グループが追加されていることを確認

  <img src="images/service-health-alert-06.png" />

- **アラート ルールの詳細** セクションの構成

  - **アラート ルール名**： alert-Service-Health（任意）

  - **リソース グループ**： ワークショップで使用中のリソース グループを選択

  - **作成時にアラート ルールを有効にする**： オン

    <img src="images/service-health-alert-07.png" />

- 内容を確認し「**アラート ルールの作成**」をクリック

  <img src="images/service-health-alert-08.png" />

<br />

### Task 2: リソース正常性アラートの構成

- **リソース正常性** を選択し「**＋ リソース正常性アラートの追加**」をクリック

  <img src="images/resource-health-01.png" />

- Reasource Health アラート ルールの作成

  - **アラートの対象**

    - **サブスクリプション**： ワークショップで使用中のサブスクリプションを選択

    - **リソースの種類**： Virtual machine を選択

    - **リソース グループ**： ワークショップで使用中のリソース グループを選択 / 将来のすべてのリソース グループを含める

    - **リソース**： すべて選択済み / 今後すべてのリソースを含める

      <img src="images/resource-health-02.png" />

  - **アラートの条件**

    - **イベントの状態**： すべて選択済み

    - **現在のリソースの状態**： すべて選択済み

    - **以前のリソースの状態**： ４個を選択済み

    - **理由の種類**： すべて選択済み

      <img src="images/resource-health-03.png" />

  - **アクション**

    - 「**アクション グループの追加**」をクリックし、先の手順で作成したアクション グループを選択

      <img src="images/select-action-group-02.png" />
    
    - アクション グループが追加されたことを確認

      <img src="images/service-health-alert-06.png" />

  - **アラート ルールの詳細**

    - **アラート ルール名**： alert-Resource-Health（任意）

    - **リソース グループ**： ワークショップで使用中のリソース グループを選択

    - **作成時にアラート ルールを有効にする**： オン

      <img src="images/resource-health-04.png" />

- 内容を確認し「**アラート ルールの作成**」をクリック

  <img src="images/resource-health-05.png" />

<br />

## Exercise 3: Azure リソースの保護

<img src="images/exercise-3.png" />

<br />

### Task 1: Microsoft Defender for Cloud の有効化

- Azure ポータルのトップ画面から ツール に表示される Microsoft Defender for Cloud をクリック

  <img src="images/defender-for-cloud-01.png" />

- **環境設定** ページを表示し、保護を行うサブスクリプションを選択

  <img src="images/defender-for-cloud-02.png" />

- **サーバー** の「**プランの変更**」をクリック

- **Microsoft Defender for servers プラン 2** が選択されていることを確認

  <img src="images/defender-for-cloud-03.png" />

- **サーバー** の状態 **オン** にし「**保存**」をクリック

  <img src="images/defender-for-cloud-04.png" />

<br />

## Exercise 4: Azure Policy による管理ガバナンスの実装

<img src="images/exercise-4.png" />

<br />

### Task 1: Microsoft Defender for servers の評価ポリシーの作成

- Azure ポータルのトップ画面から **検索バー** のテキストボックスに「**ポリシー**」と入力

- 表示される候補より「**ポリシー**」を選択

  <img src="images/azure-policy-01.png" />

- **定義** を選択し、検索のテキスト ボックスに「**Defender for Endpoint**」と入力

- 抽出された結果から「**Windows 仮想マシンに Microsoft Defender for Endpoint エージェントをデプロイする**」をクリック

  <img src="images/azure-policy-02.png" />

- ポリシー定義の画面で「**割り当て**」をクリック

  <img src="images/azure-policy-03.png" />

- **スコープ** の **...** をクリックしポリシーを割り当てるスコープを指定

  <img src="images/azure-policy-04.png" />

  - **サブスクリプション**: ワークショップで使用中のサブスクリプションを選択

  - **リソース グループ**: ワークショップで使用中のリソース グループを選択

    <img src="images/azure-policy-05.png" />

- 「**修復**」タブを選択

  <img src="images/azure-policy-06.png" />

- マネージド ID の選択

  - **マネージド ID の種類**: ユーザー割り当てマネージド ID

  - **スコープ**: ワークショップで使用中のサブスクリプション

  - **既存のユーザー割り当て ID**: id-cloudworkshop（事前に作成済みのマネージド ID）

    <img src="images/azure-policy-07.png" />

- 「**確認および作成**」をクリック

- 「**作成**」をクリック

  <img src="images/azure-policy-08.png" />

<br />

### Task 2: 展開できる仮想マシン SKU の設定ポリシーの作成

- **定義** を選択し、検索のテキスト ボックスに「**許可**」と入力

- 「**許可されている仮想マシン サイズ SKU**」をクリック

  <img src="images/azure-policy-09.png" />

- 「**割り当て**」をクリック

  <img src="images/azure-policy-10.png" />

- スコープにワークショップで使用中のサブスクリプション、リソース グループを指定し「**次へ**」をクリック

  <img src="images/azure-policy-11.png" />

- 「**許可されているサイズ SKU**」に展開可能な仮想マシンのインスタンス サイズを指定

  <img src="images/azure-policy-12.png" />

  ※ Standard_B2ms, Standard_B2s, Standard_F2s-v2, Standard_D2s_v3 を選択

- 「**確認および作成**」をクリック

- 指定した内容を確認し「**作成**」をクリック

  <img src="images/azure-policy-13.png" />

<br />

### 参考情報

- [組み込みのポリシー定義](https://docs.microsoft.com/ja-jp/azure/governance/policy/samples/built-in-policies)

<br />
<hr />

## Exercise 5: 仮想マシンの展開とネットワークの構成

<img src="images/exercise-5.png" />

<br />

### Task 1: 仮想マシンの展開

- Azure Portal のトップ画面上部の「リソースの作成」をクリック

  <img src="images/create-resources.png" />

- 仮想マシンの 「**作成**」 をクリック

  <img src="images/virtual-machine-01.png" />

- 仮想マシンの作成

  - 「**基本タブ**」

    - プロジェクトの詳細

      - **サブスクリプション**: ワークショップで使用中のサブスクリプション

      - **リソース グループ**: ワークショップで使用中のリソース グループ

    - インスタンスの詳細

      - **仮想マシン名**: vm1（任意）

      - **地域**: 仮想ネットワーク（vnet-spoke-1）と同じ地域を選択

      - **可用性オプション**: 可用性ゾーン

      - **可用性ゾーン**: ゾーン 1

      - **セキュリティの種類**: Standard

      - **イメージ**: Windows Server 2022 Datacenter - Gen2

      - **VM アーキテクチャ**: x64

      - **Azure Spot 割引で実行する**: オフ

      - **サイズ**: Standard_B2ms

    - 管理者アカウント

      - **ユーザー名**: AzureUser（任意）

      - **パスワード**: 任意（12 ～ 123 文字、英語小文字、大文字、数字、特殊文字のうち３つを含める必要あり）

    - 受信ポートの規則

      - **パブリック受信ポート**: なし

    - ライセンス

      - **既存の Windows Server ライセンスを使用しますか**: オフ

        <br />

      <img src="images/virtual-machine-02.png" />

      ※ 仮想マシンのサイズ選択では、ポリシーで許可した SKU のみが表示されることを確認

      <img src="images/select-vm-sku.png" />


  - 「**ディスク**」タブ

    - ディスクのオプション

      - **OS ディスクの種類**: Standard SSD

        <br />

      <img src="images/virtual-machine-03.png" />

  - 「**ネットワーク**」タブ

    - ネットワーク インターフェイス

      - **仮想ネットワーク**:

      - **サブネット**: Subnet-1

      - **パブリック IP**: なし

      - **NIC ネットワーク セキュリティ グループ**: Basic

      - **パブリック受信ポート**: なし

      - **VM が削除されたときに NIC を削除する**: オン

    - 負荷分散

      - **負荷分散のオプション**: なし

        <br />

      <img src="images/virtual-machine-04.png" />

  - 「**管理**」タブ

    - 自動シャットダウン

      - **自動シャットダウンを有効にする**: オン

        ※その他は既定の設定

      <img src="images/virtual-machine-05.png" />

  - Monitoring、詳細、タグは既定の設定のまま「**確認および作成**」をクリック

  - 指定した内容を確認し「**作成**」をクリック

    <img src="images/virtual-machine-06.png" />
  
<br />

### Task 2: 仮想マシンのディザスター リカバリー構成

- 仮想マシンの管理ブレードへ移動し **ディザスター リカバリー** を選択

  <img src="images/vm-zone-dr-01.png" />

- **可用性ゾーン間のディザスター リカバリーを行いますか** に **はい** を選択し「**次へ: 詳細設定**」をクリック

  <img src="images/vm-zone-dr-02.png" />

- 設定の内容を確認し「**次へ: レプリケーションを確認して開始する**」をクリック

  ※ 設定は既定のまま、Recovery Services コンテナーや Automation アカウントが作成されることを確認

  <img src="images/vm-zone-dr-03.png" />

- 「**レプリケーションの開始**」をクリック

  <img src="images/vm-zone-dr-04.png" />

  ※ 最初のレプリケーションの完了まで 20 分ほどかかるため次のタスクを実行

<br />

### Task 3: 仮想ネットワーク ピアリングの構成

- リソース グループ内の仮想ネットワーク（vnet-spoke-1）を選択

- **ピアリング** を選択し「**＋ 追加**」をクリック

  <img src="images/vnet-peering-01.png" />

- ピアリングの追加

  - この仮想ネットワーク

    - **ピアリング リンク名**: spoke-to-hub（任意）

    - **リモート仮想ネットワークへのトラフィック**: 許可

    - **リモート仮想ネットワークから転送されたトラフィック**: 許可

    - **仮想ネットワーク ゲートウェイまたはルート サーバー**: なし

  - リモート仮想ネットワーク

    - **ピアリング リンク名**: hub-to-spoke（任意）

    - **仮想ネットワークのデプロイ モデル**: Resource Manager

    - **サブスクリプション**: ワークショップで使用中のサブスクリプション

    - **仮想ネットワーク**: vnet-hub

    - **リモート仮想ネットワークへのトラフィック**: 許可

    - **リモート仮想ネットワークから転送されたトラフィック**: 許可

    - **仮想ネットワーク ゲートウェイまたはルート サーバー**: なし

    <img src="images/vnet-peering-02.png" />

- 「**追加**」をクリック

- **ピアリング状態** が **接続済み** となることを確認

  <img src="images/vnet-peering-03.png" />

<br />

### 参考情報

- [可用性ゾーン間で仮想マシンのディザスター リカバリーを有効にする](https://docs.microsoft.com/ja-jp/azure/site-recovery/azure-to-azure-how-to-enable-zone-to-zone-disaster-recovery)

<br />
<hr />

## Exercise 6: 仮想マシンの構成

<img src="images/exercise-6.png" />

<br />

### Task 1: 仮想マシンの監視設定

- Azure ポータルのトップ画面から ツール に表示される **Azure Monitor** をクリック

  <img src="images/defender-for-cloud-01.png" />

- **仮想マシン** を選択、「**分析情報の構成**」をクリック

- 作成した仮想マシンの「**有効にする**」をクリック

  <img src="images/vm-insights-01.png" />

- 「**有効**」をクリック

  <img src="images/vm-insights-02.png" />

- 監視の構成で **データの収集ルール** の **新規作成** をクリック

  <img src="images/vm-insights-03.png" />

- 新しいルールの作成を行い「**作成**」をクリック

  - **データの収集ルール名**: data-collection-rule-1（任意）

  - **プロセスと依存関係を有効にする**: オン

  - **Log Analytics workspaces**: log-1（ワークショップ環境に作成済みのワークスペース）

    <img src="images/vm-insights-04.png" />

- 「**構成**」をクリック

  <img src="images/vm-insights-05.png" />

- Azure Monitor の管理ブレードの **データ収集ルール** を選択

  「**＋ 作成**」をクリック

  <img src="images/vm-insights-06.png" />

- データ収集ルールの作成

  - 「**基本**」タブ

    - **ルール名**: data-collection-rule-2（任意）

    - **サブスクリプション**: ワークショップで使用中のサブスクリプション

    - **リソース グループ**: ワークショップで使用中のリソース グループ

    - **Region**: 仮想マシンを展開した地域

    - **プラットフォームの選択**: Windows

      <img src="images/vm-insights-07.png" />

  - 「**リソース**」タブ

    - 「**リソースの追加**」をクリック

      <img src="images/vm-insights-08.png" />

    - 範囲の選択で作成した仮想マシンを選択

      <img src="images/vm-insights-09.png" />

    - 仮想マシンがリソースとして追加されていることを確認

      <img src="images/vm-insights-10.png" />

  - 「**収集と配信**」タブ

    - 「**データ ソースの追加**」をクリック

      <img src="images/vm-insights-11.png" />

    - 収集するログを選択

      - **データ ソースの種類**: Windows event logs

      - **アプリケーション**： クリティカル、エラー、警告

      - **セキュリティ**: 監査の失敗

      - **システム**: クリティカル、エラー、警告

      <img src="images/vm-insights-12.png" />

    - データ ソースが追加されていることを確認

      <img src="images/vm-insights-13.png" />
  
  - 「**確認および作成**」をクリック

- 「**作成**」をクリック

<br />

### Task 2: Microsoft Defender for Endpoint のインストール

- Azure Policy の管理ブレードを表示

- Defender for Endpoint エージェントのコンプライアンス状態を確認

  <img src="images/vm-configuration-01.png" />

  ※ ポリシー評価が終了していない場合は、次のタスクを完了後、再度ご確認ください

- **Windows 仮想マシンに Microsoft Defender for Endpoint エージェントをデプロイする** をクリック

- コンプライアンス未準拠のリソースを確認し「**修復タスクの作成**」をクリック

  <img src="images/vm-configuration-02.png" />

- 「**修復**」をクリック

  <img src="images/vm-configuration-03.png" />

- **修復** の「**修復タスク**」タブから修復状態を確認

  <img src="images/vm-configuration-04.png" />

<br />

### Task 3: 更新プログラムの管理

- 仮想マシンの管理ブレードへ移動し **更新プログラム** を選択

- 「**更新の管理センターを使用して更新プログラムに移動**」をクリック

  <img src="images/update-management-01.png" />

- 「**設定の更新**」をクリック

  <img src="images/update-management-02.png" />

- **プロパティ** を設定し「**次へ**」をクリック

  - **更新設定を変更する**: バッチ オーケストレーション

  - **バッチ オーケストレーション オプション**: Azure によるオーケストレーション (プレビュー)

    <img src="images/update-management-03.png" />

- **Machines** で作成したマシンが表示されていることを確認し「**次へ**」をクリック

  <img src="images/update-management-04.png" />

- 「**確認して変更**」をクリック

- 「**スケジュールの更新**」をクリックしメンテナンス構成を作成

  <img src="images/update-management-06.png" />

- **メンテナンス構成の作成**

  - 「**基本**」タブ

    - **プロジェクトの詳細**

      - **サブスクリプション**: ワークショップで使用中のサブスクリプション

      - **リソース グループ**: ワークショップで使用中のリソース グループ

    - **インスタンスの詳細**

      - **構成名**: vm-update（任意）

      - **地域**: 仮想マシンを展開した地域

      - **メンテナンス スコープ**: ゲスト (Azure VM、Arc 対応 VM/サーバー)

      - **再起動の設定**: 必要に応じて再起動

    <img src="images/update-management-07.png" />

      - **スケジュール**:

        - **開始日**: 任意

        - **メンテナンス期間**: 2 時間 0 分

        - **繰り返し**: 1 月

          - **曜日**: 第 2 水曜日

          - **オフセット (経過日数)**: 1

        <img src="images/update-management-08.png" />

- 「**マシン**」タブ

  リストに作成した仮想マシンが表示されていることを確認し「**次: Updates >**」をクリック

  <img src="images/update-management-09.png" />

- 「**確認および作成**」をクリック

  <img src="images/update-management-10.png" />

  - 更新プログラムの分類から仮想マシンに適用する更新プログラムの種類を選択可

    <img src="images/update-management-11.png" />

  - KB 番号による指定も可

    <img src="images/update-management-12.png" />

- 指定した内容を確認し「**作成**」をクリック

  <img src="images/update-management-13.png" />

- 「**更新プログラムの確認**」をクリック

  <img src="images/update-management-05.png" />

- 今すぐ評価をトリガーするのメッセージが表示されるので「**OK**」をクリック

  <img src="images/update-management-14.png" />

- Recommended updates に表示される更新プログラムの KB ID をメモし「**↓ 1 回限りの更新**」をクリック

  ※ 複数の更新プログラムが表示される場合は Microsoft Defender Antivirus の再起動不要な更新プログラムを選択

  <img src="images/update-management-15.png" />

- 作成した仮想マシンが表示されていることを確認し「**次へ**」をクリック

  <img src="images/update-management-16.png" />

- 「**＋ KB ID/パッケージを含む**」をクリック

  <img src="images/update-management-17.png" />

- メモした KB ID を入力し「**保存**」をクリック

  <img src="images/update-management-18.png" />

- 「**次へ**」をクリック

  <img src="images/update-management-19.png" />

- プロパティを設定し「**次へ**」をクリック

  - **再起動オプション**: 必要に応じて再起動

  - **メンテナンス期間 (分)**: 120

    <img src="images/update-management-20.png" />

- 「**インストール**」をクリック

  <img src="images/update-management-21.png" />

  ※ インストールに数分かかるため次のタスクの後に結果を確認

- 「**履歴**」タブからログを確認可

  <img src="images/update-management-22.png" />

- Azure ポータルのトップ画面から **検索バー** のテキストボックスに「**update**」と入力

- 表示される候補より「**Update Management センター (プレビュー)**」を選択

  <img src="images/update-management-23.png" />

- 複数の仮想マシンの管理が行えることを確認

  <img src="images/update-management-24.png" />

<br />

### Task 4: 仮想マシンの Windows Firewall の構成

- 作成した仮想マシンの管理ブレードへ移動

- 「**接続**」-「**Bastion**」を選択

  <img src="images/connect-vm-01.png" />

- ユーザー名、パスワードを入力し「**接続**」をクリック

  <img src="images/connect-vm-02.png" />

- ブラウザの新しいタブに Windows Server の画面が表示

  <img src="images/connect-vm-03.png" />

- スタート メニューからコントロール パネルを選択

- 「**System and Security**」を選択し「Administrative Tools」をクリック

  <img src="images/connect-vm-04.png" />

- 「**Windows Defender Firewall with Advanced Security」をダブルクリックして起動

  <img src="images/connect-vm-05.png" />

- 「**Inbound Rules**」を選択

- 「**Core Networking Diagnostics - ICMP Echo Request (ICMPv4-In)**」の Profile が Private の項目をダブルクリック

  <img src="images/connect-vm-06.png" />

- 「**General**」タブで「Enabled」にチェック

  <img src="images/connect-vm-07.png" />

- 「**Scope**」タブで「**Remote IP address**」の「**Any IP address**」をチェック

  <img src="images/connect-vm-08.png" />

- 「**OK**」をクリックして変更を適用

- ルールが有効になったことを確認

  <img src="images/connect-vm-09.png" />

### Task 5: 仮想マシンの操作（ファイル作成、ブラウジング、ログオン失敗）

- 接続中の仮想マシンのデスクトップ上で右クリック

- 「**New**」-「**Text Document**」を選択

  <img src="images/new-text-document-01.png" />

- 任意のファイル名に変更

  <img src="images/new-text-document-02.png" />

- Edge を起動し www.microsoft.com へアクセス

  <img src="images/browser-01.png" />

- ブラウザのタブを閉じて接続を切断

- 再度、仮想マシンの管理ブレードから「**接続**」-「**Bastion**」を選択

- ログオン失敗のイベントを記録するため、異なるパスワードを入力し「**接続**」をクリック

- Connection Error メッセージが表示され、ログオンに失敗することを確認

  <img src="images/connection-error.png" />

- タブを閉じて終了

<br />

### 参考情報

- [Update Management センター (プレビュー) のサポート マトリックス](https://docs.microsoft.com/ja-jp/azure/update-center/support-matrix?tabs=azurevm%2Cazurevm-os)

- [更新プログラムとメンテナンスの概要](https://docs.microsoft.com/ja-jp/azure/virtual-machines/updates-maintenance-overview)

- [Azure VM での VM ゲストの自動パッチ適用](https://docs.microsoft.com/ja-jp/azure/virtual-machines/automatic-vm-guest-patching)

<br />
<hr />

## Exercise 7: ネットワーク診断の設定と監視

<img src="images/exercise-7.png" />

<br />

### Task 1: NSG フロー ログの収集

- Azure ポータルのトップ画面から **検索バー** のテキストボックスに「**network**」と入力

- 表示される候補より「**Network Watcher**」を選択

  <img src="images/network-watcher-01.png" />

- **NSG フロー ログ** を選択し「**＋ 作成**」をクリック

  <img src="images/network-watcher-04.png" />

- 使用中のサブスクリプションを選択し「**＋ NSG の選択**」をクリック

  <img src="images/network-watcher-05.png" />

- 作成した仮想マシンと仮想マシンの展開先のサブネットの NSG を選択し「**選択の確認**」をクリック

  <img src="images/network-watcher-06.png" />

- 「**新しいストレージ アカウントの作成**」をクリック

  <img src="images/network-watcher-07.png" />

- 新しいストレージ アカウントを作成

  - **名前**: 任意（英語小文字、数字の組み合わせ）

  - **アカウントの種類**: StorageV2 (汎用 v2)

  - **パフォーマンス**: Standard

  - **レプリケーション**: ローカル冗長ストレージ (LRS)

  - **場所**: 仮想ネットワークの展開先と同じ地域

  - **リソース グループ**: ワークショップで使用中のリソース グループ

  - **TLS の最小バージョン**: バージョン 1.2

    <img src="images/network-watcher-08.png" />
  
- 「**次: 構成 >**」をクリック

    <img src="images/network-watcher-09.png" />

- 構成を行い「**確認および作成**」をクリック

  - **フロー ログのバージョン**: バージョン 2

  - **Traffice Analytics を有効にする**: チェック

  - **トラフィック分析の処理間隔**: 1 時間ごと（既定）

  - **サブスクリプション**: ワークショップで使用中のサブスクリプション

  - **Log Analytics ワークスペース**: 使用中の環境に作成済みのワークスペース

    <img src="images/network-watcher-10.png" />

- 指定した内容を確認し「**作成**」をクリック

<br />

### Task 2: 接続モニターの作成

- Network Watcher の管理ブレードで「**接続モニター**」を選択

- 「**＋ 作成**」をクリック

  <img src="images/network-watcher-11.png" />

- 「**基本**」タブの設定を行い「**次へ: テスト グループ >>**」をクリック

  - **接続モニター名**: connection-monitor-1（任意）

  - **サブスクリプション**: ワークショップで使用中のサブスクリプション

  - **リージョン**: 仮想ネットワークの展開先と同じ地域

  - **接続モニターによって作成されたワークスペースを使用する**: オフ

  - **サブスクリプション**: ワークショップで使用中のサブスクリプション

  - **リージョン**: 仮想ネットワークの展開先と同じ地域

  - **ワークスペース**: 使用中の環境に作成済みのワークスペース

    <img src="images/network-watcher-12.png" />

- **テスト グループの詳細の追加** で **テスト グループ名** を入力

  例）test-group-1（任意）

- 「**ソースの追加**」をクリック

  <img src="images/network-watcher-13.png" />

  - **ソースの追加** でエンドポイントとなる仮想マシンを選択し「**エンドポイントの追加**」をクリック

    - **Azure エンドポイント** を選択（既定）

    - **型**: Virtual Machines（既定）

    - vnet-hub に展開されている仮想マシン（vm-monitor）を選択

      <img src="images/network-watcher-14.png" />

- 「**テスト構成の追加**」をクリック

  <img src="images/network-watcher-15.png" />

  - **テスト構成の追加** で構成を行い「**テスト構成の追加**」をクリック

    - **テスト構成名**: test1（任意）

    - **プロトコル**: ICMP

    - **テストの頻度**: 1 分ごと

    - **成功のしきい値**:
    
      - **チェックの失敗率 (%)**: 100

      - **ラウンド トリップ時間 (ミリ秒)**: 3000

      <img src="images/network-watcher-16.png" />

- 「**ターゲットの追加**」をクリック

  <img src="images/network-watcher-17.png" />

  - **ターゲットの追加** で対象となる仮想マシンを選択し「**エンドポイントの追加**」をクリック

    - **Azure エンドポイント** を選択（既定）

    - **型**: Virtual Machines（既定）

    - 先の手順で作成した仮想マシンを選択

    <img src="images/network-watcher-18.png" />

- 指定した内容を確認し「**テスト グループの追加**」をクリック

  <img src="images/network-watcher-19.png" />

- 「**次へ: アラートの作成 >>**」をクリック

  <img src="images/network-watcher-20.png" />

- **アラートの作成** でアラートの有効化、アクション グループの選択を行い「**確認および作成**」をクリック

  - **アラートの作成**: オン

  - **アラート グループ名**: 正常性アラート構成時に作成したアラート グループを選択

    <img src="images/network-watcher-21.png" />

- 指定した内容を確認し「**作成**」をクリック

  <img src="images/network-watcher-22.png" />

- 接続モニターの作成が完了後、テストが開始

  <img src="images/network-watcher-23.png" />

- テスト グループ名をクリックし、テストの概要を確認

  <img src="images/network-watcher-24.png" />

- テスト構成でテスト結果を確認

  <img src="images/network-watcher-25.png" />

- テスト グループ配下の項目をクリック

  <img src="images/network-watcher-26.png" />

- トポロジやパフォーマンスの状況を確認

  <img src="images/network-watcher-27.png" />

<br />

### Task 3: NSG 診断による通信状況の確認

- Network Watcher の管理ブレードで「**NSG 診断**」を選択

- ツールに診断を行う情報を入力し「**チェック**」をクリック

  - **サブスクリプション**: ワークショップで使用中のサブスクリプション

  - **リソース グループ**: ワークショップで使用中のリソース グループ

  - **サポートされているリソースの種類**: 仮想マシン

  - **リソース**: 作成した仮想マシン

  - **プロトコル**: TCP

  - **方向**: 受信

  - **ソースの種類**: サービス タグ

  - **サービス タグ**: Internet

  - **ターゲット IP アドレス**: 仮想マシンの IP アドレス

  - **ターゲット ポート**: 3389

    <img src="images/network-watcher-02.png" />

- 指定したトラフィックの状態を確認

  <img src="images/network-watcher-03.png" />

  ※ サブネット、仮想マシンのネットワーク セキュリティ グループでのアクションを表示

  ※ インターネットからの RDP での接続が拒否されていることを確認

<br />
<hr />

## Exercise 8: テスト フェールオーバーの実行

<img src="images/exercise-8.png" />

<br />

### Task 1: テスト用の仮想ネットワークの作成

- Azure Portal のトップ画面上部の「リソースの作成」をクリック

  <img src="images/create-resources.png" />

- 検索ボックスに **Virtual Network** と入力し、表示される候補より「**Virtual Network**」を選択

  <img src="images/virtual-network-01.png" />

- 「**作成**」をクリック

  <img src="images/virtual-network-02.png" />

- 仮想ネットワークの作成

  - 「**基本**」タブ

    - プロジェクトの詳細

      - **サブスクリプション**: ワークショップで使用中のサブスクリプション

      - **リソース グループ**: ワークショップで使用中のリソース グループ

    - インスタンスの詳細

      - **名前**: vnet-spoke-2（既定）

      - **地域**: フェールオーバー対象の仮想マシンと同じ地域

    <img src="images/virtual-network-03.png" />

  - 「**IP アドレス**」タブ

    - IP アドレス、サブネットは既定の設定（他の仮想ネットワークと重複しないかは確認）

    <img src="images/virtual-network-04.png" />

  - 「**セキュリティ**」タブ

    - BastionHost / DDos Protection Standard / ファイアウォール はすべて無効化（既定）

    <img src="images/virtual-network-05.png" />

- 「**作成**」をクリック

  <img src="images/virtual-network-06.png" />

- 作成した仮想ネットワークの管理ブレードへ移動

- **ピアリング** を選択し「**＋ 作成**」をクリック

  <img src="images/virtual-network-07.png" />

- ピアリングを作成

  - この仮想ネットワーク

    - **ピアリング リンク名**: spoke-2-to-hub（任意）

  - リモート仮想ネットワーク

    - **ピアリング リンク名**: hub-to-spoke-2（任意）

    - **サブスクリプション**: ワークショップで使用中のサブスクリプション

    - **仮想ネットワーク**: vnet-hub

  <img src="images/virtual-network-08.png" />

- 「**追加**」をクリックしてピアリングを構成

<br />

### Task 2: テスト フェールオーバーの実行

- **site-recovery** ではじまるリソース グループが作成されていることを確認

- リソース グループ内に Automation アカウント、Recovery Services コンテナー、ストレージが作成されていることを確認

  <img src="images/vm-zone-dr-14.png" />

- 仮想マシンの管理ブレードへ移動し **ディザスター リカバリー** を選択

- 「**テスト フェールオーバー**」をクリック

  <img src="images/vm-zone-dr-05.png" />

- フェールオーバーの設定を行い「**OK**」をクリック

  - **フェールオーバー元**: 仮想マシンが展開されている地域 (ゾーン 1)

  - **フェールオーバー先**: 仮想マシンが展開されている地域 (ゾーン 2)

  - **Azure 仮想ネットワーク**: 先の手順で作成した仮想ネットワーク

    <img src="images/vm-zone-dr-06.png" />

    ※ **復旧ポイントを選択してください** のリンクをクリックし復旧ポイントの選択が可

- フェールオーバー完了後、リソースを確認

  ※ フェール オーバー設定時に作成された **-asr** が接尾語に付与されたリソース グループを選択

  <img src="images/vm-zone-dr-07.png" />

  ※ 仮想マシン、NIC、ディスクが作成、それぞれ名前の接尾語に **-test** が付与

- テスト フェールオーバーで作成された仮想マシンの管理ブレードへ移動し ** Bastion** を選択

- ユーザー名、パスワードを入力し「**接続**」をクリック

  <img src="images/vm-zone-dr-09.png" />

- 新しいタブで Windows Server の画面が表示

  <img src="images/vm-zone-dr-10.png" />

- ファイルや設定を確認後、タブを閉じて接続を切断

<br />

### Task 3: テスト フェールオーバーのクリーンアップ

- フェールオーバー元の仮想マシンの管理ブレードへ移動し **ディザスター リカバリー** を選択

- 「**テスト フェールオーバーのクリーンアップ**」をクリック

  <img src="images/vm-zone-dr-11.png" />

- 「**テストが完了しました。テスト フェールオーバー仮想マシンを削除してください。**」をチェック

  <img src="images/vm-zone-dr-12.png" />

- 「**OK**」をクリックし、テスト フェールオーバー環境を削除

- リソースの確認

  ※ フェール オーバー設定時に作成された **-asr** が接尾語に付与されたリソース グループを選択

  <img src="images/vm-zone-dr-13.png" />

<br />

### 参考情報

- [Site Recovery に関する一般的な質問](https://docs.microsoft.com/ja-jp/azure/site-recovery/site-recovery-faq)

<br />
<hr />

## Exercise 9: 仮想マシンの監視

<img src="images/exercise-9.png" />

<br />

### Task 1: 仮想マシンの分析情報の確認

- 仮想マシンの管理ブレードへ移動し **分析情報** を選択

  <img src="images/vm-insights-15.png" />

- 「**パフォーマンス**」タブを選択し、リソースの使用率を確認

  <img src="images/vm-insights-16.png" />

- 「**マップ**」タブを選択、プロセスの依存関係を確認

  <img src="images/vm-insights-17.png" />

- 仮想マシンのプロセスを展開

  <img src="images/vm-insights-18.png" />

- ポートを展開し接続先を確認

  <img src="images/vm-insights-19.png" />

- Time range で時間の範囲を選択可

  <img src="images/vm-insights-20.png" />

<br />

### Task 2: ログ クエリによるデータ分析とアラート作成

- 仮想マシンの管理ブレードから **ログ** を選択

  <img src="images/azure-monitor-01.png" />

- イベント種別にログをカウントするクエリを実行

  ```
  Event
  | summarize count() by Computer, EventLog, EventLevelName
  | sort by Computer, EventLog, EventLevelName
  ```

  <img src="images/azure-monitor-02.png" />

- 仮想マシンに特定の Windows イベントが記録された回数を抽出するクエリを実行

  ※ 4625 はログオン失敗イベント

  ```
  Event 
  | where EventID == 4625 
  | where Computer == "vm1"
  ```

  ※ vm1 は仮想マシン名、使用中の環境のものに変更して実行

  <img src="images/azure-monitor-03.png" />

- 「**＋ アラート ルール**」をクリック

- **しきい値** に「**5**」を入力し、あとは既定のまま「**次へ: アクション >**」をクリック

  <img src="images/azure-monitor-04.png" />

- **アクション グループ** に正常性アラートの構成時に作成したアクション グループを選択し「**次へ: 詳細>**」をクリック

  <img src="images/azure-monitor-05.png" />

- **アラート ルール名** を入力し「**確認および作成**」をクリック

  <img src="images/azure-monitor-06.png" />

- 「**作成**」をクリックし、アラートを作成

<br />

### 参考情報

- [VM insights の概要](https://docs.microsoft.com/ja-jp/azure/azure-monitor/vm/vminsights-overview)

- [VM insights を使用したパフォーマンスのグラフ化](https://docs.microsoft.com/ja-jp/azure/azure-monitor/vm/vminsights-performance)

- [VM insights のマップ機能](https://docs.microsoft.com/ja-jp/azure/azure-monitor/vm/vminsights-maps)

- [VM insights からログをクエリする方法](https://docs.microsoft.com/ja-jp/azure/azure-monitor/vm/vminsights-log-query)

- [Azure Monitor を使用して仮想マシンを監視する](https://docs.microsoft.com/ja-jp/azure/azure-monitor/vm/monitor-virtual-machine-workloads)

<br />
<hr />
