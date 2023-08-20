# 大規模言語モデル入門

<a href="https://www.amazon.co.jp/o/ASIN/4297136333/"><img src="misc/cover-small.png" width="200"></a>

「[大規模言語モデル入門](https://www.amazon.co.jp/o/ASIN/4297136333/)」（技術評論社, 2023）のリポジトリです。

## Mac上での再現メモ（mtake-mac ブランチ固有）
- [chapter8/8-3-simcse-training.ipynb](/chapter8/8-3-simcse-training.ipynb) 3時間, 2時間かかるところがある
- [chapter8/8-4-simcse-faiss.ipynb](/chapter8/8-4-simcse-faiss.ipynb) 10時間かかっても終わらず中断
- [chapter9/9-3-quiz-chatgpt.ipynb](/chapter9/9-3-quiz-chatgpt.ipynb), [chapter9/9-5-quiz-chatgpt-plus-bpr.ipynb](/chapter9/9-5-quiz-chatgpt-plus-bpr.ipynb) ChatGPTに依存するため未試行
- [chapter9/9-4-3-bpr-training.ipynb](/chapter9/9-4-3-bpr-training.ipynb) 次のエラーで失敗 `NotImplementedError: The operator 'aten::masked_scatter_' is not currently implemented for the MPS device.`
- [chapter9/9-4-4-bpr-embedding.ipynb](/chapter9/9-4-4-bpr-embedding.ipynb) 10時間かかっても終わらず中断

## コード

コードはすべて Google Colaboratory で動作確認を行なっています。
コードの中で利用したデータセットや作成したモデルは[Hugging Face Hub](https://huggingface.co/llm-book)にて公開しています。

**⚠️ 2023/7/28 現在、MARC-ja のデータセットの配布元のリンクが切れており、書籍上の 5.2, 5.3, 5.5.4 に掲載されているコードにおいて、データセット読み込みの箇所でエラーが出る状態です。
現在問い合わせのメールを送り、復旧待機中です。**

**これに応じて、日本語感情分析データセットである [WRIME](https://github.com/ids-cv/wrime) を使用したノートブックを追加致しましたので、コードを動作させたい方はご活用ください。**


| 章                                             | 節／項                                                                                                                     | Colab                                                                                                                                                                                                 | Link                                                                                                      |
| ---------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| 第 1 章 はじめに                               | 1.1 transformers を使って自然言語処理を解いてみよう<br />1.2 transformers の基本的な使い方                                 | [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ghmagazine/llm-book/blob/main/chapter1/1-introduction.ipynb)                    | [Link](https://github.com/ghmagazine/llm-book/blob/main/chapter1/1-introduction.ipynb)                    |
| 第 2 章 Transformer                            | 2.2 エンコーダ                                                                                                             | [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ghmagazine/llm-book/blob/main/chapter2/2-2-transformer-position-encoding.ipynb) | [Link](https://github.com/ghmagazine/llm-book/blob/main/chapter2/2-2-transformer-position-encoding.ipynb) |
| 第 3 章 大規模言語モデルの基礎                 | 3.2 GPT（デコーダ）<br />3.3 BERT・RoBERTa（エンコーダ）<br />3.4 T5（エンコーダ・デコーダ）                               | [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ghmagazine/llm-book/blob/main/chapter3/3-zero-shot-inference.ipynb)             | [Link](https://github.com/ghmagazine/llm-book/blob/main/chapter3/3-zero-shot-inference.ipynb)             |
|                                                | 3.6 トークナイゼーション                                                                                                   | [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ghmagazine/llm-book/blob/main/chapter3/3-6-tokenization.ipynb)                  | [Link](https://github.com/ghmagazine/llm-book/blob/main/chapter3/3-6-tokenization.ipynb)                  |
| 第 5 章 大規模言語モデルのファインチューニング | 5.2 感情分析モデルの実装                                                                                                   | [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ghmagazine/llm-book/blob/main/chapter5/5-2-sentiment-analysis-finetuning.ipynb) <br /> [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ghmagazine/llm-book/blob/main/chapter5/5-2-sentiment-analysis-finetuning-wrime.ipynb) | [Link (MARC-ja)](https://github.com/ghmagazine/llm-book/blob/main/chapter5/5-2-sentiment-analysis-finetuning.ipynb) <br /> [Link (WRIME)](https://github.com/ghmagazine/llm-book/blob/main/chapter5/5-2-sentiment-analysis-finetuning-wrime.ipynb) |
|                                                | 5.3 感情分析モデルのエラー分析                                                                                             | [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ghmagazine/llm-book/blob/main/chapter5/5-3-sentiment-analysis-analysis.ipynb) <br /> [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ghmagazine/llm-book/blob/main/chapter5/5-3-sentiment-analysis-analysis-wrime.ipynb)     | [Link (MARC-ja)](https://github.com/ghmagazine/llm-book/blob/main/chapter5/5-3-sentiment-analysis-analysis.ipynb) <br /> [Link (WRIME)](https://github.com/ghmagazine/llm-book/blob/main/chapter5/5-3-sentiment-analysis-analysis-wrime.ipynb)     |
|                                                | 5.4.1 自然言語推論の実装（訓練）                                                                                           | [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ghmagazine/llm-book/blob/main/chapter5/5-4-nli-finetuning.ipynb)                 | [Link](https://github.com/ghmagazine/llm-book/blob/main/chapter5/5-4-nli-finetuning.ipynb)                 |
|                                                | 5.4.1 自然言語推論の実装（分析）                                                                                           | [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ghmagazine/llm-book/blob/main/chapter5/5-4-nli-analysis.ipynb)                 | [Link](https://github.com/ghmagazine/llm-book/blob/main/chapter5/5-4-nli-analysis.ipynb)                 |
|                                                | 5.4.2 意味的類似度計算の実装（訓練）                                                                                       | [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ghmagazine/llm-book/blob/main/chapter5/5-4-sts-finetuning.ipynb)                 | [Link](https://github.com/ghmagazine/llm-book/blob/main/chapter5/5-4-sts-finetuning.ipynb)                 |
|                                                | 5.4.2 意味的類似度計算の実装（分析）                                                                                       | [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ghmagazine/llm-book/blob/main/chapter5/5-4-sts-analysis.ipynb)                 | [Link](https://github.com/ghmagazine/llm-book/blob/main/chapter5/5-4-sts-analysis.ipynb)                 |
|                                                | 5.4.3 多肢選択式質問応答モデルの実装（訓練）                                                                               | [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ghmagazine/llm-book/blob/main/chapter5/5-4-multiple-choice-qa-finetuning.ipynb)       | [Link](https://github.com/ghmagazine/llm-book/blob/main/chapter5/5-4-multiple-choice-qa-finetuning.ipynb)       |
|                                                | 5.4.3 多肢選択式質問応答モデルの実装（分析）                                                                               | [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ghmagazine/llm-book/blob/main/chapter5/5-4-multiple-choice-qa-analysis.ipynb)       | [Link](https://github.com/ghmagazine/llm-book/blob/main/chapter5/5-4-multiple-choice-qa-analysis.ipynb)       |
|                                                | 5.5.4 LoRA チューニング（感情分析）                                                                                        | [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ghmagazine/llm-book/blob/main/chapter5/5-5-sentiment-analysis-finetuning-LoRA.ipynb) <br /> [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ghmagazine/llm-book/blob/main/chapter5/5-5-sentiment-analysis-finetuning-LoRA-wrime.ipynb) | [Link (MARC-ja)](https://github.com/ghmagazine/llm-book/blob/main/chapter5/5-5-sentiment-analysis-finetuning-LoRA.ipynb) <br /> [Link (WRIME)](https://github.com/ghmagazine/llm-book/blob/main/chapter5/5-5-sentiment-analysis-finetuning-LoRA-wrime.ipynb) |
| 第 6 章 固有表現認識                           | 6.2 データセット・前処理・評価指標<br />6.3 固有表現認識モデルの実装<br />6.4 アノテーションツールを用いたデータセット構築 | [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ghmagazine/llm-book/blob/main/chapter6/6-named-entity-recognition.ipynb)        | [Link](https://github.com/ghmagazine/llm-book/blob/main/chapter6/6-named-entity-recognition.ipynb)        |
| 第 7 章 要約生成                               | 7.2 データセット<br />7.3 評価指標<br />7.4 見出し生成モデルの実装<br />7.5 多様な生成方法による見出し生成                 | [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ghmagazine/llm-book/blob/main/chapter7/7-summarization-generation.ipynb)        | [Link](https://github.com/ghmagazine/llm-book/blob/main/chapter7/7-summarization-generation.ipynb)        |
| 第 8 章 文埋め込み                             | 8.3 文埋め込みモデルの実装                                                                                                 | [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ghmagazine/llm-book/blob/main/chapter8/8-3-simcse-training.ipynb)               | [Link](https://github.com/ghmagazine/llm-book/blob/main/chapter8/8-3-simcse-training.ipynb)               |
|                                                | 8.4 最近傍探索ライブラリ `Faiss` を使った検索                                                                              | [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ghmagazine/llm-book/blob/main/chapter8/8-4-simcse-faiss.ipynb)                  | [Link](https://github.com/ghmagazine/llm-book/blob/main/chapter8/8-4-simcse-faiss.ipynb)                  |
| 第 9 章 質問応答                               | 9.3 ChatGPT にクイズを答えさせる                                                                                           | [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ghmagazine/llm-book/blob/main/chapter9/9-3-quiz-chatgpt.ipynb)                  | [Link](https://github.com/ghmagazine/llm-book/blob/main/chapter9/9-3-quiz-chatgpt.ipynb)                  |
|                                                | 9.4.3 BPR の実装                                                                                                           | [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ghmagazine/llm-book/blob/main/chapter9/9-4-3-bpr-training.ipynb)                | [Link](https://github.com/ghmagazine/llm-book/blob/main/chapter9/9-4-3-bpr-training.ipynb)                |
|                                                | 9.4.4 BPR によるパッセージの埋め込みの計算                                                                                 | [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ghmagazine/llm-book/blob/main/chapter9/9-4-4-bpr-embedding.ipynb)               | [Link](https://github.com/ghmagazine/llm-book/blob/main/chapter9/9-4-4-bpr-embedding.ipynb)               |
|                                                | 9.5 文書検索モデルと ChatGPT を組み合わせる                                                                                | [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ghmagazine/llm-book/blob/main/chapter9/9-5-quiz-chatgpt-plus-bpr.ipynb)         | [Link](https://github.com/ghmagazine/llm-book/blob/main/chapter9/9-5-quiz-chatgpt-plus-bpr.ipynb)         |

## 正誤表

本書の正誤表は以下のページで公開しています。

[https://github.com/ghmagazine/llm-book/wiki/errata](https://github.com/ghmagazine/llm-book/wiki/errata)

## リンク

- [Hugging Face Hub](https://huggingface.co/llm-book)
- [技術評論社のページ](https://gihyo.jp/book/2023/978-4-297-13633-8)
- [Amazon.co.jp](https://www.amazon.co.jp/o/ASIN/4297136333/)
