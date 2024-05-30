# Classificação de sentimento em reviews de filmes

<p align="center">
  <img width="400" height="250" src="https://github.com/kamillafsilva/nlp_imdb_review/blob/main/cloud.png">
</p>

## Overview
Esse projeto foi desenvolvido durante o curso [Spark: Processamento de Linguagem Natural](https://cursos.alura.com.br/course/spark-processamento-linguagem-natural), o objetivo era construir um modelo para a classificação de reviews positivas e negativas deixadas no site IMDB. A base de dados consiste em comentários escritos pelos usuários do site sobre os filmes assistidos. Várias técnicas de Processamento de Linguagem Natural (NLP) foram aplicadas para trabalhar com esses textos:

* Remoção de caracteres especias, espaços e *stop words* (preposições, pronomes, verbos, etc..)
* Tokenização para transformar os comentários em lista de palavras (*tokens*)
* Conversão das palavras em números utilizando um algoritmo de *hashing* (*Hashing TF*)
* Utilização do método *TF-IDF* para obter a importância de cada *token*.

Após essas etapas os dados estavam prontos para construção do modelo de classificação. Para a escolha do melhor modelo implementei uma função que avalia a métrica Área sob a curva ROC utilizando a técnica de *cross-validation*. Segundo esse critério, o melhor modelo foi o de Regressão Logística:

<div align="center">

| **modelo** | **auc_roc** | 
|:----------:|:-------:|
| logReg     |    0.87 |  
| tree       |    0.62 |
| xgb        |    0.85 |  

</div>

## Implementação
O código completo do projeto está disponível neste notebook do Colab: [nlp_imdb_reviews](https://colab.research.google.com/drive/1QRni6J7vrpxSuTJFvEhiIrEcSR6_StB2?usp=sharing).
