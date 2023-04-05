# OSテスト

## セクション後のテスト

### 一、Web開発の概要

---

##### １、OutSystemsで作成できるのは、どのタイプのアプリケーションですか。

 <span style="color:red;background:yellow;">A、Web、モバイル、およびサービス</span>

```bash
# OutSystemsのアプリケーションは、Web、モバイル、サービスのいずれかです。
```

B、Web、モバイル、サービス、および拡張機能

C、モジュールと拡張機能

D、Webのみ

##### ２、次のうち、プロデューサモジュール内の要素の公開に関する説明として正しいものはどれですか。

A、任意の要素を公開でき、同じアプリケーションのモジュールでのみ再利用できる。

B、任意の要素を公開でき、任意のアプリケーションのモジュールで再利用できる。

<span style="color:red;background:yellow;">C、Publicプロパティが［Yes］に設定されている要素のみを公開でき、任意のアプリケーションのモジュールで再利用できる。</span>

```bash
# 要素を他のモジュールで利用するには、Publicプロパティが［Yes］に設定されている必要があります。
```

D、Publicプロパティが［Yes］に設定されている要素のみを公開でき、同じアプリケーションのモジュールでのみ再利用できる。

##### ３、次のうち、コンシューマモジュールに関する説明として正しいものはどれですか。

A、同じアプリケーションのプロデューサモジュールからのみ要素を再利用できる。

<span style="color:red;background:yellow;">B、プロデューサモジュール内で公開されている要素のみを再利用できる。</span>

```bash
# モジュール内の公開要素のみを環境内の他のモジュールが再利用できます。
```

C、任意のプロデューサモジュールから任意の要素を再利用できる。

D、他のアプリケーションのプロデューサモジュールからのみ要素を再利用できる。



---

### 二、データのモデリング

##### １、 OutSystemsは、基盤となる開発者用のデータベーステーブルを管理しますか。

<span style="color:red;background:yellow;">A、はい</span>

```bash
# エンティティ、アトリビュート、インデックスは、モジュールのパブリッシュ時にプラットフォームで自動的に管理されます。
```

B、いいえ

##### ２、エンティティとアトリビュートは、データベースで何として作成されますか。

<span style="color:red;background:yellow;">A、テーブルと列</span>

```bash
# エンティティは、データベーステーブルに保持されます。新しいレコードは対応するテーブルに行として挿入されます。
```

B、テーブルとインデックス

C、インデックスと列

D、テーブルと制約

##### ３、「TotalCount」という名前のアトリビュートは、OutSystemsで自動的にどのデータ型に設定されますか。

A、Text

<span style="color:red;background:yellow;">B、Integer</span>

```bash
# 名前に基づいて自動的にデータ型が推定されます。*CountはIntegerにマッピングされます。
```

C、Boolean

D、Date

##### ４、エンティティはCRUD操作のためのエンティティアクションとともに作成されますが、次のうちどれですか。

A、Insert、Update、Delete

<span style="color:red;background:yellow;">B、Create、CreateOrUpdate、Update、Get、GetForUpdate、Delete</span>

```bash
# OutSystemsで定義されたエンティティには、これらのエンティティアクションがあります。静的エンティティの場合は、Getエンティティアクションのみです。
```

C、GET、POST、DELETE

D、Add、Change、Remove

##### ５、入力パラメータは常に必須です。

A、TRUE

<span style="color:red;background:yellow;">B、FALSE</span>

```bash
# Is Mandatoryプロパティを使用して、入力パラメータを必須に設定することができます。
```

##### ６、出力パラメータはどこで使用できますか。

A、実装スコープ内のみ。

B、実装スコープ外のみ。

<span style="color:red;background:yellow;">C、実装スコープ内と実装スコープ外の両方。</span>

```bash
# 値をスコープ内の出力パラメータに値を割り当て、スコープ外に返すようにする必要があります。
```

