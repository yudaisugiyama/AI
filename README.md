## 開発環境

- Anaconda 22.9.0

## ツール

name: MFV-jetson

channels:
  - conda-forge
  - defaults

dependencies:
  - bzip2=1.0.8=he774522_0
  - ca-certificates=2022.10.11=haa95532_0
  - certifi=2022.9.24=py310haa95532_0
  - libffi=3.4.2=hd77b12b_4
  - openssl=1.1.1s=h2bbff1b_0
  - pip=22.2.2=py310haa95532_0
  - python=3.10.6=hbb2ffb3_1
  - setuptools=65.5.0=py310haa95532_0
  - sqlite=3.39.3=h2bbff1b_0
  - tk=8.6.12=h2bbff1b_0
  - tzdata=2022f=h04d1e81_0
  - vc=14.2=h21ff451_1
  - vs2015_runtime=14.27.29016=h5e58377_2
  - wheel=0.37.1=pyhd3eb1b0_0
  - wincertstore=0.2=py310haa95532_2
  - xz=5.2.6=h8cc25b3_0
  - zlib=1.2.13=h8cc25b3_0
  - pip:
    <!-- - ailia==1.2.13.0 -->
    <!-- - face-detection==1.0.5 -->
    - blinker==1.5
    - charset-normalizer==2.1.1
    - contexts==0.12
    - contourpy==1.0.6
    - cycler==0.11.0
    - fonttools==4.38.0
    - idna==3.4
    - imageio==2.22.4
    - kiwisolver==1.4.4
    - matplotlib==3.6.2
    - networkx==2.8.8
    - numpy==1.23.4
    - opencv-python==4.6.0.66
    - packaging==21.3
    - paho-mqtt==1.6.1
    - pandas==1.5.1
    - pillow==9.3.0
    - py-context==0.3.1
    - pyparsing==3.0.9
    - python-dateutil==2.8.2
    - pytz==2022.6
    - pywavelets==1.4.1
    - requests==2.28.1
    - scikit-image==0.19.3
    - scipy==1.9.3
    - six==1.16.0
    - sixdrepnet==0.1.2
    - tifffile==2022.10.10
    - torch==1.13.0
    - torchvision==0.14.0
    - typing-extensions==4.4.0
    - urllib3==1.26.12

prefix: D:\chen\anaconda3\envs\MFV-jetson

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

```cmd
conda activate test
```

cdコマンドでenv.ymlが存在するディレクトリに移動してください.

本稿は開発用パソコンのパスを例にします.


移動したら下記のコマンドで仮想環境の複製を行います.

```cmd
conda env create -n test -f env.yml
```

ここで, ほとんどのライブラリのインストールは完了しましたが, 追加で下記のライブラリもインストールします.

まず, 仮想環境を有効化します.

```cmd
cd C:\Users\trl\Documents\INT01750-yudai-sugiyama
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





