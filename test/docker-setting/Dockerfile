FROM python:3
ENV PYTHONUNBUFFERED=1

# 作業ディレクトリ
WORKDIR /app

# 必要なパッケージをインストール
RUN apt-get update && apt-get install -y \
    build-essential \
    uwsgi \
    && apt-get clean

# Pythonの依存関係をインストール
COPY requirements.txt /app/
# COPY uwsgi.ini /usr/bin/
RUN pip install -r requirements.txt

# uwsgiを起動
CMD ["uwsgi", "--ini", "uwsgi.ini"]