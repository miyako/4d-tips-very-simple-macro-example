![version](https://img.shields.io/badge/version-18%2B-EB8E5F)
[![license](https://img.shields.io/github/license/miyako/4d-tips-very-simple-macro-example)](LICENSE)

# 4d-tips-very-simple-macro-example
マクロを使用してメソッドの履歴を保存する例題

#### 使い方（シンプル）

```4d
$History:=History 
```

メソッドのソースファイルを書き出すフォルダーは，データベースフォルダーの「History」となります。  
マクロイベントで呼び出すフォーミュラは，コンポーネント内のものが使用されます。  

#### 使い方（カスタム）

```4d
$folder:=Folder(fk desktop folder).folder("TEST")
$onSave:=Formula(onSave )
$threshold:="seconds"
$History:=History .setFolder($folder).setMethod($onSave).setThreshold($threshold)
```

または

```4d
$folder:=Folder(fk desktop folder).folder("TEST")
$onSave:=Formula(onSave )
$threshold:="seconds"
$History:=History ($folder;$onSave;$threshold)
```

`$folder`: メソッドのソースファイルを書き出すフォルダー  
`$onSave`: `on_save`および`on_close`マクロイベントで呼び出すフォーミュラ  
`$threshold`: フォルダー名をインクリメントする単位（デフォルトでは「分単位」）

メソッドが保存される度に「.save」というフォルダーにファイルが作成されます（保存前の内容）。  

メソッドエディターが閉じられる度に「.close」というフォルダーにファイルが作成されます（保存後の内容）。  

<img width="618" alt="result" src="https://user-images.githubusercontent.com/1725068/118444287-e2b43300-b727-11eb-84df-4731c97232a4.png">


