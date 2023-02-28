# OSテスト

## セクション後のテスト

### 一、Web開発の概要

---

##### １、OutSystemsで作成できるのは、どのタイプのアプリケーションですか。

 <span style="color:red;background:yellow;">A、Web、モバイル、およびサービス</span>

B、Web、モバイル、サービス、および拡張機能

C、モジュールと拡張機能

D、Webのみ

##### ２、次のうち、プロデューサモジュール内の要素の公開に関する説明として正しいものはどれですか。

A、任意の要素を公開でき、同じアプリケーションのモジュールでのみ再利用できる。

B、任意の要素を公開でき、任意のアプリケーションのモジュールで再利用できる。

<span style="color:red;background:yellow;">C、Publicプロパティが［Yes］に設定されている要素のみを公開でき、任意のアプリケーションのモジュールで再利用できる。</span>

D、Publicプロパティが［Yes］に設定されている要素のみを公開でき、同じアプリケーションのモジュールでのみ再利用できる。

##### ３、次のうち、コンシューマモジュールに関する説明として正しいものはどれですか。

A、同じアプリケーションのプロデューサモジュールからのみ要素を再利用できる。

<span style="color:red;background:yellow;">B、プロデューサモジュール内で公開されている要素のみを再利用できる。</span>

C、任意のプロデューサモジュールから任意の要素を再利用できる。

D、他のアプリケーションのプロデューサモジュールからのみ要素を再利用できる。



---

### 二、データのモデリング

##### １、 OutSystemsは、基盤となる開発者用のデータベーステーブルを管理しますか。

<span style="color:red;background:yellow;">A、はい</span>

B、いいえ

##### ２、エンティティとアトリビュートは、データベースで何として作成されますか。

<span style="color:red;background:yellow;">A、テーブルと列</span>

B、テーブルとインデックス

C、インデックスと列

D、テーブルと制約

##### ３、「TotalCount」という名前のアトリビュートは、OutSystemsで自動的にどのデータ型に設定されますか。

A、Text

<span style="color:red;background:yellow;">B、Integer</span>

C、Boolean

D、Date

##### ４、エンティティはCRUD操作のためのエンティティアクションとともに作成されますが、次のうちどれですか。

A、Insert、Update、Delete

<span style="color:red;background:yellow;">B、Create、CreateOrUpdate、Update、Get、GetForUpdate、Delete</span>

C、GET、POST、DELETE

D、Add、Change、Remove

##### ５、入力パラメータは常に必須です。

A、TRUE

<span style="color:red;background:yellow;">B、FALSE</span>

##### ６、出力パラメータはどこで使用できますか。

A、実装スコープ内のみ。

B、実装スコープ外のみ。

<span style="color:red;background:yellow;">C、実装スコープ内と実装スコープ外の両方。</span>

##### ７、ストラクチャが持つことができるアトリビュートのデータ型はどれですか。

A、Basic、Complex、およびRecord

B、Basic、String、およびObject

<span style="color:red;background:yellow;">C、Basic、Structure、Entity、およびList</span>

D、BasicとListのみ。

##### ８、次のうち、OutSystemsのリストに関する説明として正しいものはどれですか。

<span style="color:red;background:yellow;">A、同じデータ型の要素の集合。</span>

B、データ型が異なる可能性がある要素の集合。



---

### 三、基本的な画面開発1

##### １、Widget Treeは何を表しますか。

A、画面のライフサイクルフロー。

<span style="color:red;background:yellow;">B、画面上のウィジェットの階層。</span>

C、アプリケーションの画面のリスト。

D、既存の画面テンプレート。

##### ２、画面内で作成できるのは、どの型の変数ですか。

A、ローカル変数のみ。

B、入力パラメータのみ。

<span style="color:red;background:yellow;">C、入力パラメータとローカル変数。</span>

D、入力パラメータ、出力パラメータ、ローカル変数。

##### ３、画面のPreparationの主な目的は何ですか。

