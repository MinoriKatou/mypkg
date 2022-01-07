# mypkg

"mypkg"は「ubuntu」の環境で，『サブリッシャ』と『サブスクライバ』を作り２つのファイルでデータのやりとりをします．

# DEMO

２つのファイルでデータのやり取りをした様子です．<br>
https://youtu.be/jjugRN7yZbM

# Features

簡単にデータのやり取りを体験できる．

# Requirement

* ubuntu 20.04.3
* Rspberry Pi 4 Model B

# tools

Raspberry Pi 4 Model B x 1<br>

# Usage

ディレクトリ内で以下のコマンドを実行．

```bash
git clone https://github.com/hoge/~
cd myled
make
sudo insmod myled.ko
sudo chmod 666 /dev/myled0
```
以下コマンドで点灯

```bash
echo 1 > /dev/myled0
```

以下コマンドで消灯

```bash
echo 0 > /dev/myled0
```

実行後のディレクトリの後処理は以下コマンド

```bash
make clean
```

# Note

* GPIO25ピンを利用した回路です．
* LEDは向きがあるので気を付けて．

# Author

* MinoriKatou
* Chiba Institute of Technology
* s20C1033CR@s.chibakoudai.jp

# License

"myled" is under [BSD 3-Clause "New" or "Revised" License](https://www.gnu.org/licenses/).

Thank you!
