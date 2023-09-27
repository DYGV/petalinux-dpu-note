## ログイン
## アクセスの方法
### SSH接続
`ssh petalinux@192.168.0.99`で接続する。  
初回ログイン時はパスワードは設定されていない。  

### シリアル接続
もしくは、シリアル通信によりアクセスすることができる。  
シリアル接続の場合は`root`ユーザに自動ログインされる。  
`root`ユーザの初期パスワードは`root`  
```
$ sudo screen /dev/ttyUSB0 115200 
PetaLinux 2022.2_release_S10071807 zynqmp-common-2022-2 ttyPS0

zynqmp-common-2022-2 login: root (automatic login)

root@zynqmp-common-2022-2:~# su petalinux 
You are required to change your password immediately (administrator enforced).
su: Authentication token is no longer valid; new one required
(Ignored)
petalinux@zynqmp-common-2022-2:/home/root$ cd 
petalinux@zynqmp-common-2022-2:~$ pwd 
/home/petalinux
petalinux@zynqmp-common-2022-2:~$
```

## パスワードの変更
初期の`petalinux`ユーザはパスワードが設定されていないため`passwd`で設定する。
```
petalinux@zynqmp-common-2022-2:~$ passwd 
New password: 
Retype new password: 
passwd: password updated successfully
petalinux@zynqmp-common-2022-2:~$ 
```
