# 学習記録
#### 2022-10-7 ~ 10-14

## 学習対象
 
<br>▼HTML 入門
    <br>- HTMLとは？
    <br>- 最初のテンプレート
    <br>- HeadとBody
    <br>- テンプレートのカスタマイズ
    <br>- もう一つ: デプロイしましょう！
    <br>- Githubに自分のコードをPushしてみよう
    <br>- 新しいコードをPythonAnywhereにpullして、自分のウェブアプリを再度実行させる
<br>▼DjangoのORMとクエリセット
    <br>- クエリセットとは？
    <br>- Django shell
    <br>- すべてのオブジェクト
    <br>- オブジェクトの作成
    <br>- オブジェクトの抽出
    <br>- オブジェクトの並び替え
    <br>- メソッドチェーンによる複雑なクエリ
    <br>▼テンプレート内の動的データ
    <br>- クエリセット
<br>▼Djangoテンプレート
    <br>- テンプレートタグとは？
    <br>- ブログ一覧テンプレートの表示
    <br>- もう一つ...





## 得たこと(自分の言葉で説明できる状態)

1. blogディレクトリの中にtemplatesという名前のディレクトリ、templatesディレクトリの中にblogというのディレクトリを作成する 
    ```
   blog
    └───templates
        └───blog
    ```
2. blog/templates/blogディレクトリの中に、post_list.htmlファイルを作成し、下記を入力
    <br>〈blog/templates/blog/post_list.html〉
    ```
    <html>
        <head>
            <title>Django Girls blog</title>
        </head>
        <body>
            <div>
                <h1><a href="/">Django Girls Blog</a></h1>
            </div>

            <div>
                <p>published: 14.06.2014, 12:14</p>
                <h2><a href="">My first post</a></h2>
                <p>Aenean eu leo quam. こんにちは！ よろしくお願いします！ </p>
            </div>

            <div>
                <p>公開日: 2014/06/14, 12:14</p>
                <h2><a href="">2番目の投稿</a></h2>
                <p> こんにちは！ よろしくお願いします！ </p>
            </div>
        </body>
    </html>
    ```
3. Githubに自分のコードをPush
    <br>→　$ git statusを実行
    <br>〈command-line〉
    ```
    (myvenv) PS C:\Users\ahase\Desktop\HTML_CSS\djangogirls> git status
    On branch main
    Changes not staged for commit:
    (use "git add <file>..." to update what will be committed)
    (use "git restore <file>..." to discard changes in working directory)
            modified:   blog/views.py
            modified:   mysite/urls.py

    Untracked files:
    (use "git add <file>..." to include in what will be committed)
            blog/templates/
            blog/urls.py
    no changes added to commit (use "git add" and/or "git commit -a")
    ```
4. git に対してこのディレクトリ内の変更を全て反映させるよう指示する
    <br>→　git add --all .を実行
    <br>〈command-line〉
    ```
        $ git add --all .
    ```
5. 全てのファイルをアップロードする前に、gitが何をアップロードするのかチェックする
    <br>→　$ git statusを実行
    <br>〈command-line〉
    ```
        (myvenv) PS C:\Users\ahase\Desktop\HTML_CSS\djangogirls> git status
    On branch main
    Changes to be committed:
    (use "git restore --staged <file>..." to unstage)
            new file:   blog/templates/blog/post_list.html
            new file:   blog/urls.py
            modified:   mysite/urls.py
    ```
6.  何を変更したのか説明するコミットメッセージを残す
    <br>→　git commit -m "メッセージ"　を実行
    <br>〈command-line〉
    ```
    (myvenv) PS C:\Users\ahase\Desktop\HTML_CSS\djangogirls> git commit -m "Changed the HTML for the site."
    [main 8c84bb4] Changed the HTML for the site.
    4 files changed, 32 insertions(+), 2 deletions(-)
    create mode 100644 blog/templates/blog/post_list.html
    create mode 100644 blog/urls.py
    ```
7. GitHubに変更部分をアップロード(push) する
    <br>→　git push -uを実行
    <br>〈command-line〉
    ```
        (myvenv) PS C:\Users\ahase\Desktop\HTML_CSS\djangogirls> git push -u
    fatal: The current branch main has no upstream branch.
    To push the current branch and set the remote as upstream, use

        git push --set-upstream origin main

    To have this happen automatically for branches without a tracking
    upstream, see 'push.autoSetupRemote' in 'git help config'.
    Writing objects: 100% (10/10), 1.25 KiB | 212.00 KiB/s, done.
    Total 10 (delta 3), reused 0 (delta 0), pack-reused 0
    remote: Resolving deltas: 100% (3/3), completed with 3 local objects.
    To github.com:Ayaka-Nichols/my-first-blog.git
    b19af9d..8c84bb4  main -> main
    branch 'main' set up to track 'origin/main'.
    ```
