# ベースイメージとしてPythonを使用
FROM python:3.10-slim

# 作業ディレクトリを作成
WORKDIR /usr/src/app

# Pythonがpycファイルとディスクキャッシュを生成するのを防ぐ
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# 必要なライブラリをインストール
RUN pip install --upgrade pip

# Pythonの依存関係をコピーしてインストール
COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

# ソースコードをコピー
COPY . .

# マイグレーションと静的ファイルの収集
# RUN python -m django startproject my_project .
# RUN python manage.py makemigrations
# RUN python manage.py migrate
# RUN python manage.py collectstatic --noinput

# Gunicornでアプリケーションを起動
CMD ["gunicorn", "--bind", "0.0.0.0:8001", "my_project.wsgi:application"]

# ポート8000を公開
EXPOSE 8001