##### ７、ストラクチャが持つことができるアトリビュートのデータ型はどれですか。

A、Basic、Complex、およびRecord

B、Basic、String、およびObject

<span style="color:red;background:yellow;">C、Basic、Structure、Entity、およびList</span>

```bash
# これら4つはOutSystemsのデータ型です。なお、Basic内には、Text、Integer、Email、Currencyなどが含まれます。
```

D、BasicとListのみ。

##### ８、次のうち、OutSystemsのリストに関する説明として正しいものはどれですか。

<span style="color:red;background:yellow;">A、同じデータ型の要素の集合。</span>

```bash
# OutSystemsのリストは一様、つまり、すべての要素のデータが同じです。
```

B、データ型が異なる可能性がある要素の集合。



---

### 三、基本的な画面開発1

##### １、Widget Treeは何を表しますか。

A、画面のライフサイクルフロー。

<span style="color:red;background:yellow;">B、画面上のウィジェットの階層。</span>

```bash
# Widget Treeに表示されるツリー状のストラクチャを使用して、開発者は画面のストラクチャを参照し、微調整することができます。
```

C、アプリケーションの画面のリスト。

D、既存の画面テンプレート。

##### ２、画面内で作成できるのは、どの型の変数ですか。

A、ローカル変数のみ。

B、入力パラメータのみ。

<span style="color:red;background:yellow;">C、入力パラメータとローカル変数。</span>

```bash
# そのとおりです。画面に出力パラメータはありません。
```

D、入力パラメータ、出力パラメータ、ローカル変数。

##### ３、画面のPreparationの主な目的は何ですか。

A、描画するウィジェットを決定する。

<span style="color:red;background:yellow;">B、データベースからデータを取得する。</span>

```bash
# 画面を描画するときに使用するデータは、画面のPreparationを使用して取得します。
```

C、フォームのデータをサーバーに送信する。

D、ユーザーを適切な画面にリダイレクトする。

##### ４、 画面のライフサイクルでは、Preparationはブラウザで実行されます。

A、正しい

<span style="color:red;background:yellow;">B、誤り</span>

```bash
# Preparationには、画面を描画する前に実行されるサーバー側のロジックが含まれます。
```

##### ５、Aggregateの［Sources］セクションは、何のために使用しますか。

A、Aggregateの出力レコードをテストするための値を定義するため。

<span style="color:red;background:yellow;">B、レコードの取得元となるエンティティを定義するため。</span>

```bash
# そのとおりです。Aggregateは、リレーションが定義されている1つ以上のソースエンティティをサポートします。
```

C、特定のレコードのサブセットを取得する条件を定義するため。

D、Aggregateの出力レコードの順序を定義するため。

##### ６、Aggregateの［Test Values］セクションは、何のために使用しますか。

<span style="color:red;background:yellow;">A、Aggregateのプレビューデータをテストするための値を定義するため。</span>

```bash
# Test Valuesセクションは、Aggregateをテストして出力レコードをプレビューするために使用します。 ［Filters］セクションと［Sort］セクションで使用する変数のテスト値を設定することができます。
```

B、すべてのレコードではなく特定のレコードを取得するための条件を設定するため。

C、Aggregateの出力レコードの順序を定義するため。

D、レコードの取得元となるエンティティを定義するため。

##### ７、Aggregateから返されるレコード数を制限するには、どのようにすればよいですか。

<span style="color:red;background:yellow;">A、Max. Recordsプロパティを使用する。</span>

```bash
# Max. Recordsは、データベースから取得されるレコードの最大数を定義します。
```

B、Length値を使用する。

C、Count値を使用する。

D、［Sorting］を使用する。

##### ８、Aggregateによって生成されたSQLを参照することができます。

<span style="color:red;background:yellow;">A、正しい</span>

```bash
# Executed SQLプロパティで、Aggregateによって生成されるSQLを参照することができます。
```

B、誤り

