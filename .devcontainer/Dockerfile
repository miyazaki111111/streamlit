# ベースイメージ
FROM python:3.11-slim

# 作業ディレクトリ作成
WORKDIR /app

# 必要なパッケージをインストール
RUN apt-get update && apt-get install -y \
    build-essential \
    curl \
    git \
    && rm -rf /var/lib/apt/lists/*

# pip のアップグレード
RUN pip install --upgrade pip

# Streamlit と一般的な依存関係を先にインストール（キャッシュ活用）
COPY requirements.txt .
RUN pip install -r requirements.txt

# ポートを開ける（streamlit用）
EXPOSE 8501

# デフォルトコマンドはなし（VSCodeから起動）
