# ssh

パッケージの管理を行うためのaptitudeをインストール

```
sudo apt-get install aptitude
```

aptitudeを使ってsshを導入
```
sudo aptitude install ssh
```

/etc/ssh/sshd_configを編集し、PermitRootLoginの行を
PermitRootLogin no
に書き換える

```
sudo /etc/init.d/ssh restart
```
でsshdのサービスを再起動させる

 

# マウント

### nfs-common install

```
sudo apt-get install nfs-common
```


実行した時に許可がなかった場合はrootユーザーで実行する  
rootユーザーへの切り替えは以下コマンドを実行  

```
sudo su -
```

### 改訂版

```
mkdir /mnt/フォルダ名 
sudo echo "アドレス:/homes /mnt/フォルダ名 nfs rw 0 0" >> /etc/fstab  
sudo mount -a  
ln -s /mnt/フォルダ名/* /home/
```
1.マウントするディレクトリ作成  
2.FSのアドレス等を書き込み  
3.マウント実行  
4.シンボリックリンク作成  

