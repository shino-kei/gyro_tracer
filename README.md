# README


# gyro_tracer
EV3のジャイロセンサを利用した倒立振子ライントレーサプログラム（RobotC環境向け）

## ロボットの組み立て方

本プログラムのロボットはこちらのロボットをベースにしています．

http://robotsquare.com/2014/06/23/tutorial-building-balanc3r/

別のロボットの場合，倒立制御の制御パラメータを変更する必要があります．

ライントレースのサンプルプログラムでは，ラインを挟むようにカラーセンサとnxt光センサをそれぞれ1個ずつ配置しています．また，2つのセンサの感度は異なるので，nxtlightGainを乗じることで左右の計測値が吊り合うよう補正しています．[[リンク]](https://github.com/shino-kei/gyro_tracer/blob/master/tracer.c#L492)

> lineError = ( (SensorValue(lightSensor) - threshould) - (SensorValue(nxtlightSensor)-nxtthreshould) * nxtlightGain )/2;

1個のセンサを使う場合や，2個ともEV3カラーセンサを用いる場合などは適宜読み替えてください．


## プログラム
倒立制御のコアな部分に関しては，下記リンクのコードをベースとしています．
tracer.cでは左右モータのパワー比を変化させることにより左右カーブを実現し，下向きに取り付けられたカラーセンサ値に応じてこのパワー比を変化させることによって，ライントレースを行います．

```
// averagePower : 並進運動入力
// extra_pwr    : 回転運動入力

pwr_c = averagePower - extra_pwr;
pwr_b = averagePower + extra_pwr;

```

http://www.robotc.net/forums/viewtopic.php?f=1&t=9673


* balancer.c : 倒立振子プログラム
* tracer.c  : 倒立振子+ライントレース


## 調整項目
* 倒立制御パラメータ
* ライントレースパラメータ
  * float threshould
  * float nxtthreshould
  * float nxtlightGain
  * float kpline
  * float kiline
  * float kdline

## TODO
[ x ] balancer.cの動作確認



## 参考リンク
* http://robotsquare.com/2014/06/23/tutorial-building-balanc3r/
* http://www.robotc.net/forums/viewtopic.php?f=1&t=9673
