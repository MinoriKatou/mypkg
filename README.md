# mypkg

"mypkg"は「ubuntu」の環境で，『サブリッシャ』と『サブスクライバ』を作り２つのファイルでデータのやりとりをします．

# DEMO

２つのファイルでデータのやり取りをした様子です．<br>
https://youtu.be/jjugRN7yZbM

# Features

簡単にデータのやり取りを体験できる．

# Requirement

* ubuntu 20.04.3
* ROS
* Rspberry Pi 4 Model B

# tools

Raspberry Pi 4 Model B x 1<br>

# Usage

始めにディレクトリを作成する．

```bash
cd
mkdir -p catkin_ws/src
cd ~/catkin_ws/src
catkin_init_workspace
```

.bashrcの下から三行目に以下の文を追加する．

```bash
source ~/catkin_ws/devel/setup.bash
```

環境をビルドする．

```bash
cd ~/catkin_ws
catkin_make
source ~/.bashrc
```

作成するパッケージ名、使用するライブラリを作成して指定する．

```bash
cd ~/catkin_ws/src
catkin_create_pkg mypkg rospy
```

パッケージ内にscriptsというディレクトリを作成して，ノードとなるプログラムを置く．

```bashcd mypkg/
mkdir scripts
cd scripts/
```

ROSを立ち上げる

```bash
roscore
```

以下のコマンドを実行．

```bash
chmod +x count.py
rosrun mypkg count.py
```

新しくubuntuを開いて以下コマンドを実行．

```bash
chmod +x twice.py
rosrun mypkg twice.py
```

更に新しくubuntuを開いて以下コマンドを実行．

```bash
rostopic echo /twice
```

実行後は全てctrl + Cで停止

# Note

* GPIO25ピンを利用した回路です．
* LEDは向きがあるので気を付けて．

# Author

* MinoriKatou
* Chiba Institute of Technology
* s20C1033CR@s.chibakoudai.jp

# License

"myled" is under [BSD 3-Clause "New" or "Revised" License](https://www.gnu.org/licenses/).

# Reference

https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbi1UTjB3Y1lYeExtUVNtWHJGM2lSMXpfSVlGd3xBQ3Jtc0ttei1mbTVjTWlzNFdGbFNTNWo2dDZvSS1BU1FYeFhibHl0QXNramtDMlpSN1ZLWTE3T19yM3BKVVBGN2hFbFMtU1k4M2ctaVY5TDJvcEVHdWRSSzhqRUtUbWlDLVBlQ29vQ29rNjNIR2h0dzdzT1BSTQ&q=https%3A%2F%2Fryuichiueda.github.io%2Frobosys2020%2Flesson10_ros.html

Thank you!
