### 学習記録
#### 2022-9-11

### 学習対象

- Djangoチュートリアル  
<br>▼仮想環境のセットアップとDjangoのインストール
    - 仮想環境
    - 仮想環境の操作
    - Djangoのインストール
    - requirementsファイルによって
    - パッケージをインストールする
    - Gitのインストール
    - GitHubのアカウント作成
    - PythonAnywhereのアカウント作成  
<br>▼Djangoってなに？
    - なぜフレームワークを必要とするか
    - 誰かがあなたのWEB サイトにリクエストを要求したときどうなりますか。
    - プロジェクトを作成しよう！
    - 設定変更
    - データベースをセットアップする
    - ウェブサーバを起動する  
<br>▼Djangoモデル
    - オブジェクト
    -  Djangoモデル
    - 新しいアプリケーションの作成
    - ブログポストモデルの作成
    - データベースにモデルのためのテーブルを作成する


### 得たこと(自分の言葉で説明できる状態)

1. 仮想環境の作成
    ```
    python3 -m venv 仮想環境名
    ```
2. 仮想環境の起動 ***※プロンプトの行頭に (myvenv) が付いたら、仮想環境起が起動されているということ**
    - Windows
    ```
    仮想環境名\Scripts\activate
    ```
    - Linux 
    ```
    source 仮想環境名/activate
    ```
3. 最新バージョンの pip がインストールされていることを確認
    ```
    python -m pip install --upgrade pip
    ```
4. Git: バージョン管理システム
5. GitHub: Gitの仕組みと連携して、他のユーザーとやりとりしやすくしているWEBサービス
6. PythonAnywhere: Pythonで書いたWebプログラムを簡単にインターネット環境で使えるようにするもの
7. Django: フレームワークのひとつ 
8. Djangoのプロジェクトを新しく作成
    - Windows
    ```
    django-admin.exe startproject mysite .
    ```
    - Linux
    ```
    django-admin startproject mysite .
    ```
9. Webサーバーを起動
   - Windows
    ```
    python manage.py runserver
    ```
    - Linux
    ```
    python manage.py runserver 0.0.0.0:8080
    ```
10. SQLiteデータベース: データベース管理システム

### 難しかったこと

- VS codeで仮想環境を有効化出来ずエラーが出てきた。
```
PS C:\Users\ahase\Desktop\HTML_CSS\djangogirls> myvenv\Scripts\active
myvenv\Scripts\active : The module 'myvenv' could not be loaded. For more information, run 'Import-Module myvenv'.
At line:1 char:1
+ myvenv\Scripts\active
+ ~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : ObjectNotFound: (myvenv\Scripts\active:String) [], CommandNotFoundException
+ FullyQualifiedErrorId : CouldNotAutoLoadModule

#調べたところ、以下のコマンドを実行したらエラーが無くなり、仮想環境を有効化ができた。

PS C:\Users\ahase\Desktop\HTML_CSS\djangogirls> Set-ExecutionPolicy -ExecutionPolicy　RemoteSigned -Scope Process
PS C:\Users\ahase\Desktop\HTML_CSS\djangogirls> myvenv\Scripts\activate
>> 
(myvenv) PS C:\Users\ahase\Desktop\HTML_CSS\djangogirls> 

```

### 解決できなかったこと
なし