A、描画するウィジェットを決定する。

<span style="color:red;background:yellow;">B、データベースからデータを取得する。</span>

C、フォームのデータをサーバーに送信する。

D、ユーザーを適切な画面にリダイレクトする。

##### ４、 画面のライフサイクルでは、Preparationはブラウザで実行されます。

A、TRUE

<span style="color:red;background:yellow;">B、FALSE</span>

##### ５、Aggregateの［Sources］セクションは、何のために使用しますか。

A、Aggregateの出力レコードをテストするための値を定義するため。

<span style="color:red;background:yellow;">B、レコードの取得元となるエンティティを定義するため。</span>

C、特定のレコードのサブセットを取得する条件を定義するため。

D、Aggregateの出力レコードの順序を定義するため。

##### ６、Aggregateの［Test Values］セクションは、何のために使用しますか。

<span style="color:red;background:yellow;">A、Aggregateのプレビューデータをテストするための値を定義するため。</span>

B、すべてのレコードではなく特定のレコードを取得するための条件を設定するため。

C、Aggregateの出力レコードの順序を定義するため。

D、レコードの取得元となるエンティティを定義するため。

##### ７、Aggregateから返されるレコード数を制限するには、どのようにすればよいですか。

<span style="color:red;background:yellow;">A、Max. Recordsプロパティを使用する。</span>

B、Length値を使用する。

C、Count値を使用する。

D、［Sorting］を使用する。

##### ８、Aggregateによって生成されたSQLを参照することができます。

<span style="color:red;background:yellow;">A、TRUE</span>

B、FALSE

８、次のうち、Expressionウィジェットに関する説明として正しいものはどれですか。

A、静的なテキストのみを表示する。

<span style="color:red;background:yellow;">B、実行時に計算されたテキストを表示する。</span>

##### ９、次のうち、Imageウィジェットに関する説明として正しいものはどれですか。

A、静的な画像のみを表示する。

B、URLで指定された画像のみを表示する。

C、データベース内に保存されている画像のみを表示する。

<span style="color:red;background:yellow;">D、静的な画像、URLにある画像、データベース内の画像を表示する。</span>

##### １０、次のうち、Table Recordsウィジェットに関する説明として正しいものはどれですか。

A、レコードを1列に1件ずつの表形式レイアウトで表示する。

<span style="color:red;background:yellow;">B、レコードを1行に1件ずつの表形式レイアウトで表示する。</span>

C、レコードを1テーブルに1件ずつの表形式レイアウトで表示する。

D、レコードを自由形式で表示する。

##### １１、Formウィジェットでは、InputウィジェットとLabelウィジェットのみを使用できます。

A、TRUE

<span style="color:red;background:yellow;">B、FALSE</span>



---

### 四、データリレーションのモデリング

##### １、エンティティ識別子は単純な主キーまたは複合キーにすることができます。

A、TRUE

<span style="color:red;background:yellow;">B、FALSE</span>

##### ２、OutSystemsで実装できるリレーションのタイプをすべて挙げてください。

A、1対多と多対多。

<span style="color:red;background:yellow;">B、1対1、1対多、および多対多。</span>

C、1対1と1対多。

D、多対多。

##### ３、多対多のリレーションで、交差エンティティに最低限必要なアトリビュートは何ですか。

A、各親エンティティを参照する複合キー。

<span style="color:red;background:yellow;">B、識別子と各親エンティティに対する外部キー。</span>

C、各親エンティティに対する外部キーと交差レコード数。

D、Id、Label、Order、Is Active。

##### ４、エンティティからレコードを削除すると、外部キー参照を使用するエンティティのレコードがすべて削除されます。 この場合、どの削除規則が使用されていますか。

A、Protect

<span style="color:red;background:yellow;">B、Delete</span>

C、Ignore



---

### 五、基本的な画面開発2

##### １、On ClickプロパティではLinkとButtonの動作を定義できます。次のうち、説明として正しいものはどれですか。

