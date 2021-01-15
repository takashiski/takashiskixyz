

## やりかた

https://reprap.org/wiki/PID_Tuning/ja


## teraterm使う場合

* 115200
* ログを設定する
* 受信改行コードはLF


### ノズル結果

#### 200

```
Connecting...
echo:start
Marlin 2.0.7.2
echo: Last Updated: 2020-10-15 | Author: (kad, Anycubic Mega Zero)
echo:Compiled: Dec 13 2020
echo: Free Memory: 11479  PlannerBufferBytes: 1376
>>> M303 E0 S200 C8
[ERROR] Printer is not online.
DIGIPOTS Loading
DIGIPOTS Loaded
DIGIPOTS Loading
DIGIPOTS Loaded
echo:V82 stored settings retrieved (669 bytes; crc 12794)
echo:SD card ok
Printer is now online.
>>> M303 E0 S200 C8
SENDING:M303 E0 S200 C8
PID Autotune start
 bias: 110 d: 110 min: 194.38 max: 208.05
 bias: 108 d: 108 min: 194.40 max: 206.68
 bias: 106 d: 106 min: 195.06 max: 206.60 Ku: 23.38 Tu: 31.62
 Classic PID
 Kp: 14.03 Ki: 0.89 Kd: 55.45
 bias: 106 d: 106 min: 194.86 max: 205.43 Ku: 25.53 Tu: 30.64
 Classic PID
 Kp: 15.32 Ki: 1.00 Kd: 58.67
 bias: 105 d: 105 min: 195.28 max: 204.90 Ku: 27.82 Tu: 29.98
 Classic PID
 Kp: 16.69 Ki: 1.11 Kd: 62.56
 bias: 105 d: 105 min: 195.03 max: 205.16 Ku: 26.40 Tu: 30.80
 Classic PID
 Kp: 15.84 Ki: 1.03 Kd: 60.99
 bias: 106 d: 106 min: 194.86 max: 205.20 Ku: 26.11 Tu: 30.31
 Classic PID
 Kp: 15.67 Ki: 1.03 Kd: 59.36
 bias: 105 d: 105 min: 195.40 max: 205.78 Ku: 25.75 Tu: 30.48
 Classic PID
 Kp: 15.45 Ki: 1.01 Kd: 58.86
PID Autotune finished! Put the last Kp, Ki and Kd constants from below into Configuration.h
#define DEFAULT_Kp 15.45
#define DEFAULT_Ki 1.01
#define DEFAULT_Kd 58.86
```

#### 190

```
>>> M303 C8 S190 E0
SENDING:M303 C8 S190 E0
PID Autotune start
 bias: 101 d: 101 min: 184.16 max: 195.60
 bias: 100 d: 100 min: 184.64 max: 195.20 Ku: 24.12 Tu: 31.46
 Classic PID
 Kp: 14.47 Ki: 0.92 Kd: 56.90
 bias: 99 d: 99 min: 185.00 max: 195.37 Ku: 24.31 Tu: 31.62
 Classic PID
 Kp: 14.59 Ki: 0.92 Kd: 57.66
 bias: 99 d: 99 min: 184.64 max: 195.11 Ku: 24.07 Tu: 31.46
 Classic PID
 Kp: 14.44 Ki: 0.92 Kd: 56.78
 bias: 99 d: 99 min: 184.81 max: 195.31 Ku: 24.00 Tu: 31.95
 Classic PID
 Kp: 14.40 Ki: 0.90 Kd: 57.51
 bias: 99 d: 99 min: 184.76 max: 195.06 Ku: 24.48 Tu: 31.46
 Classic PID
 Kp: 14.69 Ki: 0.93 Kd: 57.77
 bias: 99 d: 99 min: 184.78 max: 195.14 Ku: 24.34 Tu: 31.29
 Classic PID
 Kp: 14.60 Ki: 0.93 Kd: 57.11
PID Autotune finished! Put the last Kp, Ki and Kd constants from below into Configuration.h
#define DEFAULT_Kp 14.60
#define DEFAULT_Ki 0.93
#define DEFAULT_Kd 57.11
```


#### 20201227

```
#define DEFAULT_Kp 13.95
#define DEFAULT_Ki 0.84
#define DEFAULT_Kd 57.87
```

### ベッド

#### 間違えたやつ