８、次のうち、Expressionウィジェットに関する説明として正しいものはどれですか。

A、静的なテキストのみを表示する。

<span style="color:red;background:yellow;">B、実行時に計算されたテキストを表示する。</span>

```bash
# Expressionウィジェットには「計算された」値が表示されます。この値は実行時に評価され、変数などに応じて変わります。
```

##### ９、次のうち、Imageウィジェットに関する説明として正しいものはどれですか。

A、静的な画像のみを表示する。

B、URLで指定された画像のみを表示する。

C、データベース内に保存されている画像のみを表示する。

<span style="color:red;background:yellow;">D、静的な画像、URLにある画像、データベース内の画像を表示する。</span>

```bash
# 画像のソースはTypeプロパティで定義します。Static、External、Databaseが選択可能な値です。
```

##### １０、次のうち、Table Recordsウィジェットに関する説明として正しいものはどれですか。

A、レコードを1列に1件ずつの表形式レイアウトで表示する。

<span style="color:red;background:yellow;">B、レコードを1行に1件ずつの表形式レイアウトで表示する。</span>

```bash
# Table Recordsウィジェットは、レコードのリストを表示するときに使用します。 各行がレコードに対応し、多くの場合、列はレコードのアトリビュートです。
```

C、レコードを1テーブルに1件ずつの表形式レイアウトで表示する。

D、レコードを自由形式で表示する。

##### １１、Formウィジェットでは、InputウィジェットとLabelウィジェットのみを使用できます。

A、TRUE

<span style="color:red;background:yellow;">B、FALSE</span>

```bash
# このウィジェットのレイアウトは自由度が高く、ニーズに応じて様々なウィジェットを追加したり整理したりできます。
```



---

### 四、データリレーションのモデリング

##### １、エンティティ識別子は単純な主キーまたは複合キーにすることができます。

A、TRUE

<span style="color:red;background:yellow;">B、FALSE</span>

```bash
# OutSystemsは、デフォルトでは複合キーをサポートしていませんが、インデックスを使用してその動作を模倣することができます。
```

##### ２、OutSystemsで実装できるリレーションのタイプをすべて挙げてください。

A、1対多と多対多。

<span style="color:red;background:yellow;">B、1対1、1対多、および多対多。</span>

```bash
# OutSystemsでは、これら3つのタイプのデータリレーションを使用して、リッチなデータモデルを実装することができます。
```

C、1対1と1対多。

D、多対多。

##### ３、多対多のリレーションで、交差エンティティに最低限必要なアトリビュートは何ですか。

A、各親エンティティを参照する複合キー。

<span style="color:red;background:yellow;">B、識別子と各親エンティティに対する外部キー。</span>

```bash
# 交差エンティティにはそれ自体の識別子と、リレーションの各エンティティの参照識別子があります。
```

C、各親エンティティに対する外部キーと交差レコード数。

D、Id、Label、Order、Is Active。

##### ４、エンティティからレコードを削除すると、外部キー参照を使用するエンティティのレコードがすべて削除されます。 この場合、どの削除規則が使用されていますか。

A、Protect

<span style="color:red;background:yellow;">B、Delete</span>

```bash
# 「Delete」は、削除されるレコードに対する外部キー参照を持つすべてのレコードのカスケード削除を実行します。
```

C、Ignore



---

### 五、基本的な画面開発2

##### １、On ClickプロパティではLinkとButtonの動作を定義できます。次のうち、説明として正しいものはどれですか。

A、Linkでできるのは、画面への移動のみである。

B、Buttonでできるのは、リクエストの送信のみである。

<span style="color:red;background:yellow;">C、LinkとButtonでできるのは、画面への移動やリクエストの送信である。</span>

```bash
# ユーザーは、LinkやButtonをクリックまたはタップすることにより、アプリケーションを操作できます。これにより、アクションをトリガーしたり、データを送信したり、別の画面に移動することができます。
```

