# 開発環境について
```
python3 -m venv nlp
```
で作成したpython仮想環境を用意した。
`source ./nlp/bin/activate`を行い、pythonコマンドのパスを通す必要がある。
終了時は`deactivate`で良い。
ただし、python versionは、
https://devcenter.heroku.com/articles/python-support#supported-runtimes
以上を確認し、対応するものを使うこと。
```
apt install python3.10-venv # pip install

python は、`which python`の上、Ubuntu の場合`ls /usr/bin/ | grep python`で確認できる。

django,herokuを使用している。

本環境へのインストール済みパッケージの確認は
`pip freeze`(requirements.txt のフォーマット)
または、`pip list`できる。
それらのインストールは
`pip install -r requirements.txt`で行う。

# 開発方法
`python manage.py runserver` にて内部IPのport8000で起動する。


# フォルダ構成

- nlp-translate-webapp/
    - ルートディレクトリは、プロジェクトのコンテナです。その名前は Django にとって重要ではありません。任意の名前に変更できます。
- /manage.py
    - Django プロジェクトに対する様々な操作を行うためのコマンドラインユーティリティです｡詳しくは django-admin と manage.py 内の manage.py を参照してください｡
- /translate/
    - ディレクトリは、このプロジェクトの実際の Python パッケージです。この名前が Python パッケージの名前であり、 import の際に 使用する名前です (例えば import translate.urls) 。
- translate/__init__.py
    - このディレクトリが Python パッケージであることを Python に知らせるための空のファイルです。Python の初心者は、 Python の公式 ドキュメントの more about packages を読んで下さい。
- translate/settings.py
    - Django プロジェクトの設定ファイルです。 設定の仕組みは Djangoの設定 を参照してください。
- translate/urls.py
    - Django プロジェクトの URL 宣言、いうなれば Django サイトにおける「目次」に相当します。詳しくは URL ディスパッチャ を参照 してください。
- translate/asgi.py
    - プロジェクトを提供する ASGI 互換 Web サーバーのエントリポイント。詳細については How to deploy with ASGI を参照してください。
- translate/wsgi.py
    - プロジェクトをサーブするためのWSGI互換Webサーバーとのエントリーポイントです。詳細は WSGI とともにデプロイするには を参照してください。

- client/
    - client アプリケーション