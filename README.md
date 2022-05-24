# posenet-hand-on-tensorrt
posenet-hand-on-tensorrt は、TensorRT 上で Hand の AIモデル を動作させるマイクロサービスです。  

## 動作環境

- PoseNet
- Docker
- TensorRT Runtime

## PoseNet Handについて
PoseNet Hand は、手の関節の位置を推定することにより、画像や動画内の手のポーズを推定するAIモデルです。  
PoseNet Hand は、特徴抽出にResNet18を使用してます。

## 動作手順
### Dockerコンテナの起動
Makefile に記載された以下のコマンドにより、Hand の Dockerコンテナ を起動します。
```
make docker-run
```
### ストリーミングの開始
以下のコマンドにより、TensorRT 上の PoseNet でストリーミングを開始します。  

```
build/aarch64/bin/posenet /dev/video0
```

## engineファイルについて
本レポジトリのengineファイルは、posenet-hand-on-tensorrt/data/networks/Pose-ResNet18-Hand/pose_resnet18_hand.onnx.1.1.8001.GPU.FP16.engine にあります。  
なお、PoseNet Handの NVIDIA Jetson用の engineファイルは、[jetson-inference](https://github.com/dusty-nv/jetson-inference) からダウンロードできます。  



