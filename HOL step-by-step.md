![Microsoft Cloud Workshop](images/ms-cloud-workshop.png)

management and security Hands-on lab  
October 2022

<br />

### Contents

- [Exercise 1: Azure ロールの割り当て](#exercise-1-azure-ロールの割り当て)

  - [Task 1: サブスクリプションへのセキュリティ管理者の追加](#task-1-サブスクリプションへのセキュリティ管理者の追加)

  - [Task 2: リソース グループへの仮想マシンの管理者ログインの追加](#task-2-リソース-グループへの仮想マシンの管理者ログインの追加)


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

- アクセスの割り当て先に **ユーザー、グループ、およびサービス プリンシパル** が選択されていることを確認し「**メンバーを選択する**」をクリック

  <img src="images/role-assignment-06.png" />

- ロールに追加するユーザーを選択

  <img src="images/role-assignment-07.png" />

- メンバーに選択したユーザーが表示されていることを確認し「**次へ**」をクリック

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

- 先と同様の手順で、ロールに追加するユーザーを選択し、ロールの割り当てを追加

  <img src="images/role-assignment-13.png" />

- **アクセス制御** 画面で「**ロールの割り当て**」タブを選択

  リソース グループの **仮想マシンの管理者ログイン** ロールへユーザーが追加されていることを確認

  <img src="images/role-assignment-14.png" />

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

