## ルートファイルシステムのサイズの変更
SDカードにイメージを焼いた初期状態では、ルートファイルシステムのディスクが3GBに割り当てられる。
```
$ lsblk
 NAME        MAJ:MIN RM  SIZE RO TYPE MOUNTPOINTS
 mmcblk0     179:0    0 29.7G  0 disk
 |-mmcblk0p1 179:1    0  976M  0 part /run/media/mmcblk0p1
 `-mmcblk0p2 179:2    0    3G  0 part /
```

簡単にディスクサイズを増やすには、`bash -x /home/petalinux/dpu_sw_optimize/zynqmp/zynqmp_dpu_optimize.sh`を実行するとよい。詳しくは[Zynq UltraScale＋ MPSoC DPU TRD V4.1 Vitis 2022.2 5.5.3 Known issuesのfine-tune](https://github.com/Xilinx/Vitis-AI/blob/3.0/dpu/ref_design_docs/README_DPUCZ_Vitis.md#fine-tune)を参照すること。実行時のログは以下の通りである。

```
$ sudo /home/petalinux/dpu_sw_optimize/zynqmp/zynqmp_dpu_optimize.sh
 Auto resize ext4 partition ...[✔]
 Start QoS config ...[✔]
```
これでサイズを増やすことができた。
```
$ lsblk
 NAME        MAJ:MIN RM  SIZE RO TYPE MOUNTPOINTS
 mmcblk0     179:0    0 29.7G  0 disk
 |-mmcblk0p1 179:1    0  976M  0 part /run/media/mmcblk0p1
 `-mmcblk0p2 179:2    0 28.8G  0 part /
```
