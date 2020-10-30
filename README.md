# Sphinx環境構築手順を作成していためのリポジトリ

## Supports Environment

|||
|--|---------|
|OS|Windows10|
|Editor|VSCode|

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
  pip --version
  ```


### Sphinx環境

  ```
   pip install sphinx
  ```

## TestProjectを立ち上げてみる。
- ディレクトリを作成する。
  ```
  mkdir test_document
  cd test_document
  ```




