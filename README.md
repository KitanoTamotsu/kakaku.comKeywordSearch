## 　　Lesson31.　NatureRemoでダイソン空気清浄機を使う
#### 開発メモというかカスタマイズ方法
### 1.仕組み
　[NatureRemoのAPI](https://developer.nature.global)がhttpsで準備されています
<br>　httpsでアクセスできるので、シェルスクリプトからはcURLでコーディングします
<br>　基本的な仕組みは以上です
<br>　シェルスクリプトで動かせるので、後はAlfredに組み込みすればOK 
### 2.NatureRemoとDyson空気清浄機を連携する
　Dyson空気清浄機に付属のリモコンとNatureRemoに覚えさせます
<br>　結構リモコンのボタンがありますが、ご自身が使いたいものだけで構いません
### 3.NatureRemoのAPIを利用する
　先ず、NatureRemoのトークンを取得してAPIを利用できるようにします
<br>　トークンを取得したらワークフローの変数として設定します
<br>　具体的にはワークフロー画面右上の[χ]をクリックして環境変数tokenのvalueに設定します
<br>　このとき引用符は付けずにそのままトークンの値を記入してください　
<br>　次にアプライアンス情報をみて、NatureRemoに覚えさせたリモコンボタンの
<br>　IDを確認します。
<br>　RunScriptでは、Alfredで入力するパラメータを条件としてIDをセットするソースになって
<br>　いるので、ご自身のNatureRemoで使っているIDに変更してください
#### 背景
　Dyson Linkというスマホアプリがあって、ダイソン製品をまとめて管理できるのですが
<br>　私の場合登録できる製品は空気清浄機のみで、スマホよりもPCで操作したかったので
<br>　NatureRemoと連携させてAlfredでコントロールしてみました
#### 取扱説明
### 機能:
　NatureRemoのAPIでダイソン空気清浄機を操作する
### インストール:
　1.[alfredworkflow](https://github.com/KitanoTamotsu/dyson/releases/download/1.0/dyson.purifier.with.NatureRemo.alfredworkflow.zip)をダウンロード 
<br>　2.ファイルをダブルクリックしてワークフローに登録
<br>　3.NatureRemoのアクセス用トークンを入力し変数を設定（インストール後で可能）
<br>　 ※ワークフロー右上の[χ]をクリックして設定
<br>　4.多分スクリプトにある$IDも変更が必要（インストール後に変更）
<br>　 ※Run Scriptを開いて書き換え
### 使い方:
　Alfredからキーワード『dyson』+パラメータで起動
<br>
<br>
[トップページに戻る](https://kitanotamotsu.github.io/)

