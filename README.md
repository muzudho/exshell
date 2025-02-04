# Exshell

Excel をディスプレイと見立てたコンソール・アプリケーションを作るライブラリー。  


## 事前設定

* 構成
    * Windows 11 で動作確認しました
    * デスクトップ・アプリ版の Microsoft Excel がインストールされていることが必要です
* 手順
    * [インストールの手順](https://github.com/muzudho/exshell/blob/main/docs/how_to_install.md)


## Exshell ライブラリーの使用例。サンプル・プログラムの動かし方

Exshell ライブラリーの使用例は、以下の［Create a color palette］リポジトリーの実装を参考にしてください。  

* 📖 [GitHub > Muzudho > Create a color palette](https://github.com/muzudho/create-a-color-palette)  


### 大まかな紹介

［Create a color palette］リポジトリーを展開したディレクトリーで、以下のコマンドを打鍵してください。  

```shell
py gradation.py
```

![エクセルのパスを入力](https://github.com/muzudho/exshell/raw/main/docs/img/202502__pg__01-2259--excel-path.png)  

👆　上図。　EXCEL.exe ファイルへのパスを入力してください。  

![コンフィグ設定](https://github.com/muzudho/exshell/raw/main/docs/img/202502__pg__01-2303--config-setup.png)  

👆　このアプリケーションが、 Excel を自動的に開けるようになりました。  

以下、自動的に Excel を開いたり閉じたりが行われます。（下図）  
ターミナルを見たり、 Excel を見たりしてください。  

![色相選択](https://github.com/muzudho/exshell/raw/main/docs/img/202502__pg__01-2310--select-hue.png)  

👆　開かれたワークシートを参考に、番号を入力してください。  

![色の数指定](https://github.com/muzudho/exshell/raw/main/docs/img/202502__pg__01-2312--number-of-colors.png)  

👆　Excel が開かれないこともあります。色の数を指定してください。  

![彩度の選択](https://github.com/muzudho/exshell/raw/main/docs/img/202502__pg__01-2315--select-saturation.png)  

👆　同様。  

![明度の選択](https://github.com/muzudho/exshell/raw/main/docs/img/202502__pg__01-2318--select-brightness.png)  

👆　同様。  

![グラデーションの出力](https://github.com/muzudho/exshell/raw/main/docs/img/202502__pg__01-2319--output-gradation.png)  

👆　グラデーションが出力されました。  
