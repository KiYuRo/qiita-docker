FROM python:3.12-slim

ARG USERNAME=app-user

# ユーザーを作成し、そのユーザーのホームディレクトリを作成
RUN useradd -ms /bin/bash $USERNAME

# 作業ディレクトリを設定
WORKDIR /home/$USERNAME/app

# ユーザーを変更
USER $USERNAME

# requirements.txt をコピー
COPY requirements.txt /home/$USERNAME/app/

# pip をアップグレードし、必要なパッケージをインストール
RUN pip install --upgrade pip && \
    pip install --no-cache-dir -r requirements.txt
