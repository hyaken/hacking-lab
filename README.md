# Hacking Lab

書籍『ハッキング・ラボのつくりかた 仮想環境におけるハッカー体験学習』で使用する仮想マシンです。

## 必要なもの

- [VirtualBox]
- [Vagrant]

[VirtualBox]: https://www.virtualbox.org/
[Vagrant]: https://www.vagrantup.com/

## 使い方

Windows 10 の Vagrant box イメージを下記から入手します。

```
https://developer.microsoft.com/en-us/microsoft-edge/tools/vms/
```

イメージを解凍して取り込みます。

```
$ unzip MSEdge.Win10.Vagrant.zip
$ vagrant box add EdgeOnWindows10.box --name windows10
```

仮想マシンを起動します。

```
$ vagrant up
```

Kali Linux と Windows 10 の仮想マシンが起動します。
個別に起動したい場合は仮想マシン名を次のように指定してください。

```
$ vagrant up kali
$ vagrant up windows10
```