A、Linkでできるのは、画面への移動のみである。

B、Buttonでできるのは、リクエストの送信のみである。

<span style="color:red;background:yellow;">C、LinkとButtonでできるのは、画面への移動やリクエストの送信である。</span>

D、LinkとButtonでできるのは、画面への移動のみである。

##### ２、次のうち、Navigateメソッドを使用するButtonをクリックした後の画面のライフサイクルの順序として正しいものはどれですか。

<span style="color:red;background:yellow;">A、Preparationを実行した後、遷移先画面を描画する。</span>

B、画面アクションを実行し、Preparationを実行し、遷移先画面を描画する。

C、遷移先画面を描画した後、その画面のPreparationを実行する。

D、Preparationを実行した後、画面アクションを実行する。

##### ３、次のうち、Submitメソッドが使用するHTTPリクエストメソッドはどれですか。

A、PUT

<span style="color:red;background:yellow;">B、POST</span>

C、GET

D、PATCH

##### ４、画面アクションをEnd要素で終了した場合と「(Current Screen)」へのDestinationで終了した場合の結果は同じになります。

A、TRUE

<span style="color:red;background:yellow;">B、FALSE</span>

##### ５、次のうち、2つのエンティティ間で「With or Without」結合を実行したときに返されるのはどれですか。

A、両方のエンティティのすべてのレコードを返す（FULL OUTER JOIN）。

B、2つのエンティティの間で対応するレコードのみを返す（INNER JOIN）。

<span style="color:red;background:yellow;">C、右のエンティティに対応するレコードがない場合でも、左のエンティティのレコードをすべて返す（LEFT JOIN）。</span>

D、左のエンティティに対応するレコードがない場合でも、右のエンティティのレコードをすべて返す（RIGHT JOIN）。

##### ６、 次のうち、Aggregateで列が非表示になっている場合の説明として正しいものはどれですか。

A、Aggregateの出力に含まれなくなる。

<span style="color:red;background:yellow;">B、引き続きAggregateの出力に含まれる。</span>

C、これらの列のみがAggregateの出力になる。

D、その理由は、これらがデータベースで空であるためである。

##### 7、次のうち、Sum、Average、Min、Max、Countなどの集約関数をアトリビュートで使用した場合の説明として正しいものはどれですか。

A、アトリビュートの集約結果が他のエンティティアトリビュートとともにAggregateの出力に追加される。

<span style="color:red;background:yellow;">B、アトリビュートの集約結果のみがAggregateの出力に含まれる。</span>

##### ８、次のうち、SQLクエリ内でエンティティおよびエンティティアトリビュートの名前を記述する場合の正しい構文はどれですか。

A、<Entity>と<Entity>.[Attribute]

B、{Entity}と{Entity}.<Attribute>

<span style="color:red;background:yellow;">C、{Entity}と{Entity}.[Attribute]</span>

D、<Entity>と<Entity>.<Attribute>

##### ９、SQLクエリでは、SELECT文のみを実行できます。

A、TRUE

<span style="color:red;background:yellow;">B、FALSE</span>

##### １０、Check Boxウィジェットがバインドされるのは、どの型の変数ですか。

A、Text

B、Integer

<span style="color:red;background:yellow;">C、Boolean</span>

D、Date

##### １１、Combo Boxウィジェットでは、ドロップダウンリストの選択肢の中から値を1つ選択することができます。次のうち、できないことはどれですか。

A、Source Entityプロパティを使用して、エンティティまたは静的エンティティから選択肢を取得する。

B、Source Record Listプロパティを使用して、レコードのリストから選択肢を取得する。

<span style="color:red;background:yellow;">C、Special Listセクションを使用して、エンティティまたは静的エンティティから選択肢を取得する。</span>

D、Special Listセクションを使用して、特殊な選択肢を手動で設定する。

##### １２、Combo Boxウィジェットに表示される値のリストでは、エンティティと特殊リストを組み合わせることができます。

