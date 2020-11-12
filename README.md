# Sphinx環境構築手順を作成していためのリポジトリ

## Supports Environment

|||
|--|---------|
|OS|Windows10|
|VSCode|1.50.1|
|chocolatey|0.10.11|
|Python|3.9.0|
|pip|20.2.3|
|Sphinx|3.2.1|

## 手順
好きなターミナルを開きます。  
開くときは、権利者権限モードで開いてください。

### Python環境の構築

- chocolateyのインストール
  ```
  Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
  ```

- Pythonのインストール
  ```
  choco install python
  ```

- Python系のパッケージインストーラpipのインストール
  ```
   python -m pip install -U pip
  ```

- 新しいterminalを開き、pythonのバージョンが3系であることを確認します。
  ```
  python --version
  ```

- pipインストールの確認
  ```
  pip show sphinx
  ```

### Sphinx環境
- Sphinxインストール
  ```
   pip install sphinx
  ```
- Sphinxバージョン確認
  ```
   pip install sphinx
  ```

## TestProjectを立ち上げてみる。
- ディレクトリを作成する。
  ```
  mkdir test_document
  cd test_document
  ```

- とりあえずクイックスタートコマンドを使用してみる。  
  ```
  下記の質問以外はEnterでスルーする。
  Separate source and build directories (y/n) [n]: y
  Project name: test_document
  Author name(s): nyx
  Project language [en]: ja
  ```
  - コマンド  
  ```
  sphinx-quickstart
  ```
  - 実行結果
  ```
  $ sphinx-quickstart
  Welcome to the Sphinx 3.2.1 quickstart utility.
  
  Please enter values for the following settings (just press   Enter to
  accept a default value, if one is given in brackets).
  
  Selected root path: .
  
  You have two options for placing the build directory for   Sphinx output.
  Either, you use a directory "_build" within the root path,   or you separate
  "source" and "build" directories within the root path.
  > Separate source and build directories (y/n) [n]: y
  
  The project name will occur in several places in the built   documentation.
  > Project name: test_document
  > Author name(s): nyx
  > Project release []:      
  
  If the documents are to be written in a language other   than English,
  you can select a language here by its language code.   Sphinx will then
  translate text that it generates into that language.
  
  For a list of supported codes, see
  https://www.sphinx-doc.org/en/master/usage/configuration.  html#confval-language.
  > Project language [en]: ja
  
  Creating file   C:\Users\nyx\Documents\sphinx-sample\source\conf.py.
  Creating file   C:\Users\nyx\Documents\sphinx-sample\source\index.rst.
  Creating file   C:\Users\nyx\Documents\sphinx-sample\Makefile.
  Creating file C:\Users\nyx\Documents\sphinx-sample\make.  bat.
  
  Finished: An initial directory structure has been created.
  
  You should now populate your master file   C:\Users\nyx\Documents\sphinx-sample\source\index.rst and   create other documentation
  source files. Use the Makefile to build the docs, like so:
     make builder
  where "builder" is one of the supported builders, e.g.   html, latex or linkcheck.
  ```

ディレクトリの中身の状態を確認する。
```
cmd //c tree //f
```

下記のように出力される。
```
$  cmd //c tree //f
フォルダー パスの一覧:  ボリューム Windows
ボリューム シリアル番号は 3A86-E7F1 です
C:.
│  make.bat
│  Makefile
│  README.md
│
├─build
├─source
│  │  conf.py
│  │  index.rst
│  │
│  ├─_static
│  └─_templates
└─test_document
```




HTMLの作成コマンド
```
./make.bat html
```

HTML作成実施時
```
$ ./make.bat html
Running Sphinx v3.2.1
loading translations [ja]... done
making output directory... done
building [mo]: targets for 0 po files that are out of date
building [html]: targets for 1 source files that are out of date
updating environment: [new config] 1 added, 0 changed, 0 removed
reading sources... [100%] index
looking for now-outdated files... none found
pickling environment... done
checking consistency... done
preparing documents... done
writing output... [100%] index
generating indices...  genindexdone
writing additional pages...  searchdone
copying static files... ... done
copying extra files... done
dumping search index in Japanese (code: ja)... done
dumping object inventory... done
build succeeded.

The HTML pages are in build\html.
```

再度中身を確認する。
```
$ cmd //c tree //f
フォルダー パスの一覧:  ボリューム Windows
ボリューム シリアル番号は 3A86-E7F1 です
C:.
│  make.bat
│  Makefile
│  README.md
│
├─build
│  ├─doctrees
│  │      environment.pickle
│  │      index.doctree
│  │
│  └─html
│      │  .buildinfo
│      │  genindex.html
│      │  index.htstart .ml
│      │  objects.inv
│      │  search.html
│      │  searchindex.js
│      │
│      ├─_sources
│      │      index.rst.txt
│      │
│      └─_static
│              alabaster.css
│              basic.css
│              custom.css
│              doctools.js
│              documentation_options.js
│              file.png
│              jquery-3.5.1.js
│              jquery.js
│              language_data.js
│              minus.png
│              plus.png
│              pygments.css
│              searchtools.js
│              translations.js
│              underscore-1.3.1.js
│              underscore.js
│
├─source
│  │  conf.py
│  │  index.rst
│  │
│  ├─_static
│  └─_templates
└─test_document
```

HTMLが生成されるのでブラウザで確認する。
```
build\html\index.html
```

デザインテーマの追加
```
pip install cloud-sptheme
```

設定ファイルの値の変更
```
# conf.py
html_//theme = 'cloud'
```


