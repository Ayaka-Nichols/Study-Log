# 学習記録
#### 2022-10-15 ~ 10-21

## 学習対象
 
<br>▼CSSでカワイくしよう!
    <br>- CSSとは？
    <br>- Bootstrapを使いましょう！
    <br>- Bootstrapのインストール
    <br>- Djangoの静的ファイル
    <br>- 静的ファイルはプロジェクトのどこに置けばいいの？
    <br>- 最初のCSSファイル！
<br>▼テンプレートを拡張しよう
    <br>- 基本テンプレートを作成する
<br>▼アプリケーションを拡張しよう
    <br>- 投稿の詳細へのテンプレートリンクを作成する
    <br>- 投稿の詳細へのURLを作成する
    <br>- 投稿の詳細ビューを追加する
    <br>- 投稿の詳細へのテンプレートリンクを作成する
    <br>- デプロイの時間です！
    <br>- サーバー上の静的ファイルの更新
<br>▼Djangoフォーム
    <br>- フォームにおけるページへのリンク
    <br>- URL
    <br>- post_new ビュー
    <br>- テンプレート
    <br>- フォームを保存する
    <br>- フォームのバリデーション(検証)
    <br>- フォームの編集
    <br>- セキュリティ
    <br>- もう一つ: デプロイの時間です!

    






## 得たこと(自分の言葉で説明できる状態)

1. CSSで装飾をつける
    <br>①　Bootstrapをインストールする
    <br>→　下記コードを追加する
    <br>〈blog/templates/blog/post_list.html〉
    ```
    <link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css">
    <link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap-theme.min.css">
    ```
    <br>②　blog アプリのための静的ファイルを追加する
    <br>→　blogアプリの中に static というフォルダを作る
    ```djangogirls
    ├── blog
    │   ├── migrations
    │   ├── static
    │   └── templates
    └── mysite
    ```
    <br>③　CSSファイルを作成する
    <br>→　static ディレクトリの中に css というディレクトリを作成、css ディレクトリの中に blog.css という新規ファイルを作成
    ```
    djangogirls
    └─── blog
        └─── static
            └─── css
                └─── blog.css
    ```
    <br>④　h1とh2の文字を装飾する
    <br>〈blog/static/css/blog.css〉
    ```
    h1 a, h2 a {
    color: #C25100;
    }
    ```
    <br>⑤　CSSを追加したことをHTMLテンプレートに教える
    <br>→　先頭に書きを追加
    <br>〈blog/templates/blog/post_list.html〉
    ```
    {% load static %}
    ```

    <br>⑥　head　と /head の中にあるBootstrap CSSファイルのリンクの下に、下記を追加
    <br>〈blog/templates/blog/post_list.html〉
    ```
    <link rel="stylesheet" href="{% static 'css/blog.css' %}">
    ```
  ***
2. テンプレートを拡張する
    <br>①　基本テンプレートを作成する
    <br> blog/templates/blog/以下にbase.htmlファイルを作成する
    ```
    blog
    └───templates
        └───blog
                base.html
                post_list.html
    ```
    <br>②　post_list.htmlからbase.htmlファイルにすべてコピーする
    <br>③　base.html内の<body>全体(<body>と</body>の間のすべて)を下記に置き換える
    <br>〈blog/templates/blog/base.html〉
    ```
    <body>
        <div class="page-header">
            <h1><a href="/">Django Girls Blog</a></h1>
        </div>
        <div class="content container">
            <div class="row">
                <div class="col-md-8">
                {% block content %}
                {% endblock %}
                </div>
            </div>
        </div>
    </body>
    ```
    <br>④　post_list.htmlの{% for post in posts %} の上と {% endfor %} の下すべてを削除する
    <br>〈blog/templates/blog/post_list.html〉
    ```
    {% for post in posts %}
        <div class="post">
            <div class="date">
                {{ post.published_date }}
            </div>
            <h2><a href="">{{ post.title }}</a></h2>
            <p>{{ post.text|linebreaksbr }}</p>
        </div>
    {% endfor %}
    ```
    <br>⑤　上記コードを {% block content %} と {% endblock %} の間に入れてあげる
    <br>〈blog/templates/blog/post_list.html〉
    ```
    {% block content %}
        {% for post in posts %}
            <div class="post">
                <div class="date">
                    {{ post.published_date }}
                </div>
                <h2><a href="">{{ post.title }}</a></h2>
                <p>{{ post.text|linebreaksbr }}</p>
            </div>
        {% endfor %}
    {% endblock %}
    ```
    <br>⑥　これら二つのテンプレートをくっつけてあげるために、ファイルの先頭にextendsタグを追加する
    <br> 〈blog/templates/blog/post_list.html〉
    ```
    {% extends 'blog/base.html' %}

    {% block content %}
        {% for post in posts %}
            <div class="post">
                <div class="date">
                    {{ post.published_date }}
                </div>
                <h2><a href="">{{ post.title }}</a></h2>
                <p>{{ post.text|linebreaksbr }}</p>
            </div>
        {% endfor %}
    {% endblock %}
    ```
    ***
