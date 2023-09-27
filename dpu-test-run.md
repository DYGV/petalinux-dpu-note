## DPU IPコアの動作確認
DPUの動作確認として、顔画像・人体画像を使った顔検出・姿勢推定を実行する。

1. `petalinux`ユーザでログイン後、ホームディレクトリに以下のディレクトリがあるか確認
    ```console
    $ ls
    dpu_sw_optimize  test_run
    ```
2. 顔検出実行
   事前学習済み顔検出モデル(DenseBox)を用いて入力画像を顔検出処理
    ```console
    $ cd ~/test_run/face_detection/
    $ sudo ./build/simple densebox_640_360_xczu19eg_dpu/densebox_640_360_xczu19eg_dpu.xmodel ./face.jpg
      x: 255, y: 124
    ```
3. 姿勢推定実行
  事前学習済み姿勢推定モデル(OpenPose)を用いて入力画像を姿勢推定処理
    ```console
    $ cd ~/test_run/pose_estimation/
    $ sudo ./build/simple ./openpose_368_368_xczu19eg_dpu/openpose_368_368_xczu19eg_dpu.xmodel ./pose.jpg
      type: 0, x: 0, y: 0,type: 0, x: 0, y: 0,type: 0, x: 0, y: 0,type: 0, x: 0, y: 0,type: 0, x: 0, y: 0,type: 0, x: 0, y: 0,type: 0, x: 0, y: 0,type: 0, x: 0, y: 0,type: 0, x: 0, y: 0,type: 0, x: 0, y: 0,type: 0, x: 0, y: 0,type: 0, x: 0, y: 0,type: 0, x: 0, y: 0,type: 0, x: 0, y: 0,
      type: 1, x: 207, y: 75,type: 1, x: 214, y: 108,type: 1, x: 224, y: 122,type: 1, x: 229, y: 164,type: 1, x: 227, y: 202,type: 1, x: 208, y: 122,type: 1, x: 210, y: 165,type: 1, x: 204, y: 199,type: 1, x: 218, y: 204,type: 1, x: 218, y: 255,type: 1, x: 221, y: 301,type: 1, x: 213, y: 205,type: 1, x: 211, y: 254,type: 1, x: 215, y: 294,

    ```
