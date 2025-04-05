# Get started はじめに


## 第１節：　［エクシェル］生成までの手順


### 手順１：　インポート

```py
import exshell as xs

from pathlib import Path
```

👆　特に決まりはありませんが、本記事では `xs` という別名を付けるとしましょう。  
`Path` は、ファイルを扱うのに便利です。  


### 手順２：　ファイルパス定数

```py
PATH_TO_EXSHELL_CONFIG = './exshell_config.toml'
PATH_TO_EXSHELL_WORKSHEET = './temp/exshell_work.xlsx'
```

👆　２つのファイルの置き場を決めておきましょう。  
１つは設定ファイル、もう１つはテンポラリー・ファイルです。  


### 手順３：　エクシェル・ビルダーの生成

```py
# ［エクシェル・ビルダー］生成
exshell_builder = xs.ExshellBuilder(
        abs_path_to_workbook=Path(PATH_TO_EXSHELL_WORKSHEET).resolve())
```

👆　［エクシェル］を作る前に、先に［エクシェル・ビルダー］を作ってください。  
引数の `abs_path_to_workbook` には、テンポラリー・ファイルへの絶対パスを設定してください。  


### 手順４：　エクシェル設定ファイルの読込

```py
# ［エクシェル設定ファイル］読込
exshell_builder.load_config(
        abs_path=Path(PATH_TO_EXSHELL_CONFIG).resolve(),
        create_if_not_exists=True)
```

👆　［エクシェル・ビルダー］を使って、［エクシェル設定ファイル］を読込んでください。  


### 手順５：　エクシェル設定ファイルが読込めなかったら、手動作成のチュートリアルを動かす

```py
# エクシェル設定ファイルが不完全ならチュートリアル開始
if not exshell_builder.config_is_ok():
    exshell_builder.start_tutorial()
```

👆　［エクシェル設定ファイル］が読込めなかったら、簡単なチュートリアルを行って  
手動で設定ファイルを作るよう促します。  


### 手順６：　エクシェル生成

```py
# ［エクシェル］生成
exshell = exshell_builder.build()
exshell_builder = None
```

👆　［エクシェル］を生成できたら、［エクシェル・ビルダー］は不要です。  
以降、［エクシェル］を使っていけます。  


## 第２節：　エクシェルの利用


### 手順７：　インポート

```py
import openpyxl as xl
```

👆　画面の作成には、`openpyxl` を使います。  


### 手順８：　画面作成

```py
# ワークブックを新規生成
wb = xl.Workbook()

# ワークシート
ws = wb['Sheet']

cell = ws[f'A1']
cell.value = "Hello, world!"

# ワークブック保存
exshell.save_workbook(wb=wb)
```

👆　［エクシェル］の `save_workbook()` メソッドを使って、ワークブックを保存してください。  


### 手順９：　仮想画面を開く

```py
# エクセル開く
exshell.open_virtual_display()
```

👆　つまり、さっき作ったワークシートが開かれます。  


### 手順１０：　任意で入力を取る

```py
line = input('数字入れろ')
print() # 空行
```

👆　好きなように入力を促してください。  
［エクシェル］には関係ありません。  


### 手順１１：　仮想画面を閉じる

```py
# エクセル閉じる
exshell.close_virtual_display()
```

👆　さっき開いたエクセルを閉じます。  

［エクシェル］はこのように、エクセルの開閉をするだけです。  
