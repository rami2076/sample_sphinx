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

