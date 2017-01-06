# README


# gyro_tracer
EV3のジャイロセンサを利用した倒立振子ライントレーサプログラム（RobotC環境向け）

## ロボットの組み立て方

本プログラムのロボットはこちらのロボットをベースにしています．

http://robotsquare.com/2014/06/23/tutorial-building-balanc3r/

別のロボットの場合，倒立制御の制御パラメータを変更する必要があります．


## プログラム
http://www.robotc.net/forums/viewtopic.php?f=1&t=9673
のコードをベースにしています．

* balancer.c : 倒立振子プログラム
* tracer.c  : 倒立振子ライントレースプログラム


## 調整項目
* 倒立制御パラメータ
* ライントレースパラメータ
* ライントレースしきい値

## TODO
- [ ] balancer.cの動作確認



## 参考リンク
* http://robotsquare.com/2014/06/23/tutorial-building-balanc3r/
* http://www.robotc.net/forums/viewtopic.php?f=1&t=9673
