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

- [Exercise 5: 仮想マシンの展開](#exercise-5-仮想マシンの展開)

<br />

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

## Exercise 2: 正常性アラートの構成

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

## Exercise 5: 仮想マシンの展開と構成

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

      - **可用性オプション**: インフラストラクチャの冗長は必要ありません

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

      <img src="images/virtual-machine-02.png" />

      ※ 仮想マシンのサイズ選択では、ポリシーで許可した SKU のみが表示されることを確認

      <img src="images/select-vm-sku.png" />


  - 「**ディスク**」タブ

    - ディスクのオプション

      - **OS ディスクの種類**: Standard SSD

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

      <img src="images/virtual-machine-04.png" />

  - 「**管理**」タブ

    - 自動シャットダウン

      - **自動シャットダウンを有効にする**: オン

        ※その他は既定の設定

      <img src="images/virtual-machine-05.png" />

  - Monitoring、詳細、タグは既定の設定のまま「**確認および作成**」をクリック

  - 指定した内容を確認し「**作成**」をクリック

    <img src="images/virtual-machine-06.png" />

### Task 2: 仮想マシンの監視設定

- Azure ポータルのトップ画面から ツール に表示される **Azure Monitor** をクリック

  <img src="images/defender-for-cloud-01.png" />

- **仮想マシン** を選択、作成した仮想マシンの「**有効にする**」をクリック

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

### Task 3: Defender for Endpoint のインストール

- Azure Policy の管理ブレードから **コンプライアンス** を選択

- Defender for Endpoint エージェントのコンプライアンス状態を確認

  <img src="images/vm-configuration-01.png" />

- **修復** を選択

  <img src="images/vm-configuration-02.png" />

- 「**修復するポリシー**」タブの **Microsoft Defender for Endpoint エージェントをデプロイする** をクリック

  <img src="images/vm-configuration-03.png" />

- 「**修復**」をクリック

  <img src="images/vm-configuration-04.png" />

<br />

### Task 4: 仮想ネットワーク ピアリングの構成

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

## Exercise 6: Network Watcher の設定

<br />

### Task 1: NSG フロー ログの収集

<br />

### Task 2: 接続モニターの作成

<br />

## Exercise 7: 

<br />

