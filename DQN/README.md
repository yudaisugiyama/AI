# レシピ
## レシピについて

このレシピを学ぶことで以下の手法を学ぶことができます.

- Anacondaを利用した仮想環境での開発
- Pytorchを利用した深層強化学習モデルの構築

## 開発環境

- Anaconda 22.9.0

## ツール


## 下ごしらえ

下記のサイトからAnacondaをインストールします.

https://www.anaconda.com/products/distribution

-Vオプションでバージョンを確認します.

```cmd:cmd
conda -V
```

下記のように出力されたらインストール成功です.

```cmd:output
conda 22.9.0
```

次に, env.ymlから, 仮想環境の複製を行います.


cdコマンドでenv.ymlが存在するディレクトリに移動してください.

本稿は開発用パソコンのパスを例にします.

```cmd
cd C:\Users\trl\Documents\INT01750-yudai-sugiyama
```

移動したら下記のコマンドで仮想環境の複製を行います.

```cmd
conda env create -n test -f env.yml
```

ここで, ほとんどのライブラリのインストールは完了しましたが, 追加で下記のライブラリもインストールします.

まず, 仮想環境を有効化します.

```cmd
conda activate test
```

有効化したら下記の手順で追加のライブラリ(ailia)をインストールします.

```cmd
cd C:\Users\trl\Documents\INT01750-yudai-sugiyama\ailia\ailia_1_213_1_trial\python
python bootstrap.py
pip3 install ./
```

うまくいかない場合は, 下記のサイトから詳細をご覧ください.

https://medium.com/axinc/ailia-sdk-%E3%83%81%E3%83%A5%E3%83%BC%E3%83%88%E3%83%AA%E3%82%A2%E3%83%AB-python-28379dbc9649

最後に環境を構築できたか確認します.

face-mask-detctionを動かしてみましょう.
下記のコマンドでディレクトリを移動してください.


```cmd
cd C:\Users\trl\Documents\INT01750-yudai-sugiyama\jetson\numofpeople-and-position\face-mask-detection
```

face-mask-detection-test.pyを動かせたら環境構築完了です.

お疲れさまでした.

```cmd
python face-mask-detection-test.py -v 0
```

```cmd
python　midas.py -v 0
```

```cmd
python driver-action-recognition-adas.py -v 0
```

```cmd
pip install git+https://github.com/elliottzheng/face-detection.git@master
```

```cmd
python demo-cpu.py --snapshot path.pth --cam 0
```





