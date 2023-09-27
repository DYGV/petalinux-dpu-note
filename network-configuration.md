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