```
>>> M303 E-1 S60 C8 
SENDING:M303 E-1 S60 C8
PID Autotune start
 bias: 100 d: 100 min: 59.74 max: 60.47
 bias: 87 d: 87 min: 59.87 max: 60.30
 bias: 88 d: 88 min: 59.73 max: 60.17 Ku: 501.27 Tu: 10.32
 No overshoot
 Kp: 100.25 Ki: 19.43 Kd: 344.94
 bias: 88 d: 88 min: 59.69 max: 60.23 Ku: 411.94 Tu: 10.49
 No overshoot
 Kp: 82.39 Ki: 15.71 Kd: 287.98
 bias: 83 d: 83 min: 59.88 max: 60.35 Ku: 455.11 Tu: 10.81
 No overshoot
 Kp: 91.02 Ki: 16.84 Kd: 328.07
 bias: 78 d: 78 min: 59.91 max: 60.31 Ku: 492.08 Tu: 10.81
 No overshoot
 Kp: 98.42 Ki: 18.20 Kd: 354.72
 bias: 73 d: 73 min: 59.83 max: 60.29 Ku: 405.33 Tu: 10.98
 No overshoot
 Kp: 81.07 Ki: 14.77 Kd: 296.65
 bias: 73 d: 73 min: 59.82 max: 60.16 Ku: 539.87 Tu: 10.16
 No overshoot
 Kp: 107.97 Ki: 21.26 Kd: 365.60
PID Autotune finished! Put the last Kp, Ki and Kd constants from below into Configuration.h
#define DEFAULT_bedKp 107.97
#define DEFAULT_bedKi 21.26
#define DEFAULT_bedKd 365.60
```

#### 正しいやつ

```
>>> M303 E-1 C8 S90
SENDING:M303 E-1 C8 S90
PID Autotune start
 bias: 132 d: 122 min: 89.65 max: 90.00
 bias: 175 d: 79 min: 89.37 max: 90.12
 bias: 183 d: 71 min: 89.68 max: 90.18 Ku: 362.82 Tu: 12.78
 No overshoot
 Kp: 72.56 Ki: 11.36 Kd: 309.13
 bias: 155 d: 99 min: 89.92 max: 90.41 Ku: 514.64 Tu: 17.04
 No overshoot
 Kp: 102.93 Ki: 12.08 Kd: 584.60
 bias: 144 d: 110 min: 89.97 max: 90.35 Ku: 753.76 Tu: 11.47
 No overshoot
 Kp: 150.75 Ki: 26.29 Kd: 576.33
 bias: 144 d: 110 min: 89.90 max: 90.19 Ku: 975.45 Tu: 10.16
 No overshoot
 Kp: 195.09 Ki: 38.41 Kd: 660.57
 bias: 145 d: 109 min: 89.77 max: 90.10 Ku: 842.66 Tu: 10.32
 No overshoot
 Kp: 168.53 Ki: 32.66 Kd: 579.86
 bias: 156 d: 98 min: 89.80 max: 90.19 Ku: 642.32 Tu: 11.31
 No overshoot
 Kp: 128.46 Ki: 22.73 Kd: 484.10
PID Autotune finished! Put the last Kp, Ki and Kd constants from below into Configuration.h
#define DEFAULT_bedKp 128.46
#define DEFAULT_bedKi 22.73
#define DEFAULT_bedKd 484.10
```

#### 実際

* 上記設定では、ベッド温度がおおよそ設定温度-10度程度までしか上がらず、タイムアウトしてしまう
* `やりかた`内の解説を参考に、Kiを30まであげたところ到達するようになった
* もうすこしあげてもいいかもしれない

```
手動調整のコツ:

オーバーシュート (目標値を通り過ぎて変化しすぎてしまうこと) が多く見られる場合や、発振が見られる場合には、積分ゲインを増やすか、全てのゲインを減らすかのどちらかを行う必要があります。
オーバーシュートの幅が大きいですか? Dを増やし、Pを減らしましょう。
レスポンスが悪くなりすぎましたか? Pを増やしましょう。
ターゲット温度の下まではすぐに加熱するのに (0-160℃まで早い)、ターゲット温度に近づくにつれ、遅くなりすぎていますか? (160-170℃で遅く、170-180℃で異常に遅いなど) I 定数を増やしてみましょう。
```