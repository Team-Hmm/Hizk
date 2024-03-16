[Hizk - GPT-4搭載の「意味から変換する」次世代IME](https://github.com/Team-Hmm/Hizk)
===================================
Copyright 2010-2024 Google LLC  
Copyright 2024-2024 kokastar,YukkuriPanda 

System Requirements
-------
64bit Windows10以降をサポートします。  
LinuxやMacOSでは動作しません。  
また、ビルド時に十分なストレージ容量が必要となります。  

プログラムの仕様上トロイの木馬と同じ挙動をするため、ウイルス対策ソフトによっては誤検知されることがあります。その場合は、ウイルス対策ソフトの設定を変更するか、このソフトウェアを使用しないでください。

How to Use
-------
How to Build の章に従いビルドを行ってください。    
その後生成される.msiファイルを実行してインストールすれば導入完了です。   

Win+SpaceキーでIMEを切り替えて入力をします。変換したい文字列の最後に「。」を入れて変換することで、意味から変換することができます。  

How to Build
-------
1.[OpenAI API key](https://platform.openai.com/api-keys)を取得してください。   
2.[Visual Studio 2022 Community Edition](https://visualstudio.microsoft.com/downloads/#visual-studio-community-2022)をインストールします。この時、以下の項目をインストールするようにしてください。  
- 「Desktop development with C++」
- 「Git for Windows」
- 「Windows11 SDK」    

3.Python3(3.9以降)をMicrosoft Store等でインストールしてください。    
4.Developer PowerShell for VS 2022を起動してください。今後のコマンドはすべてここで実行してください。    
5.このリポジトリをクローンして、srcディレクトリに移動します。    
```
git clone https://github.com/Team-Hmm/Hizk.git
cd mozc\src
```
6.[src\converter\segments.h](src/converter/segments.h)の1行目`YOUR_API_KEY`の部分を、1.で取得したAPIキーに書き換えます。
7.以下のコマンドを実行して、追加のツール([Ninja 1.11.0](https://github.com/ninja-build/ninja/releases/download/v1.11.0/ninja-win.zip)・[Qt 6.6.2](https://download.qt.io/archive/qt/6.6/6.6.2/submodules/qtbase-everywhere-src-6.6.2.tar.xz)・[WiX 3.14](https://github.com/wixtoolset/wix3/releases/download/wix314rtm/wix314-binaries.zip)・[git submodules](../.gitmodules))を入手します。
```
python -m pip install six requests
python build_tools/update_deps.py
```
8.ビルドシステムのセットアップを行うために以下のコマンドを実行します。
```
"C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Auxiliary\Build\vcvarsamd64_x86.bat"
```
9.QtとHizkのビルドを以下のコマンドで行います。
```
python build_mozc.py gyp
python build_mozc.py build -c Release package
```
10.以下のコマンドを実行するか、`src\out_win\Release\Mozc64.msi`を実行してインストールします。
```
out_win\Release\Mozc64.msi
```

License
-------

All Hizk code written by Google & Team-Hmm is released under
[The BSD 3-Clause License](http://opensource.org/licenses/BSD-3-Clause).
For third party code under [src/third_party](src/third_party) directory,
see each sub directory to find the copyright notice.  Note also that
outside [src/third_party](src/third_party) following directories contain
third party code.

### [src/data/dictionary_oss/](src/data/dictionary_oss)
Mixed.
See [src/data/dictionary_oss/README.txt](src/data/dictionary_oss/README.txt)

### [src/data/test/dictionary/](src/data/test/dictionary)
The same to [src/data/dictionary_oss/](src/data/dictionary_oss).
See [src/data/dictionary_oss/README.txt](src/data/dictionary_oss/README.txt)

### [src/data/test/stress_test/](src/data/test/stress_test)
Public Domain.  See the comment in
[src/data/test/stress_test/sentences.txt](src/data/test/stress_test/sentences.txt)

### [src/data/unicode/](src/data/unicode)
UNICODE, INC. LICENSE AGREEMENT.
See each file header for details.
