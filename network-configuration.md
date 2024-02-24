## ネットワーク設定
初期設定として下記のセットワーク設定が適用される。必要に応じて`/etc/systemd/network/20-wired.network`から変更する。
```
[Match]
Name=eth0

[Network]
DNS=192.168.0.1

[Address]
Address=192.168.0.99/24

[Route]
Gateway=192.168.0.1
```
  
また、複数のFPGAボードでpetalinuxを使用する時はMACアドレスが重複する場合があるので、その時は以下の方法で変更する。  
`sudo sh -c 'echo "ethaddr=02:11:44:33:44:55" >> /run/media/mmcblk0p1/uEnv.txt'`