<span style="color:red;background:yellow;">A、TRUE</span>

B、FALSE



---

### 六、ロジックとバリデーション

##### １、次のうち、サーバーアクションで使用できる変数はどれですか。

A、入力パラメータと出力パラメータを使用できるが、ローカル変数は使用できない。

B、入力パラメータとローカル変数を使用できるが、出力パラメータは使用できない。

<span style="color:red;background:yellow;">C、入力パラメータ、出力パラメータ、およびローカル変数。</span>

D、出力パラメータとローカル変数を使用できるが、入力パラメータは使用できない。

##### ２、次のうち、サーバーアクションのフローを設計する場合の説明として正しいものはどれですか。

A、複数のStartノードとEndノードを含めることができる。

B、Startノードは1つまたは複数含めることができるが、Endノードは1つのみ含めることができる。

<span style="color:red;background:yellow;">C、Startノードは1つのみ含めることができるが、Endノードは1つまたは複数含めることができる。</span>

D、StartノードもEndノードも1つのみ含めることができる。

##### ３、次のうち、Switch文に関するコメントとして正しくないものはどれですか。

A、条件の評価がTrueになる最初のブランチが実行される。

B、評価がTrueになるブランチがない場合、Otherwiseブランチが実行される。

C、Otherwiseブランチは必須である。

<span style="color:red;background:yellow;">D、評価がTrueになるすべてのブランチが実行される。</span>

##### ４、次のうち、アクションフロー内に複数の例外ハンドラがあるときに例外が発生した場合の説明として正しいものはどれですか。

A、実行は、常にグローバル例外ハンドラに移動される。

<span style="color:red;background:yellow;">B、実行は、例外に最も適した例外ハンドラに移動される。</span>

C、実行は、アクションのすべての例外ハンドラに移動される。

D、実行を続ける例外ハンドラを選択するためにSwitch文が必要である。

##### ５、Submitメソッドを使用してサーバーにデータが送信されるとき、OutSystemsのビルトイン検証によって検証されるのはどれですか。

A、必須の値、正しいデータ型、およびビジネスルール。

<span style="color:red;background:yellow;">B、必須の値と正しいデータ型。</span>

C、正しいデータ型とビジネスルール。

D、必須の値とビジネスルール。

##### ６、検証がClient & Serverに設定されている場合の説明として正しいものはどれですか。

A、すべての必須フィールドが空の場合、サーバー側でカスタム検証が実行される。

<span style="color:red;background:yellow;">B、ビルトイン検証はまずクライアント側で実行され、有効ではない場合、ただちにユーザーに対してエラーメッセージが表示される。</span>

C、ビルトイン検証はまずクライアント側で実行され、結果にかかわらずサーバーへのリクエストが行われ、カスタム検証が実行される。

D、Client & Server検証はない。

##### ７、ウィジェットが有効になっていない場合（ValidがFalseに設定されている場合）、インターフェイスの動作はどのようになりますか。

A、ウィジェットがグレーアウトで表示され、入力に検証エラーメッセージが表示される。	

B、ウィジェットが非表示になり、その場所に検証エラーメッセージが表示される。

<span style="color:red;background:yellow;">C、通常のウィジェットが表示され、特定のスタイル（赤枠など）が適用され、検証エラーメッセージが表示される。</span>

D、通常のウィジェットが表示され、マウスポインタを重ねると検証エラーメッセージが表示される。

##### ８、次のうち、OutSystemsのデバッガで利用できないコマンドはどれですか。

A、Stop Debugging

B、Continue Request

C、Step Over

<span style="color:red;background:yellow;">D、Restart Debugging</span>

##### ９、OutSystemsでは、デバッグ中に変数の値を検査することができます。

<span style="color:red;background:yellow;">A、TRUE</span>

B、FALSE

##### １０、ログレポートや環境の状態に関する情報を確認するときにアクセスするWebコンソールは、何という名前ですか。

