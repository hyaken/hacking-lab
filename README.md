# Hacking Lab

書籍『ハッキング・ラボのつくりかた 仮想環境におけるハッカー体験学習』で使用する仮想マシンです。

## 必要なもの

- [VirtualBox]
- [Vagrant]

[VirtualBox]: https://www.virtualbox.org/
[Vagrant]: https://www.vagrantup.com/

## 準備

Kali Linux と Windows 10 の仮想マシンが構築できますが、Windows 10 はサイトからイメージを取り込んでおく必要があります。
まず Windows 10 の Vagrant box イメージを下記から入手します。

```
https://developer.microsoft.com/en-us/microsoft-edge/tools/vms/
```

イメージを解凍して取り込みます。

```
$ unzip MSEdge.Win10.Vagrant.zip
$ vagrant box add EdgeOnWindows10.box --name windows10
```

## 起動

Kali Linux を起動するには下記コマンドを実行します。

```
$ vagrant up
or
$ vagrant up kali
```

Windows 10 を起動するには下記コマンドを実行します。
```
$ vagrant up windows10
```
