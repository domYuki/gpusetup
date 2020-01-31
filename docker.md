# Dockerのインストール

Dockerをインストール。   
Dockerの公式ドキュメントに従ってdocker-ceをインストール。  
(https://docs.docker.com/install/linux/docker-ce/ubuntu/#set-up-the-repository)  
まずはドキュメントのSET UP THE REPOSITORYに従って以下のようにコマンドしていく。  

```
sudo apt-get update  
sudo apt-get install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -  
sudo apt-key fingerprint 0EBFCD88  
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"  
```
 

次にドキュメントのINSTALL DOCKER CEに従って以下のようにコマンド。  

```
sudo apt-get update  
sudo apt-get install docker-ce docker-ce-cli containerd.io  
```

# docker composeインストール  

```  
curl -L https://github.com/docker/compose/releases/download/1.24.1/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose  
chmod +x /usr/local/bin/docker-compose  
```  

もし "Permission denied" エラーが出たら、おそらく /usr/local/bin ディレクトリが書き込み可能ではないため、Compose のインストールをスーパーユーザで行う必要がある。  
sudo -i を実行してから、先ほどの２つのコマンドを実行し、実行する  

```  
sudo pip install -U docker-compose  
```  

docker-compose --version を実行してインストールをテスト。  

# Nvidia-Dockerのインストール  

Nvidia-Dockerをインストール
これもNvidia-Dockerの公式ドキュメントに従うだけ  
(https://github.com/NVIDIA/nvidia-docker/wiki/Installation-(version-2.0))

まずはRepository configurationのDebian-based distributionsの項目に従って以下のようにコマンドしていく。  
(https://nvidia.github.io/nvidia-docker/)


```
curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | sudo apt-key add -  
distribution=$(. /etc/os-release;echo $ID$VERSION_ID)  
curl -s -L https://nvidia.github.io/nvidia-docker/$distribution/nvidia-docker.list | sudo tee /etc/apt/sources.list.d/nvidia-docker.list  
sudo apt-get update  
```

次にNvidia-Dockerのドキュメントの指示に戻って以下のようにコマンド  

```
sudo apt-get install nvidia-docker2
sudo pkill -SIGHUP dockerd
```

これでNvidia-Dockerのインストールは完了です。  
:bug: :bug: :bug: :bug: :bug: :bug: :bug: :bug: :bug: :bug: :bug: :bug: