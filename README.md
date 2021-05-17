![version](https://img.shields.io/badge/version-18%2B-EB8E5F)
[![license](https://img.shields.io/github/license/miyako/4d-tips-very-simple-macro-example)](LICENSE)

# 4d-tips-very-simple-macro-example
マクロを使用してメソッドの履歴を保存する例題

#### 使い方

```4d
$folder:=Folder(fk desktop folder).folder("TEST")
$onSave:=Formula(onSave )
$History:=History .setFolder($folder).setMethod($onSave)
```

または

```4d
$folder:=Folder(fk desktop folder).folder("TEST")
$onSave:=Formula(onSave )
$History:=History ($folder;$onSave)
```

`$folder`: メソッドのソースファイルを書き出すフォルダー  
`$onSave`: `on_save`および`on_close`マクロイベントで呼び出すフォーミュラ

デフォルトでフォルダー名は「分単位」で作成されます。

秒あるいは時間にすることもできます。

```4d
$History.setThreshold("hours")
$History.setThreshold("minutes")
$History.setThreshold("seconds")
```
