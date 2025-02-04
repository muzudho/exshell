# Get started はじめに


## 手順１：　インポート

```py
import exshell as xs

from pathlib import Path
```

👆　特に決まりはありませんが、`xs` という別名を付けるとしましょう。  
`Path` は、ファイルを扱うのに便利です。  


## 手順２：　ファイルパス定数

```py
PATH_TO_EXSHELL_CONFIG = './exshell_config.toml'
PATH_TO_EXSHELL_WORKSHEET = './temp/exshell_work.xlsx'
```

👆　２つのファイルの置き場を決めておきましょう。  
１つは設定ファイル、もう１つはテンポラリー・ファイルです。  


## 手順３：　エクシェル・ビルダーの生成

```py
# ［エクシェル・ビルダー］生成
exshell_builder = xs.ExshellBuilder(
        abs_path_to_workbook=Path(PATH_TO_EXSHELL_WORKSHEET).resolve())
```

👆　［エクシェル］を作る前に、先に［エクシェル・ビルダー］を作ってください。  
引数の `abs_path_to_workbook` には、テンポラリー・ファイルへの絶対パスを設定してください。  


## 手順４：　エクシェル設定ファイルの読込

```py
# ［エクシェル設定ファイル］読込
exshell_builder.load_config(
        abs_path=Path(PATH_TO_EXSHELL_CONFIG).resolve(),
        create_if_not_exists=True)
```

👆　［エクシェル・ビルダー］を使って、［エクシェル設定ファイル］を読込んでください。  


## 手順５：　エクシェル設定ファイルが読込めなかったら、手動作成のチュートリアルを動かす

```py
# エクシェル設定ファイルが不完全ならチュートリアル開始
if not exshell_builder.config_is_ok():
    exshell_builder.start_tutorial()
```

👆　［エクシェル設定ファイル］が読込めなかったら、簡単なチュートリアルを行って  
手動で設定ファイルを作るよう促します。  


## 手順６：　エクシェル生成

```py
# ［エクシェル］生成
exshell = exshell_builder.build()
exshell_builder = None
```

👆　［エクシェル］を生成できたら、［エクシェル・ビルダー］は不要です。  
以降、［エクシェル］を使っていけます。  
