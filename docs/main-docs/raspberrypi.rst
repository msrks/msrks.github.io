========================================
Raspberry Pi
========================================
.. highlight:: bash

OS Installation @ Mac OS X
------------------------------
@160501

#. 公式サイト `RPI official  <https://www.raspberrypi.org/downloads/raspbian/>`_ よりRASPBIAN JESSIEの最新イメージを取得(かなり時間かかる)

#. zip解凍::

    $ cd Downloads
    $ tar zxvf 2016-05-27-raspbian-jessie.zip

#. SDカードを挿して、下記コマンドで割り当てデバイスを調べる(Mac bookだと、おそらく ``/dev/disk3`` に割り当てられてる)::

    $ diskutil list

#. SDカードをフォーマットする::

    $ sudo diskutil eraseDisk FAT32 RPI /dev/disk3
    Started erase on disk3
    Unmounting disk
    Creating the partition map
    ...
    Finished erase on disk3

#. SDカードをアンマウントする::

    $ sudo diskutil unmountDisk /dev/disk3
    Unmount of all volumes on disk3 was successful

#. SDカードにイメージを書き込む::

    $ sudo dd bs=1m if=2016-05-27-raspbian-jessie.img of=/dev/disk3
    3125+0 records in
    3125+0 records out
    3276800000 bytes transferred in 2784.822319 secs (1176664 bytes/sec)

#. RPIにSDカードを挿して起動し、コンフィグしたら完了::

    pi@raspberrypi ~ $ sudo raspi-config

ipアドレスの設定
------------------------------
ラズパイの場合は、直接 ``/etc/network/interfaces`` をいじらずに、 dhcpクライアントデーモンの設定ファイル``/etc/dhcpcd.conf`` をいじる。::

    $ sudo leafpad /etc/dhcpcd.conf
    $ sudo /etc/init.d/dhcpcd reload
