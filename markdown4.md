### 学習記録
#### 2022-10-7

### 学習対象
 
<br>▼GitHubの使い方
    <br>- 学習記録の追加
<br>▼ログインページを作ろう
    <br>- Django admin
<br>▼デプロイ！
    <br>- Git
    <br>- Gitリポジトリを始める
    <br>- GitHubにコードをプッシュする
    <br>- PythonAnywhereでブログを設定する
    <br>- PythonAnywhere でサイトを設定する
    <br>- あなたのサイトをチェック！
    <br>- blogのURL
<br>▼Djangoビュー
    <br>- Djangoビュー – 今こそ作りましょう！
    <br>- blog/views.py




### 得たこと(自分の言葉で説明できる状態)

1. 作成したポストを追加、編集、削除する
    <br>〈blog/admin.py〉
    ```
    from django.contrib import admin
    from .models import Post
    admin.site.register(Post)
    ```
2. superuser （サイトの全てを管理するユーザー）を作る
    <br> 〇Windows
    ```
    (myvenv) PS C:\Users\ahase\Desktop\HTML_CSS\djangogirls> python manage.py runserver
    Watching for file changes with StatReloader
    Performing system checks...

    System check identified no issues (0 silenced).
    September 30, 2022 - 10:34:59
    Django version 3.2.15, using settings 'mysite.settings'
    Starting development server at http://127.0.0.1:8000/
    Quit the server with CTRL-BREAK.

    (myvenv) PS C:\Users\ahase\Desktop\HTML_CSS\djangogirls> python manage.py createsuperuser
    ユーザー名 (leave blank to use 'ahase'): Ayaka
    メールアドレス: ahasegawa0425@gmail.com
    Password: 
    Password (again): 
    Superuser created successfully.
    (myvenv) PS C:\Users\ahase\Desktop\HTML_CSS\djangogirls> 
    ```
    <br> 〇Linux
    ```
    ^C(myvenv) Cloud9user:~/environment/djangogirls $ python manage.py runserver
    Performing system checks...

    System check identified no issues (0 silenced).
    September 30, 2022 - 10:22:28
    Django version 2.1.15, using settings 'mysite.settings'
    Starting development server at http://127.0.0.1:8000/
    Quit the server with CONTROL-C.


    (myvenv) Cloud9user:~/environment/djangogirls $ python manage.py createsuperuser
    ユーザー名 (leave blank to use 'ec2-user'): Ayaka
    メールアドレス: ahasegawa0425@gmail.com
    Password: 
    Password (again): 
    Superuser created successfully.
    ```
3. Gitリポジトリを作成
    <br>〈command-line〉
    ```
    $ git init
    Initialized empty Git repository in ~/djangogirls/.git/
    $ git config --global user.name "Ayaka"
    $ git config --global user.email ahasegawa0425@gmail.com
    ```
4. gitignore という名前のファイルを作成し下記を書く
    <br>（Gitでコード管理したくないファイルやディレクトリを指定するためのファイル
    <br>〈.gitignore〉
    ```
    *.pyc
    *~
    /.vscode
    __pycache__
    myvenv
    db.sqlite3
    /static
    .DS_Store
    ```
5. リポジトリにファイルを作成・追加した状態でgit statusコマンドを実行
    <br>〈command-line〉
    ```
    (myvenv) PS C:\Users\ahase\Desktop\HTML_CSS\djangogirls> git status
    On branch master

    No commits yet

    Untracked files:
    (use "git add <file>..." to include in what will be committed)
            .gitignore
            blog/
            manage.py
            mysite/
            requirements.txt
    ```
6. blog ディレクトリの下に、新しく urls.pyファイルを作って下記を入力
    <br>〈blog/urls.py〉
    ```
    from django.urls import path
    from . import views

    urlpatterns = [
        path('', views.post_list, name='post_list'),
    ]
    nothing added to commit but untracked files present (use "git add" to track)
    ```
7. 変更内容を保存
    <br>〈command-line〉
    ```
    (myvenv) PS C:\Users\ahase\Desktop\HTML_CSS\djangogirls> git commit -m "My Django Girls app, first commit"
    [master (root-commit) f049fd3] My Django Girls app, first commit
    16 files changed, 276 insertions(+)
    create mode 100644 .gitignore
    create mode 100644 blog/__init__.py
    create mode 100644 blog/admin.py
    create mode 100644 blog/apps.py
    create mode 100644 blog/migrations/0001_initial.py
    create mode 100644 blog/migrations/__init__.py
    create mode 100644 blog/models.py
    create mode 100644 blog/tests.py
    create mode 100644 blog/views.py
    create mode 100644 manage.py
    create mode 100644 mysite/__init__.py
    create mode 100644 mysite/asgi.py
    create mode 100644 mysite/settings.py
    create mode 100644 mysite/urls.py
    create mode 100644 mysite/wsgi.py
    create mode 100644 requirements.txt
    ```