D、LinkとButtonでできるのは、画面への移動のみである。

##### ２、次のうち、Navigateメソッドを使用するButtonをクリックした後の画面のライフサイクルの順序として正しいものはどれですか。

<span style="color:red;background:yellow;">A、Preparationを実行した後、遷移先画面を描画する。</span>

```bash
# ボタンをクリックすると、サーバーで遷移先画面のPreparationが処理され、ブラウザ上に描画するデータが準備されます。
```

B、画面アクションを実行し、Preparationを実行し、遷移先画面を描画する。

C、遷移先画面を描画した後、その画面のPreparationを実行する。

D、Preparationを実行した後、画面アクションを実行する。

##### ３、次のうち、Submitメソッドが使用するHTTPリクエストメソッドはどれですか。

A、PUT

<span style="color:red;background:yellow;">B、POST</span>

```bash
# POSTメソッドは、ファイルをアップロードするときやフォームのデータを送信するときによく使用されます。
```

C、GET

D、PATCH

##### ４、画面アクションをEnd要素で終了した場合と「(Current Screen)」へのDestinationで終了した場合の結果は同じになります。

A、TRUE

<span style="color:red;background:yellow;">B、FALSE</span>

```bash
# そのとおりです。Endの場合は画面の変数とウィジェットの値が保持されるのに対し、Destinationの場合はデフォルト値にリセットされます。
```

##### ５、次のうち、2つのエンティティ間で「With or Without」結合を実行したときに返されるのはどれですか。

A、両方のエンティティのすべてのレコードを返す（FULL OUTER JOIN）。

B、2つのエンティティの間で対応するレコードのみを返す（INNER JOIN）。

<span style="color:red;background:yellow;">C、右のエンティティに対応するレコードがない場合でも、左のエンティティのレコードをすべて返す（LEFT JOIN）。</span>

```bash
# 「A Customer With or Without Orders」は、SQLの「...Customer LEFT JOIN Order...」に相当します。
```

D、左のエンティティに対応するレコードがない場合でも、右のエンティティのレコードをすべて返す（RIGHT JOIN）。

##### ６、 次のうち、Aggregateで列が非表示になっている場合の説明として正しいものはどれですか。

A、Aggregateの出力に含まれなくなる。

<span style="color:red;background:yellow;">B、引き続きAggregateの出力に含まれる。</span>

```bash
# 列を非表示にしても、Aggregateの出力には影響を及ぼしません。ただし、OutSystemsでは、クエリの外で使用されている出力アトリビュートに基づいて取得される列が最適化されます。
```

C、これらの列のみがAggregateの出力になる。

D、その理由は、これらがデータベースで空であるためである。

##### 7、次のうち、Sum、Average、Min、Max、Countなどの集約関数をアトリビュートで使用した場合の説明として正しいものはどれですか。

A、アトリビュートの集約結果が他のエンティティアトリビュートとともにAggregateの出力に追加される。

<span style="color:red;background:yellow;">B、アトリビュートの集約結果のみがAggregateの出力に含まれる。</span>

```bash
# アトリビュートを集約するとAggregateの出力が変わり、計算後の集約された列のみが返されます。 Aggregateの出力に含まれるアトリビュートはすべて青色で表示されるため、視覚的に検証することができます。
```

##### ８、次のうち、SQLクエリ内でエンティティおよびエンティティアトリビュートの名前を記述する場合の正しい構文はどれですか。

A、<Entity>と<Entity>.[Attribute]

B、{Entity}と{Entity}.<Attribute>

<span style="color:red;background:yellow;">C、{Entity}と{Entity}.[Attribute]</span>

```bash
# エンティティ名を{Entity}と記述し、アトリビュート名を{Entity}.[Attribute]と記述します。
```

D、<Entity>と<Entity>.<Attribute>

##### ９、SQLクエリでは、SELECT文のみを実行できます。

A、TRUE

<span style="color:red;background:yellow;">B、FALSE</span>

```bash
# たとえば、DELETE、INSERT、UPDATEなどのSQL文をSQLクエリで使用できます。
```

##### １０、Check Boxウィジェットがバインドされるのは、どの型の変数ですか。

A、Text

B、Integer

<span style="color:red;background:yellow;">C、Boolean</span>

```bash
# Check BoxウィジェットはBoolean型変数にバインドされ、チェックの有無に応じて変数をTrueまたはFalseに設定します。
```

D、Date

##### １１、Combo Boxウィジェットでは、ドロップダウンリストの選択肢の中から値を1つ選択することができます。次のうち、できないことはどれですか。

A、Source Entityプロパティを使用して、エンティティまたは静的エンティティから選択肢を取得する。

B、Source Record Listプロパティを使用して、レコードのリストから選択肢を取得する。

<span style="color:red;background:yellow;">C、Special Listセクションを使用して、エンティティまたは静的エンティティから選択肢を取得する。</span>

```bash
# Special Listの値は英数字の値のペアのみで構成されている必要があります。
```

D、Special Listセクションを使用して、特殊な選択肢を手動で設定する。

##### １２、Combo Boxウィジェットに表示される値のリストでは、エンティティと特殊リストを組み合わせることができます。

<span style="color:red;background:yellow;">A、正しい</span>

```bash
# エンティティまたはレコードリストで提供される値と特殊リストの他の値と組み合わせることができます。
```

B、誤り



---

### 六、ロジックとバリデーション

##### １、次のうち、サーバーアクションで使用できる変数はどれですか。

A、入力パラメータと出力パラメータを使用できるが、ローカル変数は使用できない。

B、入力パラメータとローカル変数を使用できるが、出力パラメータは使用できない。

<span style="color:red;background:yellow;">C、入力パラメータ、出力パラメータ、およびローカル変数。</span>

```bash
# サーバーアクションを使用することにより、コードの再利用性が向上し、任意のアクションフロー内で呼び出すことができます。
```

D、出力パラメータとローカル変数を使用できるが、入力パラメータは使用できない。

##### ２、次のうち、サーバーアクションのフローを設計する場合の説明として正しいものはどれですか。

A、複数のStartノードとEndノードを含めることができる。

B、Startノードは1つまたは複数含めることができるが、Endノードは1つのみ含めることができる。

<span style="color:red;background:yellow;">C、Startノードは1つのみ含めることができるが、Endノードは1つまたは複数含めることができる。</span>

```bash
# アクションフローにはStartノードを1つのみ含めることができ、異なるEndノードまたはRaise Exceptionノードで終了することができます。
```

D、StartノードもEndノードも1つのみ含めることができる。

##### ３、次のうち、Switch文に関するコメントとして正しくないものはどれですか。

A、条件の評価がTrueになる最初のブランチが実行される。

B、評価がTrueになるブランチがない場合、Otherwiseブランチが実行される。

C、Otherwiseブランチは必須である。

<span style="color:red;background:yellow;">D、評価がTrueになるすべてのブランチが実行される。</span>

```bash
# Switchのいずれかのブランチのみが実行されます。具体的には、評価がTrueになる最初のブランチです。Trueになるブランチがない場合は、Otherwiseが実行されます。
```

##### ４、次のうち、アクションフロー内に複数の例外ハンドラがあるときに例外が発生した場合の説明として正しいものはどれですか。

A、実行は、常にグローバル例外ハンドラに移動される。

<span style="color:red;background:yellow;">B、実行は、例外に最も適した例外ハンドラに移動される。</span>

```bash
# 例外によって処理を担当するハンドラは異なります。
```

C、実行は、アクションのすべての例外ハンドラに移動される。

D、実行を続ける例外ハンドラを選択するためにSwitch文が必要である。

##### ５、Submitメソッドを使用してサーバーにデータが送信されるとき、OutSystemsのビルトイン検証によって検証されるのはどれですか。

