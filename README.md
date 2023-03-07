# dev_humble with vnc
[![Open in Dev Containers](https://img.shields.io/static/v1?label=Dev%20Containers&message=Open&color=blue&logo=visualstudiocode)](https://vscode.dev/redirect?url=vscode://ms-vscode-remote.remote-containers/library-specification?url=https://github.com/teruyamato0731/dev_humble_with_vnc)

ROS2 humbleのdev container開発環境。
VNCを使用することでUbuntu以外の環境でも使用することができる。

# Quick Start
あなたがすでにVS CodeとDockerをインストールしている場合は、上記のバッジまたは[こちら](https://vscode.dev/redirect?url=vscode://ms-vscode-remote.remote-containers/cloneInVolume?url=https://github.com/teruyamato0731/dev_humble_with_vnc)をクリックすることで使用することができる。<br>
これらのリンクをクリックすると、vscodeが必要に応じてdev container拡張機能を自動的にインストールし、ソースコードをコンテナボリュームにクローンし、使用するためのdev containerを起動する。

# How to use
1. Docker, vscode, devcontainer拡張機能をインストールする。
1. GitHub上部の緑の「Use this template」を押し、自身のGitHubアカウントで新規リポジトリを作成。
1. リポジトリをcloneしvscodeで開く。リポジトリのリンクやディレクトリ名は各自で読み替えること。
    ```bash
    git clone https://github.com/teruyamato0731/dev_humble_with_vnc.git
    code dev_humble_with_vnc
    ```
1. 下記コマンドでuidとgidを調べられるので、必要に応じてダウンロードしてきた[.devcontainer/devcontainer.json](.devcontainer/devcontainer.json) を編集する。
    ```bash
    echo uid:$(id -u) gid:$(id -g)
    # uid:1000 gid:1000
    ```
    ```json
    "userUid": "1000",
    "userGid": "1000"
    ```
1. 必要に応じて[.devcontainer/.env](.devcontainer/.env)を編集する
    COMPOSE_PROJECT_NAMEに従って、コンテナ名やワークスペースのディレクトリが変更される
    ```
    COMPOSE_PROJECT_NAME=dev_humble_with_vnc
    ```
1. 「Reopen in Container」でdevcontainerを開く
1. ブラウザから[localhost:6080](localhost:6080)へ接続しデスクトップ環境へアクセスする。
