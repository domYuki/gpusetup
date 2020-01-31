## nvidia driver

ドライバインストール時にgcc必要  

```
sudo apt install build-essential  
```

ここから自分の環境にあった設定で検索。  
https://www.nvidia.com/Download/index.aspx  

ダウンロードリンクをコピーしてコマンド実行でダウンロードする

```
wget リンク
```

nouveau止める  

「/etc/modprobe.d/blacklist.conf」に「blacklist nouveau」を追加.  
->これでnouveauが次にLinuxに読みこなくさせるようにできます。  
「sudo update-initramfs -u」でOSに反映。ここ忘れがち。



ダウンロードしたファイルに実行権限を付与して実行。  

```
chmod +x NVIDIA-Linux-x86_64-[バージョン].run  
sudo ./NVIDIA-Linux-x86_64-[バージョン].run   
```

インストール後、nvidia-smiを実行していつものやつが表示されればおｋ  

# cuda toolkit install(やらなくていい)

以下コマンドで実行  

```
sudo apt install nvidia-cuda-toolkit  
```

以下コマンドでインストールされているのかチェック    

```
nvcc -V
```