A、必須の値、正しいデータ型、およびビジネスルール。

<span style="color:red;background:yellow;">B、必須の値と正しいデータ型。</span>

```bash
# OutSystemsの入力ウィジェットのビルトイン検証では、必須フィールドが入力されているかどうかと、入力された値が変数のデータ型に適合しているかどうかが検証されます。
```

C、正しいデータ型とビジネスルール。

D、必須の値とビジネスルール。

##### ６、検証がClient & Serverに設定されている場合の説明として正しいものはどれですか。

A、すべての必須フィールドが空の場合、サーバー側でカスタム検証が実行される。

<span style="color:red;background:yellow;">B、ビルトイン検証はまずクライアント側で実行され、有効ではない場合、ただちにユーザーに対してエラーメッセージが表示される。</span>

```bash
# ビルトイン検証はまずクライアント側で実行され、データ型がまだ適合していない場合にサーバーへの不要なリクエストが行われないようにします。
```

C、ビルトイン検証はまずクライアント側で実行され、結果にかかわらずサーバーへのリクエストが行われ、カスタム検証が実行される。

D、Client & Server検証はない。

##### ７、ウィジェットが有効になっていない場合（ValidがFalseに設定されている場合）、インターフェイスの動作はどのようになりますか。

A、ウィジェットがグレーアウトで表示され、入力に検証エラーメッセージが表示される。	

B、ウィジェットが非表示になり、その場所に検証エラーメッセージが表示される。

<span style="color:red;background:yellow;">C、通常のウィジェットが表示され、特定のスタイル（赤枠など）が適用され、検証エラーメッセージが表示される。</span>

```bash
# 赤枠によって無効なウィジェットが視覚的にユーザーに示され、エラーメッセージによって問題の内容とその修正方法がわかります。
```

D、通常のウィジェットが表示され、マウスポインタを重ねると検証エラーメッセージが表示される。

##### ８、次のうち、OutSystemsのデバッガで利用できないコマンドはどれですか。

A、Stop Debugging

B、Continue Request

C、Step Over

<span style="color:red;background:yellow;">D、Restart Debugging</span>

```bash
# インスタンスの実行中にデバッグを再開することはできません。ただし、停止してからもう一度開始することは可能です。
```

##### ９、OutSystemsでは、デバッグ中に変数の値を検査することができます。

<span style="color:red;background:yellow;">A、TRUE</span>

```bash
# コードのデバッグ中、スコープに基づいて変数の値を検査することができます。
```

B、FALSE

##### １０、ログレポートや環境の状態に関する情報を確認するときにアクセスするWebコンソールは、何という名前ですか。

A、Service Studio

<span style="color:red;background:yellow;">B、Service Center</span>

```bash
# Service Centerは、環境の運用管理を実行できるWebコンソールです。
```

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

##### ５、推奨されるセッション変数のデータ型はどれですか。

A、任意のデータ型を使用できる。

B、Basic型およびStructures型。

<span style="color:red;background:yellow;">C、Basic型およびEntity Identifier型。</span>

```bash
# セッションに配置する情報はできるだけ少なくし、大きいレコードやレコードリストは特に避けます。
```

D、Basic型およびEntity型。

##### ６、次のうち、ユーザーセッションのライフサイクルに関する説明として正しいものはどれですか。

A、ユーザーがアプリケーションで認証を行ったときに開始し、終了することはない。

B、ユーザーがアプリケーションで認証を行ったときに開始し、ログアウトまたはタイムアウトで終了する。

C、アプリケーションに最初にアクセスしたとき（匿名アクセスを含む）に開始し、終了することはない。

<span style="color:red;background:yellow;">D、アプリケーションに最初にアクセスしたとき（匿名アクセスを含む）に開始し、ログアウトまたはタイムアウトで終了する。</span>

