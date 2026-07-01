> [!note]
> このノートは削除しても構いません。
> ただの取説です。

# ノートの種類
- Classノート  
  目次とまとめの役割を担います。
  "Add Page"ボタンから新規ページを作成することができます。
  "Add Flash"ボタンからフラッシュカード用のノートを作成できます。
- 通常ノート  
	- ただのノート  
	    実際に記述を行うノートです。
	    全てタグで管理されます。
	- Flashノート  
	  フラッシュカード用のノートです。
	  Spaced Repetitionからフラッシュカードとして読み込むことができます。

# ディレクトリ構成
- Class  
  Classノートが配置されます。
- Pages  
  通常ノートが配置されます。
- Refs  
  ノート内で使う画像などのデータが配置されます。
- Template  
  テンプレートノートが配置されています。

# 使い方
- [[Home.canvas]]がメインのノートです。  
- ノートは階層分けされません。  
  -> タグで管理されます。
- Classノートには"目次とまとめ"の役割があり、Classノートから作成されたノートには、自動的にタグ付けが行われます。  
  -> [[Home.canvas]]上の"Add Page"ボタンから作成したノートにはタグが付与されません。

# 新規ノートの命名規則について
　デフォルト状態では"Add Page"および"Add Flash"で追加されるノートの名前は`生成元のClass名 + ファイル生成時の時間`になっています。ファイル名に時間を埋め込んでいる理由は、ファイル名の衝突を回避するため(ファイル名に一意にするため)です。しかし、明らかにファイル名が読みづらくなっています。ノートのタイトルは別で管理しているので慣れれば問題ないはずですが、それでも使いづらいと言う人のために、ファイル名にノートタイトルを埋め込む方法を紹介しておきます。
　`Template/`配下にある`Flash`、`Page`、`Page-ask-title`の三つのファイルに対して次のような変更を加えてください。

`Flash`と`Page`に対する変更
```
let title = tp.file.title;
await tp.file.rename(title + tp.date.now("YYYYMMDDHHMMSS"));
```
->
```
let title = await tp.system.prompt("Title");
await tp.file.rename(title;
```

`Page-ask-title`に対する変更
```
let title = await tp.system.prompt("Title");
await tp.file.rename(title + tp.date.now("YYYYMMDDHHmmss"));
```
->
```
let title = await tp.system.prompt("Title");
await tp.file.rename(title;
```

# 導入されているプラグイン
- Advanced Tabled  
  表作成の補助を行います。
- BRAT  
  ベータ版のプラグインの管理を行います。
  コミュニティプラグインとして配布される前のプラグインの導入に利用します。
- Chem  
  化学式などのレンダリングを補助します。
- Current View  
  ファイルを開いたときの表示モードを固定します。
  Classノートは編集モードではなくプレビューモードで開きたいので、事前に表示モードをプレビューに固定するために利用しています。
- Dataview  
  動的に動作するリストを生成します。
- Desmos  
  グラフなどのレンダリングを行います。
- Excalidraw  
  手書きなどに対応したホワイトボードを追加します。
- Git  
  保管庫全体をGit管理します。
- Homepage  
  指定したノートをホームページとして扱い、起動時に表示したり、ショートカットからホームページを開いたりできます。
- Iconize  
  ファイルエクスプローラー画面でファイル名の隣にアイコンを設定できるようになります。
- Image Converter  
  画像を貼り付けるときに画像サイズを変更できるようになります。
- JS Engine  
  Dataviewプラグインを強化するために必要です。
- Latex Suite  
  Tex入力を支援してくれます。
- Link Embed  
  リンクを貼り付けるときに埋め込み表示してくれます。
- Masking Type  
  "\=="で囲んだところを穴埋め問題にしたりできます。
- Mermaid Tools  
  Mermaid記法を支援してくれます。
- Meta Bind  
  ボタンとかを追加してくれます。
- Mindmap NextGen  
  マインドマップをMarkdownベースの記述方法で作成できます。
- Minimal Theme Settings  
  Minimalというテーマをカスタマイズできるプラグインです。
- Obsidian Functionplot  
  グラフ描画ようです。
- Shiki Highlighter  
  コードスニペットを見やすくしてくれます。
- Sortable  
  表のソートを可能にします。
- Spaced Repetition  
  単語帳機能を追加します。
- Style Settings  
  テーマやCSSの変数を変更できるようになります。
- Tasks  
  Todoを管理しやすくします。
- Templater  
  テンプレートノートから新しいノートを作成できるようになります。
- TikZJax  
  Latex系の機能を強化します。
- Typewiter Scroll  
  文字を書くときに自動的にノートをスクロールしてくれます。
- Typing Assistant  
  "/"を入力すると事前に設定したショートカットを発動呼び出せます。