8. GitHub.comにアクセスし、新しいリポジトリ（"my-first-blog"）を作成
9. 自分のコンピューター上のGitリポジトリをGitHub上のGitリポジトリに結びつける
    <br>〈command-line〉
    ```
    (myvenv) PS C:\Users\ahase\Desktop\HTML_CSS\djangogirls> git remote add origin https://github.com/Ayaka-Nicholes/my-first-blog.git           
    (myvenv) PS C:\Users\ahase\Desktop\HTML_CSS\djangogirls> git push -u origin master
    ```
10. PythonAnywhereにWebアプリケーションをデプロイする
    <br>〈PythonAnywhere command-line〉
    ```
    $ pip3.6 install --user pythonanywhere
    ```
11. GitHub からアプリを自動的に構成するためのヘルパーを実行
    <br>〈PythonAnywhere command-line〉
    ```
    pa_autoconfigure_django.py --python=3.6　https://github.com/Ayaka-Nichols/my-first-blog.git
    ```
12. PythonAnywhereとあなたのPC上のデータベースは別物なのでcreatesuperuserで管理者アカウントを初期化する
    <br>〈PythonAnywhere command-line〉
    ```
    python manage.py createsuperuser
    ```
13. PythonAnywhereのWebページをクリックするとwebサイトが閲覧できる
14. DjangoのURLを作る：
    <br>'http://127.0.0.1:8000/' をブログの入口ページにして、投稿したブログポストのリストを表示するようにする
    <br>〈mysite/urls.py〉
    ```
        from django.contrib import admin
    from django.urls import path, include

    urlpatterns = [
        path('admin/', admin.site.urls),
        path('', include('blog.urls')),
    ]
    ```
15. blogのURLを作る：
    <br>Blogディレクトリの下にurls.pyというファイルを作り下記を入力
    <br>〈blog/urls.py〉
    ```
        from django.urls import path
    from . import views

    urlpatterns = [
        path('', views.post_list, name='post_list'),
    ```
16. Djangoビューを作る：
    <br>blog /views.pyに下記を入力
    ```
    def post_list(request):
    return render(request, 'blog/post_list.html', {})
    ```
17. http://127.0.0.1:8000/ を確認すると、TemplateDoesNotExistというエラーが現れる。
    <br>→テンプレートを作る



### 難しかったこと

1. 自分のコンピューター上のGitリポジトリをGitHub上のGitリポジトリに結びつける際、
git push -u origin masterを入力しても上手くいかず、下記が表示された

    ```
    (myvenv) PS C:\Users\ahase\Desktop\HTML_CSS\djangogirls> git push -u origin master
    error: failed to push some refs to 'github.com:USERNAME/REPO.git'
    ```
    - 　やったこと：sshキーを作成し、下記を入力したらpushできた
    ```(myvenv) PS C:\Users\ahase\Desktop\HTML_CSS\djangogirls> git remote set-url origin git@github.com:Ayaka-Nichols/my-first-blog.git
    (myvenv) PS C:\Users\ahase\Desktop\HTML_CSS\djangogirls> git push origin main
    ```
    <br>

2. GitHub からアプリを自動的に構成するためのヘルパーを実行しても仮想環境に入れなかった。
    <br>〈PythonAnywhere command-line〉
    ```
    09:17 ~ $ pa_autoconfigure_django.py --python=3.7 https://github.com/Ayaka-Nichols/my-first-blog.git
    < Running API sanity checks >
    \
        ~<:>>>>>>>>>
    Traceback (most recent call last):
    File "/home/Nichols/.local/bin/pa_autoconfigure_django.py", line 49, in <module>
        main(
    File "/home/Nichols/.local/bin/pa_autoconfigure_django.py", line 30, in main
        project.sanity_checks(nuke=nuke)
    File "/home/Nichols/.local/lib/python3.10/site-packages/pythonanywhere/project.py", line 24, in sanity_checks
        self.webapp.sanity_checks(nuke=nuke)
    File "/home/Nichols/.local/lib/python3.10/site-packages/pythonanywhere/api/webapp.py", line 40, in sanity_checks
        raise SanityException(
    pythonanywhere.exceptions.SanityException: You already have a webapp for nichols.pythonanywhere.com.
    Use the --nuke option if you want to replace it.
    ```
    - 下記を入力すると実行できた。
    ```
    pa_autoconfigure_django.py --python=3.7 https://github.com/Ayaka-Nichols/my-first-blog.git  --nuke
    ```





### 解決できなかったこと
なし