```bash
# セッションは最初のアクセス時に自動的に開始し、タイムアウト（通常20分）後に自動的に終了します。
```

##### ７、Service Centerでサイトプロパティの値を変更し、実行時のアプリケーションの動作を変更することができます。

<span style="color:red;background:yellow;">A、TRUE</span>

```bash
# 設計時にデフォルト値を設定し、Service Centerで変更してセッションをまたいで適用することができます。
```

B、FALSE



---

### 九、Webサービス

##### １、 SOAP Webサービスを利用するには、どのようにすればよいですか。

A、WSDLを指定（エンドポイントURLを指定するか、ファイルをアップロード）し、バインディングを選択（複数ある場合）すると、すべてのメソッドが自動的に利用される。

<span style="color:red;background:yellow;">B、WSDLを指定（エンドポイントURLを指定するか、ファイルをアップロード）し、バインディングを選択（複数ある場合）し、利用するメソッドを選択する。</span>

```bash
# SOAP 1.1および1.2にバインディングされた1つ以上のメソッドを利用することができます。「(Select All)」オプションもあります。
```

##### ２、REST APIを利用する場合に単一のRESTメソッドを利用してできることはどれですか。

<span style="color:red;background:yellow;">A、メソッドのURLを指定し、パラメータ値を入力し（該当する場合）、テストを実行してJSONレスポンスを取得し、JSONレスポンスを本文にコピーする。</span>

```bash
# テストを実行してJSONレスポンスを取得する代わりに、REST APIドキュメントでメソッドと予測されるJSONレスポンスを参照します。そのJSONを本文にコピーすることもできます。
```

B、WSDLを指定（エンドポイントURLを指定するか、ファイルをアップロード）し、バインディングを選択（複数ある場合）し、利用するメソッドを選択する。

##### ３、RESTサービスを利用する場合に外部サービスに送信されるリクエストをカスタマイズするには、どのコールバックアクションを使用する必要がありますか。

A、On Consume

<span style="color:red;background:yellow;">B、On Before Request</span>

```bash
# これを使用して、URL、リクエストテキスト、ヘッダーなど、元のリクエストの情報を変更することができます。
```

C、On After Response

D、On REST Request

##### ４、OutSystemsでREST APIを公開することはできますか。

<span style="color:red;background:yellow;">A、はい</span>

```bash
# REST APIサービスを提供するには、公開するREST APIを作成し、それにRESTメソッドを追加し、サーバーアクションとして実装します。
```

B、いいえ



---

### 十、テーマと高度なUI

##### １、テーマは、アプリケーションの画面のルックアンドフィールを定義します。次のうち、テーマを直接適用できるものはどれですか。

A、モジュール、UIフロー、個別の画面またはWebブロック。

B、モジュール、UIフロー、個別の画面。

<span style="color:red;background:yellow;">C、モジュールまたはUIフロー。</span>

```bash
# 各モジュールにはデフォルトのテーマがありますが、各UIフローには固有のテーマがある場合があります。
```

D、モジュールのみ。

##### ２、スタイルクラスは上書きすることができます。Webブロック、画面、テーマで同じスタイルクラスが定義されている場合、どの定義が適用されますか。

A、Webブロック。

<span style="color:red;background:yellow;">B、画面。</span>

```bash
# 画面（またはメール）のスタイルシートは、最後に読み込まれます。最初にWebブロック、次にテーマ、最後に画面（またはメール）のスタイルシートが読み込まれます。
```

C、テーマ。

D、UIフロー。

##### ３、スタイルクラスは上書きすることができます。Webブロック、画面、テーマで同じスタイルクラスが定義されている場合、どの定義が適用されますか。

A、はい

<span style="color:red;background:yellow;">B、いいえ</span>

```bash
# 前のレイアウトWebブロックを使用してすでに作成されている画面は影響を受けません。必要な場合は、それらの画面に移動して手動で変更します。
```