8. 新しいコードをPythonAnywhereにpullして、自分のウェブアプリを再度実行させる
    <br>→　cd ~/<your-pythonanywhere-domain>.pythonanywhere.comを実行
    <br>→　git pullを実行
    <br>〈PythonAnywhere command-line〉
    ```
    (nichols.pythonanywhere.com) 00:57 ~ $ cd ~/nichols.pythonanywhere.com
    (nichols.pythonanywhere.com) 00:58 ~/nichols.pythonanywhere.com (main)$ git pull
    remote: Enumerating objects: 15, done.
    remote: Counting objects: 100% (15/15), done.
    remote: Compressing objects: 100% (5/5), done.
    remote: Total 10 (delta 3), reused 10 (delta 3), pack-reused 0
    Unpacking objects: 100% (10/10), 1.23 KiB | 8.00 KiB/s, done.
    From https://github.com/Ayaka-Nichols/my-first-blog
    b19af9d..8c84bb4  main       -> origin/main
    Updating b19af9d..8c84bb4
    Fast-forward
    blog/templates/blog/post_list.html | 21 +++++++++++++++++++++
    blog/urls.py                       |  6 ++++++
    blog/views.py                      |  2 ++
    mysite/urls.py                     |  5 +++--
    4 files changed, 32 insertions(+), 2 deletions(-)
    create mode 100644 blog/templates/blog/post_list.html
    create mode 100644 blog/urls.py
     ```
9. - PythonAnywhereの「Files」ページでコードがダウンロードされたことを確認。
    - PythonAnywhereの「Web」ページへ移動して、アプリのReloadボタンをクリック
        <br>→　ウェブサイトを開いて、動いているか確認
***
10. Django shellを起動する
    <br>→　python manage.py shellを実行
    <br>〈command-line〉
    ```
    (myvenv) PS C:\Users\ahase\Desktop\HTML_CSS\djangogirls> python manage.py shell
    Python 3.10.7 (tags/v3.10.7:6cc6b13, Sep  5 2022, 14:08:36) [MSC v.1933 64 bit (AMD64)] on win32
    Type "help", "copyright", "credits" or "license" for more information.
    (InteractiveConsole)
    >>>
    ```
11. Djangoの管理画面から作ったポストのリストを表示させてみる
    <br>①　blog.models から Post モデルをインポート
    <br>〈command-line〉
    ```
    >>> from blog.models import Post
    ```
    <br>②　Post.objects.all()を実行
    <br>〈command-line〉
    ```
    >>> Post.objects.all()
     <QuerySet [<Post: 日記１>, <Post: 日記２>, <Post: 日記３>, <Post: 日記４>, <Post: 日記５>]>
    ```
12. コンソール画面から、新たにポストを作ってみる
    <br>①　Userモデルを先にインポートする。作成しておいたスーパーユーザ（Ayaka）を取り出す。
    <br>〈command-line〉
    ```
    >>> from django.contrib.auth.models import User
    >>> User.objects.all()
    <QuerySet [<User: Ayaka>]>
    >>> me = User.objects.get(username='Ayaka')
    ```
    <br>②　コンソール画面から、ポストを作成する
    <br>→　>>> Post.objects.create(author=me, title='Sample title', text='Test')を実行
    <br>〈command-line〉
    ```
    >>> Post.objects.create(author=me, title='Sample title', text='Test')
    <Post: Sample title>
    ```
    <br>③　ポストが作成出来ているか、確認してみる
    <br>→　>>> Post.objects.all()を実行
    <br>〈command-line〉
    ```
    >>> Post.objects.all()
    <QuerySet [<Post: 日記１>, <Post: 日記２>, <Post: 日記３>, <Post: 日記４>, <Post: 日記５>, <Post: Sample title>]>
    ```
    <br>④　さらに投稿を追加してみる
    <br>〈command-line〉
    ```
    >>> Post.objects.create(author=me, title='Sample title2', text='Test')
    <Post: Sample title2>
    >>> Post.objects.all()
    <QuerySet [<Post: 日記１>, <Post: 日記２>, <Post: 日記３>, <Post: 日記４>, <Post: 日記５>, <Post: Sample title>, <Post: Sample title2>]>
    ```
13. オブジェクトの抽出(Ayakaのポストだけを取り出したい場合)
    <br>→　Post.objects.filter(author=me)を実行
    <br>〈command-line〉
    ```
    >>> Post.objects.filter(author=me)
    <QuerySet [<Post: 日記１>, <Post: 日記２>, <Post: 日記３>, <Post: 日記４>, <Post: 日記５>, <Post: Sample title>, <Post: Sample title2>]>
    ```
14. オブジェクトの抽出（title フィールドに title という単語が含まれているポストだけを取り出したい場合）
    <br>→　Post.objects.filter(title__contains='title')を実行
    <br>〈command-line〉
    ```
    >>> Post.objects.filter(title__contains='title')
    <QuerySet [<Post: Sample title>, <Post: Sample title2>]>
    ```
