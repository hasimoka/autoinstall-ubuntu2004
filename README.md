# autoinstall-ubuntu2004

## Ubuntu20.04のインストーラーISOファイルを作成する

1. ubuntu-autoinstall-generatorに必要なパッケージのインストール
    ```
    $ cd ~/autoinstall-ubuntu2004
    $ sudo apt install -y xorriso sed curl gpg isolinux
    ```
1. ubuntu-autoinstall-generatorを実行し、ISOファイルを作成する
    ```
    $ sudo ./ubuntu-autoinstall-generator.sh -a -k -u server/user-data -m server/meta-data -d ubuntu-20.04-autoinstall.iso
    ```
1. 作成したISOファイルをUSBメディアに書き出す
    ```
    $ sudo parted -l 
    $ sudo dd if=ubuntu-20.04-autoinstall.iso of=/dev/sdc bs=1024k status=progress && sync
    ```