A、Service Studio

<span style="color:red;background:yellow;">B、Service Center</span>

C、Log Center

D、Environment Center



---

### 七、Ajaxと再利用可能なUI

##### １、画面アクションのフローでAjax Refreshを使用して特定のウィジェットを更新することができますが、これを動作させるために必要なのはどれですか。

A、ウィジェットがTable Recordsで、Ajax Submitで画面アクションを実行する必要がある。

<span style="color:red;background:yellow;">B、ウィジェットに名前があり、Ajax Submitで画面アクションを実行する必要がある。</span>

```bash
# Ajax Refreshは名前があるウィジェットに対してのみ使用でき、メソッドがAjax Submit以外の場合は無視されます。
```

C、ウィジェットに名前があり、Submitで画面アクションを実行する必要がある。

D、ウィジェットに名前があり、Navigateで画面アクションを実行する必要がある。

##### ２、画面アクションのフローで、Refresh Dataは何のために使用しますか。

<span style="color:red;background:yellow;">A、Preparation内にある特定のクエリのデータを更新する。</span>

```bash
# Refresh Dataは、指定されたAggregateまたはSQLクエリを再実行してデータを更新します。これを使用して、Preparation内にあるAggregateとSQLクエリのデータを更新することができます。
```

B、Preparation内のすべてのクエリのデータを更新する。

C、Preparationを再実行する。

D、特定のウィジェットを更新する。

##### ３、一部のウィジェットではAjaxを使用して画面アクションをトリガーすることができます。これは、プロパティの何というセクションで定義しますか。

A、Special List

B、Events

C、On Refresh

<span style="color:red;background:yellow;">D、On ClickまたはOn Change（ウィジェットにより異なる）</span>

```bash
# Containerの場合は、［On Click］セクションです。Input、Combo Box、List Box、Check Box、Radio Buttonの場合は、［On Change］セクションです。
```

##### ４、OutSystemsでは、Webブロックは再利用可能なUIコンポーネントです。次のうち、正しくないものはどれですか。

A、再利用性が向上し、一度開発すれば何度も再利用できる。

B、独自のロジックをカプセル化する。

C、保守性が向上し、デザインや機能を変更すると、すべての利用箇所に反映される。

<span style="color:red;background:yellow;">D、再利用できるのは、一度だけである。</span>

```bash
# 一度しか使用しない場合は、おそらくWebブロックにする必要はありません。
```

##### ５、Webブロックはどこで使用できますか。

<span style="color:red;background:yellow;">A、Web画面内とWebブロック内（そのWebブロック自体は除く）。</span>

```bash
# Webブロックを他のWebブロック内で使用することはできますが、そのWebブロック内で再帰的に使用することはできません。
```

B、Web画面内とWebブロック内（そのWebブロック自体を含む）。

##### ６、Webブロックのインスタンスがウィジェットであるとき、これをAjax Refreshで更新する場合の説明として正しいものはどれですか。

A、Ajax Refreshは無視される。

B、画面全体が更新される。

<span style="color:red;background:yellow;">C、WebブロックのPreparationが実行され、Webブロックが更新される。</span>

```bash
# 正しい説明です。また、忘れずにWeb Blockウィジェットに名前を付け、Ajax Refreshで呼び出すことができるようにしてください。
```

D、Preparationが実行されないため、Webブロックはそのまま変わらない。



---

### 八、セキュリティとセッション処理

##### １、 次のうち、アプリケーションのユーザーとそのロールを作成・管理するためにOutSystemsに用意されているビルトインアプリケーションはどれですか。

A、UserMgmtアプリケーション。

<span style="color:red;background:yellow;">B、Usersアプリケーション。</span>

```bash
# Usersアプリケーションでは、エンドユーザー、ロール、グループを管理することができます。
```

C、Enterpriseアプリケーション。

D、Companyアプリケーション。

##### ２、OutSystemsには、AnonymousとRegisteredの2つのビルトインロールがあります。

