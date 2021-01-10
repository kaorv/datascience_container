# jupyternotebookの公式imageを取得(datascienceに特化したimage)
FROM jupyter/datascience-notebook

# root権限を取得する
USER root

# MeCabインストール
RUN sudo apt-get update \
  && apt-get install -y mecab \
  && apt-get install -y mecab-ipadic \
  && apt-get install -y libmecab-dev \
  && apt-get install -y mecab-ipadic-utf8 \
  && apt-get install -y swig \
  && pip install mecab-python3==0.996.2

# 初期ライブラリinstall
RUN pip install \
	gensim==3.8.3 \
	spacy==2.3.2 \
	ginza==4.0.4 \
	word2vec==0.11.1 \
	sudachipy==0.4.9 \
	nltk==3.4.5