15. オブジェクトの抽出（公開済みの全ポストを取り出したい場合）
    <br>①　コンソールから追加したポストがまだ公開されていない場合は、まずポストを公開する
    - まず公開するポストを決める
    <br>〈command-line〉
    ```
    >>> post = Post.objects.get(title="Sample title")
    ```
    - publish メソッドを呼び出す
    <br>〈command-line〉
    ```
    >>> post.publish()
    ```
    <br>②　公開済みの全ポストを取り出す
    <br>→　Post.objects.filter(published_date__lte=timezone.now())を実行
    <br>〈command-line〉
    ```
    >>> Post.objects.filter(published_date__lte=timezone.now())
    <QuerySet [<Post: Sample title>]>
    ```
16. オブジェクトのリストの並べ替えをしてみる
    <br>→　Post.objects.order_by('created_date')を実行
    <br>〈command-line〉
    ```
    >>> Post.objects.order_by('created_date')
    <QuerySet [<Post: 日記１>, <Post: 日記２>, <Post: 日記３>, <Post: 日記４>, <Post: 日記５>, <Post: Sample title>, <Post: Sample title2>]>
    ```
17. 逆順（新しく追加した順）に並べ替えてみる
   <br>→　Post.objects.order_by('-created_date')を実行
    <br>〈command-line〉
    ```
    >>> Post.objects.order_by('-created_date')
    <QuerySet [<Post: Sample title2>, <Post: Sample title>, <Post: 日記５>, <Post: 日記４>, <Post: 日記３>, <Post: 日記２>, <Post: 日記１>]>
    ```
18. メソッドチェーンによる複雑なクエリ
    <br>〈command-line〉
    ```
    >>> Post.objects.filter(published_date__lte=timezone.now()).order_by('published_date')
    <QuerySet [<Post: 日記４>, <Post: 日記５>, <Post: Sample title>]>
    ```
***
19. ポストをHTMLファイルに出力する
    <br>①　blog/views.pyのコードに、models.py から Post モデルをインポートするため下記を入力
    <br>〈blog/views.py〉
    ```
    from django.shortcuts import render
    from .models import Post
    ```
    <br>②　Postモデルからブログの記事を取り出す
    <br>→　クエリセットを使って、公開したブログ記事を published_dateで並べ替える
    <br>→　def post_list(request)で始まる関数の中にこのコードを加える
    <br>〈blog/views.py〉
    ```
    Post.objects.filter(published_date__lte=timezone.now()).order_by('published_date')
    ```
    <br>③　from django.utils import timezoneを追記する
    <br>④　クエリセットを参照している変数postsをテンプレートに渡す
    <br>→　一番最後の行の後ろに {'posts': posts})を追加
    <br>⑤　最終的に下記のように記載されていればOk
    <br>〈blog/views.py〉
    ```
    from django.shortcuts import render
    from django.utils import timezone
    from .models import Post

    def post_list(request):
        posts = Post.objects.filter(published_date__lte=timezone.now()).order_by('published_date')
        return render(request, 'blog/post_list.html', {'posts': posts})
    ```
****

20. Djangoテンプレートタグを使ってPythonも使えるようにする
    <br>①　変数の名前を二重中括弧で括る
    <br>→　blog/templates/blog/post_list.htmlの2つめの div から3つめの /div までをまるごと {{ posts }} に置き換える
    <br>
    <br>〈blog/templates/blog/post_list.html〉
    ```
    {{ posts }}
    ```
    <br>②　ループを使ってリスト内のすべてのデータを表示させるようにする
    <br>〈blog/templates/blog/post_list.html〉
    ```
    {% for post in posts %}
    {{ post }}
    {% endfor %} 
    ```
    <br>③　HTMLとテンプレートタグを混ぜる
    <br>〈blog/templates/blog/post_list.html〉
    ```
    <div>
    <h1><a href="/">Django Girls Blog</a></h1>
    </div>

    {% for post in posts %}
        <div>
            <p>published: {{ post.published_date }}</p>
            <h2><a href="">{{ post.title }}</a></h2>
            <p>{{ post.text|linebreaksbr }}</p>
        </div>
    {% endfor %}
    ```
21. pythonAnywhereでデプロイする
    <br>①　GithubにあなたのコードをPushする
    <br>〈command-line〉
    ```
    $ git status
    [...]
    $ git add --all .
    $ git status
    [...]
    $ git commit -m "Modified templates to display posts from database."
    [...]
    $ git push
    ```
    <br>②　PythonAnywhereのBashコンソールで下記を実行
    <br>〈PythonAnywhere command-line〉
    ```
    $ cd nichols.pythonanywhere.com
    $ git pull
    [...]
    ```
    <br>③　リロードして投稿したものが表示されるか確認
    <br>→　Django 管理画面から新しい投稿を追加する際は、published_date 公開日の設定を忘れずに

## 難しかったこと

1. メソッドチェーンによる複雑なクエリがよく理解できない
    <br>↓これは何が起きている？
    ```
    >>> Post.objects.filter(published_date__lte=timezone.now()).order_by('published_date')
    <QuerySet [<Post: Post number 2>, <Post: My 3rd post!>, <Post: 4th title of post>, <Post: Sample title>]>
    ```
2. テンプレート内の動的データのクエリセットの部分がよくわからない
   



## 解決できなかったこと
