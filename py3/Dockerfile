#ベースイメージ作成
ARG PYTHON_VER
FROM python:${PYTHON_VER}
ENV PYTHONUNBUFFERED 1

#ディレクトリ作成、ワーキングディレクトリ指定
ARG WORKDIR
RUN mkdir -p ${WORKDIR}
WORKDIR ${WORKDIR}

#パッケージインストール
RUN apt-get update && \
    apt-get -y install gcc git

#requirements.txtからパッケージインストール
COPY requirements.txt "${WORKDIR}/"
#ydata-profiling1のエラー対応でphik0.11.2をインストール
RUN pip install --no-cache-dir phik==0.11.2
RUN pip install --upgrade pip
RUN pip install -r requirements.txt