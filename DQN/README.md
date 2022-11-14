# メニュー*

## 概要*

このレシピでは, 等周問題に対する深層強化学習モデルの実装を試すことができます.

ここでは, 実装コードのダウンロード $\rightarrow$ 仮想環境の複製 $\rightarrow$ 実行 $\rightarrow$ アルゴリズムの解説という流れで進めます.


深層強化学習(Deep Q-learning Network; DQN)では, Convolutional Neural Network; CNNを用いた画像の分類器と異なり, 学習データを必要としません.
DQNは設計者が設定した環境とインタラクティブに学習することで, 試行錯誤のみで正解を導きます.


今回のレシピでは, DQNを実際に実装し, アルゴリズムの主要なポイントを紹介します^^

## 学べること*

このレシピを学ぶことで以下の手法を学ぶことができます.

- Anacondaを利用した仮想環境での開発
- Pytorchを利用した深層強化学習モデルの構築

## 始める前のスキルセット*

- Pythonの基礎知識

## 実務活用例*

- 自動運転技術
- 将棋や囲碁などのゲームAIの作成

# キッチン*

## 開発環境*

開発環境を記述してください。

## ツール*

- Anaconda 22.9.0のデフォルトライブラリ

## データセット

下記のサイトからAnacondaをインストールします.

https://www.anaconda.com/products/distribution

-Vオプションでバージョンを確認します.

```cmd:cmd
conda -V
```

下記のように出力されたらインストール成功です^^.

```cmd:output
conda 22.9.0
```

Anacondaのインストールの詳細は下記のサイトを参考にしてください.

次に, githubから実装コードを取得します.
gitを既にインストールされている場合はgit cloneで取得できます.

```cmd:cmd
git clone https://github.com/yudaisugiyama/AI/tree/main/DQN/dqn-isoperimetric-problem.git
```

gitが入っていない場合は, 

https://github.com/yudaisugiyama/AI から<>code $\rightarrow$ Download ZIPでダウンロードして解凍してください.

ダウンロードが完了したらenv.ymlから, 仮想環境の複製を行います.

cdコマンドでenv.ymlが存在するディレクトリに移動してください.

下記のコードはAIディレクトリから見た相対パスを例にしています.

```cmd:cmd
cd DQN/dqn-isoperimetric-problem
```

移動したら下記のコマンドで仮想環境の複製を行います.

ここで, testは仮想環境の名前で任意の文字列です.

```cmd:cmd
conda env create -n test -f env.yml
```

createに成功したらツールの用意が完了しました^^.


# 調理*

## 仮想環境を有効化しよう！

まず, 先ほど複製した仮想環境を有効化します.

ここでも, testは仮想環境の名前であり, 複製した環境名と同じものを使ってください.

```cmd:cmd
conda activate test
```

## 構成

## モデルをトレーニングさせよう！

冒頭でも触れたように, DQNは学習データを必要としません.

では, どうやって学習するのか?

+++

上記のアルゴリズムを踏まえた上で, とりあえず動かしてみましょう^^

まずはトレーニングを行うtrain.pyを実行します.

*MacOSの場合はpython3コマンドを使用してください.

```cmd:cmd
python train.py
```

下記のような出力まで表示されたらトレーニング成功です!

[xxxx-xx-xx xx:xx:xx,xxx][utils][INFO] - weight pathの下に, 学習したデータが記録されたファイルが生成されます.

次に行うテスト時に必要になるのでコピーしておきましょう!


```cmd:output
[2022-11-14 17:36:58,509][utils][INFO] - total reward history
    total reward      loss
0     208.653274  3.507581
1     229.643826  3.035437
2     239.498059  2.719864
3     244.923276  2.548927
4     236.284524  3.044429
..           ...       ...
95    687.290309       NaN
96    685.052552       NaN
97           NaN       NaN
98    685.213402       NaN
99    684.730853       NaN

[100 rows x 2 columns]
[2022-11-14 17:36:58,524][utils][INFO] - weight path
C:\Users\fogefoge\Documents\AI\DQN\dqn-isoperimetric-problem\outputs\2022-11-14\17-36-08/weight.pth
[2022-11-14 17:36:58,524][utils][INFO] - time
50.377s
```

## 学習済データを使ってテストしてみよう！

テストを行う場合はtest.pyを実行します.

```cmd:cmd
python test.py
```

下記のようなインタープリターが表示されたら

コピーしておいた重みファイルのパスを貼り付けます.

Enterを押して, テストを開始しましょう!

```cmd:cmd
Input path of weight.pth-->
```

