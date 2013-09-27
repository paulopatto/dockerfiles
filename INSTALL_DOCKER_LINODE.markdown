# Instalando o docker no Linode

> Baseado no artigo [Install Docker on Linode de Mike Milano](http://goo.gl/kIbvrV).

1. Criar uma instancia Ubuntu 12.04 no Linode
2. Instale o kernel especifico conforme indica o [tutorial do próprio linode](http://goo.gl/OR8AP9)

```shell
  # Run this commando with root or sudo
  $ sudo apt-get install -y linux-virtual grub-legacy-ec2
```
3. Ache a seguinte linha no arquivo `/boot/grub/menu.list`

```shell
  # defoptions=console=hvc
```

> deixar ela assim:

```shell
  # defoptions=console=hvc0 rootflags=nobarrier
```