3. アプリケーションを拡張する
    <br>①　投稿の詳細のページのリンクを作る
    <br>→　post_list.htmlファイルのh2の行を下記に変更する
    ```
    <h2><a href="{% url 'post_detail' pk=post.pk %}">{{ post.title }}</a></h2>
    ```
    <br>②　URLを作成する
    <br>→　blog/urls.pyに下記を追加する
    ```
    path('post/<int:pk>/', views.post_detail, name='post_detail'),
    ```
    <br>③　ビューを追加する
    <br>→　blog/views.pyに下記を追加する
    ```
    from django.shortcuts import render, get_object_or_404
    ```
    <br>　ファイルの最後にビューを追加する　
    <br>→　blog/views.pyの一番下に、下記を追加する
    ```
    def post_detail(request, pk):
        post = get_object_or_404(Post, pk=pk)
        return render(request, 'blog/post_detail.html', {'post': post})
    ```
    <br>④　テンプレートリンクを作成する
    <br>→　blog/templates/blogにpost_detail.htmlというファイルを作成し、下記コードを入力する
    <br>〈blog/templates/blog/post_detail.html〉
    ```
    {% extends 'blog/base.html' %}

    {% block content %}
        <div class="post">
            {% if post.published_date %}
                <div class="date">
                    {{ post.published_date }}
                </div>
            {% endif %}
            <h2>{{ post.title }}</h2>
            <p>{{ post.text|linebreaksbr }}</p>
        </div>
    {% endblock %}
    ```
    <br>⑤　デプロイする
    <br>
    <br>
    <br>⑥、CSSファイルを変更する場合は、毎回サーバーで更新する必要がある
    <br>→PythonAnywhereの仮想環境を有効にする、workonコマンド、python manage.py collectstaticコマンド
    ***
4. フォームを作成する
    <br>①　blogディレクトリの下にforms.pyというファイルを作成する
    ```
    blog
     └── forms.py
    ```
    <br>このファイルをエディタで開き、下記のコードを入力する
    <br>〈blog/forms.py〉
    ```
    from django import forms

    from .models import Post

    class PostForm(forms.ModelForm):

        class Meta:
            model = Post
            fields = ('title', 'text',)
    ```
    <br>②　blog/templates/blog/base.htmlのpage-header と名付けた div 中に下記を追加する
    ```
    <a href="{% url 'post_new' %}" class="top-menu"><span class="glyphicon glyphicon-plus"></span></a>
    ```
    <div>③　URLを作成する
    <div>→　blog/urls.pyに下記を追加する
    ```
    path('post/new/', views.post_new, name='post_new'),
    ```
    <br>④　post_new ビューを作成する
    <br>→　blog/views.pyのfromの行の後に下記を追加する
    ```
    from .forms import PostForm
    ```
    <br>ビューを追加
    ```
    def post_new(request):
        form = PostForm()
        return render(request, 'blog/post_edit.html', {'form': form})
    ```
    <br>⑤　テンプレートを作成する
    <br>→blog/templates/blogディレクトリにpost_edit.htmlファイルを作成し、下記を入力
    <br>〈blog/templates/blog/post_edit.html〉
    ```
     {% extends 'blog/base.html' %}

    {% block content %}
        <h2>New post</h2>
        <form method="POST" class="post-form">{% csrf_token %}
            {{ form.as_p }}
            <button type="submit" class="save btn btn-default">Save</button>
        </form>
    {% endblock %}

    ```

<br>⑥　フォームを保存する
<br>→　blog/views.pyのpost_new ビューを下記に変更する
<br>→　blog/views.py
```
    def post_new(request):
        if request.method == "POST":
            form = PostForm(request.POST)
            if form.is_valid():
                post = form.save(commit=False)
                post.author = request.user
                post.published_date = timezone.now()
                post.save()
                return redirect('post_detail', pk=post.pk)
        else:
            form = PostForm()
        return render(request, 'blog/post_edit.html', {'form': form})
```
<br>⑦　フォームの編集
<br>→　blog/templates/blog/post_detail.htmlに下記を追加
```
    <a class="btn btn-default" href="{% url 'post_edit' pk=post.pk %}"><span class="glyphicon glyphicon-pencil"></span></a>
```
<br>→　blog/urls.pyに下記を追加する。
```
    path('post/<int:pk>/edit/', views.post_edit, name='post_edit'),
```
<br>→blog/views.py の最後に下記を追加する
```
def post_edit(request, pk):
    post = get_object_or_404(Post, pk=pk)
    if request.method == "POST":
        form = PostForm(request.POST, instance=post)
        if form.is_valid():
            post = form.save(commit=False)
            post.author = request.user
            post.published_date = timezone.now()
            post.save()
            return redirect('post_detail', pk=post.pk)
    else:
        form = PostForm(instance=post)
    return render(request, 'blog/post_edit.html', {'form': form})
```
<br>⑧　他の人に新しいブログ投稿を作成させないようにする
<br>→　blog/templates/blog/base.htmlに{% if %}タグを追加する
<br>〈blog/templates/blog/base.html〉
```
{% if user.is_authenticated %}
    <a href="{% url 'post_new' %}" class="top-menu"><span class="glyphicon glyphicon-plus"></span></a>
{% endif %}
```
<br>→　blog/templates/blog/post_detail.htmlに{% if %}タグを追加する
<br>〈blog/templates/blog/post_detail.html〉
```
{% if user.is_authenticated %}
     <a class="btn btn-default" href="{% url 'post_edit' pk=post.pk %}"><span class="glyphicon glyphicon-pencil"></span></a>
{% endif %}
```
<br>⑨　デプロイする
    
    






## 難しかったこと

1. 
  
2.
   



## 解決できなかったこと