##### ４、画面のメニューオプションを作成するには、画面をメニュー上にドラッグ&ドロップするだけです。

<span style="color:red;background:yellow;">A、TRUE</span>

```bash
# デフォルトのMenu Webブロック（Common UIフローの下）を使用する場合、画面をメニューにドラッグ&ドロップするだけで、画面の名前が付いた新しいメニューオプションが自動的に作成されます。
```

B、FALSE

##### ５、優れたUIパターンを備えた画面を設計するためのウィジェットがOutSystems UIおよびリッチウィジェットで提供されており、これらはService Studioツールボックスで利用できます。

<span style="color:red;background:yellow;">A、正しい</span>

```bash
# これらのウィジェットは、ドラッグ&ドロップするだけで簡単に画面に配置することができるビルド済みのUIパターンです。
```

B、誤り

##### ６、次のうち、リッチウィジェットのList_Navigationウィジェットに関する説明として正しいものはどれですか。

<span style="color:red;background:yellow;">A、複数のページを持つTable Recordsのナビゲータであり、定義されている数の要素を各ページに表示する。</span>

```bash
# このウィジェットにより、複数のページを持つテーブルでページネーション機能を使用することができます。
```

B、複数のページを持つFormのナビゲータであり、定義されている数の要素を各ページに表示する。

##### ７、次のうち、リッチウィジェットのList_SortColumnウィジェットに関する説明として正しいものはどれですか。

A、Formの列をクリックすると、その列でソートすることができる。

<span style="color:red;background:yellow;">B、Table Recordsの列をクリックすると、その列でソートすることができる。</span>

```bash
# このウィジェットを使用すると、列をクリックすることによりTable Recordsが更新され、新しい順序で行が表示されるアクションを実行できます。
```

##### ８、アプリケーション開発を高速化するため、OutSystemsには一般的なシナリオ向けのロジックとデータを含むビルド済みの画面が用意されています。

<span style="color:red;background:yellow;">A、TRUE</span>

```bash
# これらのビルド済みの画面は画面テンプレートであり、サンプルデータを使用してUIに入力したりロジックを有効にしたりします。
```

B、FALSE

##### ９、次のうち、テンプレートを使用して画面を作成する場合の説明として正しいものはどれですか。

A、画面を作成するためにサンプルデータを含むテンプレートのコピーが作成される。サンプルデータを置き換えることはできない。

<span style="color:red;background:yellow;">B、画面を作成するためにサンプルデータを含むテンプレートのコピーが作成される。サンプルデータを実際のデータに置き換えることができる。</span>

```bash
# 作成される画面は、レイアウト、ウィジェット、スタイル、ロジックなど、テンプレートのすべてをコピーしたものです。
```

##### １０、自動データ置換を備えたウィジェット（Tables Records、List Records、Formなど）のデータを置き換えるには、どのようにすればよいですか。

A、ウィジェットを右クリックして、［Import Data from Entity］を選択する。

B、ウィジェットを削除し、適切なエンティティを使用してもう一度作成する。

<span style="color:red;background:yellow;">C、エンティティをウィジェットにドラッグ&ドロップする。</span>

```bash
# この機能を使用すると、サンプルデータを独自のアプリケーションデータにすばやく置き換えることができます。
```

D、エンティティを右クリックして、［Import Data from Excel］を選択する。

##### １１、リスト画面と詳細画面を作成するには、どのようにすればよいですか。

A、エンティティをUIフローにドラッグ&ドロップすると、リスト画面と詳細画面が自動的に作成される。

<span style="color:red;background:yellow;">B、エンティティをUIフローにドラッグ&ドロップしてリスト画面を作成し、この手順を繰り返して詳細画面を作成する。</span>

```bash
# スキャフォールディングパターンを使用すると、データ駆動型の画面の作成を自動化することができ、簡単な画面やロジックを数回のクリックで作成できます。
```



---

## 他のテストリソース

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
