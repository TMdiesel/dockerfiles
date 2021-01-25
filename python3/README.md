# Dockerfile for python3 environment
VSCodeを用いたPython用のDocker環境の構築方法です。

## 手順
ホスト環境がwindows10であることを想定します。
手順は以下のとおりです。
1. WSL2をインストールする
1. [Setting up to Run Containers](https://docs.nvidia.com/cuda/wsl-user-guide/index.html#setting-containers)に従って、Dockerをインストールする
1. [CUDA on Windows Subsystem for Linux (WSL)](https://developer.nvidia.com/cuda/wsl)からNVIDIAドライバーをインストールする
1. [Setting up CUDA Toolkit](https://docs.nvidia.com/cuda/wsl-user-guide/index.html#running-cuda)に従って、nvidia-container-toolkitパッケージをインストールする
1. VSCoceの[Remote Containers](https://code.visualstudio.com/docs/remote/containers)を使ってコンテナにリモート接続する

手順の3,4はGPUの設定です。不要な場合はそこをスキップして、`devcontainer.json`の下記をコメントアウトしてください。
```
"runArgs": ["--gpus=all"]
```

## 参考
- https://github.com/microsoft/vscode-dev-containers