## 　　Lesson4.　シェルスクリプトでURLエンコードする
#### 開発メモ
### 1.検索結果のURLを解析する
　試しに[価格コム](https://kakaku.com)で『時計』と検索してみましょう
<br>　リターンされたブラウザのURLはこうなっています
<br>　`https://kakaku.com/search_results/%8E%9E%8Cv/`
<br>　％の部分は日本語をエンコードしたものでしょう
<br>　URLでたまに見かけますが、日本語のままではうまく稼働しないブラウザに
<br>　対応するためコード化しています
<br>　URLでは基本的にUTF-8を使うものと思っていたのですが違うようです
<br>　
<br>　ネットの世界は便利なもので、デコードサイトがあるので確認したら
<br>　Shift-JISでした
<br>　ということは、上記リターンのURLの%部分を作ればOKですね
###　2.シェルスクリプトで％エンコードする
　シェルスクリプトで実施するにはnkfコマンドを利用するそうです
<br>　試しにターミナル.appで叩いてたら、nkfがない！
<br>　nkfコマンドはインストールが必要なようです
<br>　その前提のパッケージ管理ソフトhomebrewも導入が必要でした
<br>　
<br>　苦労して前提ができたところでAlfredのスクリプトを作成
<br>　実装したコードはたった3行。キモとなるのは下記のコード
<br>　```　open "https://kakaku.com/search_results/"`echo -n $query | nkf -WsMQ | tr = % ` ```
<br>　バックスラッシュはコマンドの結果を返します
<br>　結果の文字列をそのままURLと連結してOpenしています
<br>　シェルスクリプトはワンライナーで書くことがよくあるので慣れが必要
<br>　ちなみに$queryはalfredの入力パラメータ＝検索キーワード
<br>　nkfでs-jisに変換すると=つきのコードが返ってくるので
<br>　trで=を%に置き換えています
###　そのた
　・Alfredのインプットキーワドを”価格”、"Kakaku"として、
<br>　　日本語でも英数でも起動できるようにしています（バイリンガル起動）
<br>　・nkfのパスを環境変数PATHに指定しています
<br>　　なので、それぞれの環境にあわせた変更が必要です　
<br>　　（そもそもnkfをパスの通った場所におくべきだったかな）
#### 背景
　価格コムはカメラ、パソコン、家電関連を買う時に参考にするぐらいですが
<br>　URLに％エンコードがあったので題材としました　

#### 取扱説明
### 機能:
　価格コム	を検索する
<br>　※URLのための％エンコードを実装したワークフローです
### インストール:
　1.[alfredworkflow](https://github.com/KitanoTamotsu/kakaku.comKeywordSearch/releases/download/1.1/kakaku.com.KeywordSearch.alfredworkflow.zip)をダウンロード 
<br>　2.ファイルをダブルクリックしてワークフローに登録
### 使い方:
　Alfredからキーワード『kakaku』or『価格』　+　検索したい文字列
<br>
<br>
[トップページに戻る](https://kitanotamotsu.github.io/)