A、正しくない。Anonymousロールのみがある。

B、正しくない。Registeredロールのみがある。

<span style="color:red;background:yellow;">C、正しい。Anonymousは不明なユーザー用であり、RegisteredはUsersアプリケーションで登録済みのユーザー用である。</span>

```bash
# Usersアプリケーションで登録済みのすべてエンドユーザーにはRegisteredロールが付与されます。その他のユーザーはAnonymousとみなされます。
```

##### ３、アプリケーションでロールが作成された場合のユーザー認証の管理に関する説明として正しいものはどれですか。

<span style="color:red;background:yellow;">A、Usersアプリケーションによる手動管理またはプログラムによる管理。</span>

```bash
# Usersアプリケーション以外に、カスタムロジックを使用して認証を設定することもできます。
```

B、Usersアプリケーションによる手動管理のみ。

C、Grant...およびRevoke...ロールアクションを使用したプログラムによる管理のみ。

##### ４、Web画面へのアクセスを制限するには、どのようにすればよいですか。

A、Usersアプリケーションに移動し、Web画面を特定のロールに関連付ける。

<span style="color:red;background:yellow;">B、［Web Screen Properties］ペインでロールを選択すると、実行時にOutSystemsで自動的にロールが確認される。</span>

```bash
# 複数のロールを選択することができ、ユーザーがWeb画面にアクセスしようとしたときに自動的にロール検証が実行されます。
```







## 二、他のテストリソース



---

### データベースエンティティ

##### １、次のうち、エンティティに関する説明として正しくないものはどれですか。

A、エンティティには、アトリビュートがある。

B、エンティティには、識別子が不要である。

<span style="color:red;background:yellow;">C、エンティティは、メモリ内にのみ保存される。</span>

D、エンティティは、作成、更新、削除することができる。

##### ２、HouseNumberという名前のエンティティアトリビュートを作成した場合、データ型についてはどのような操作をする必要がありますか。

A、Integerに設定する必要がある。

B、Decimalに設定する必要がある。

C、何もしない。自動的にIdentifierに設定される。

<span style="color:red;background:yellow;">D、何もしない。自動的にIntegerに設定される。</span>

##### ３、次のうち、Customerエンティティのエンティティアクションではないものはどれですか。

A、CreateCustomer

<span style="color:red;background:yellow;">B、RetrieveCustomer</span>

C、UpdateCustomer

D、DeleteCustomer

---

##### ９、アプリケーションで保存・アクセスする必要があるビジネスコンセプトは、何としてモデル化する必要がありますか。

<span style="color:red;background:yellow;">A、エンティティ</span>

B、エンティティ図

C、エンティティリレーション

D、データベーステーブル

##### １０、次のうち、OutSystemsとデータベースの間のマッピングとして正しくないものはどれですか。

A、エンティティ - テーブル

B、アトリビュート - 列

<span style="color:red;background:yellow;">C、参照アトリビュート - 主キー</span>

D、インデックス - インデックス

---

### 静的エンティティ

##### １、次のうち、静的エンティティの特性はどれですか。

A、最初のパブリッシュ以降、変更することはできない。

<span style="color:red;background:yellow;">B、一連のレコードが含まれる。</span>

C、2つのエンティティアクションがある。

D、新しいアトリビュートで拡張することはできない。

##### ２、次のうち、静的エンティティのレコードに関する説明として正しくないものはどれですか。

<span style="color:red;background:yellow;">A、4つのデフォルトアトリビュートの値を定義する必要がある。</span>

B、レコードの追加や削除は、開発中にのみ行うことができる。

C、静的エンティティの識別子はレコード識別子である。

D、識別子アトリビュートは、すべての静的エンティティで必要である。



##### ３、静的エンティティと最も似ているのは、どのプログラミング概念ですか。

A、リンクされたリスト

<span style="color:red;background:yellow;">B、エンティティ</span>

C、ハッシュマップ

D、静的変数
