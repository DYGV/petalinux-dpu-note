## パッケージマネージャ
Petalinuxではパッケージマネージャとして`dnf`を用いる。
- パッケージのアップデート
    ```
    dnf check-update
    dnf update
    ```
- `libpng`や`cmake`など基本的なパッケージ
    ```
    dnf install packagegroup-petalinux
    ```
- `vim`や`gcc`、`git`など開発に使うパッケージ
    ```
    dnf install packagegroup-petalinux-self-hosted
    ```
