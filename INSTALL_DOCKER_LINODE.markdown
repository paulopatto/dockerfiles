# Instalando o docker no Linode

> Baseado no artigo [Install Docker on Linode de Mike Milano](http://goo.gl/kIbvrV).

Bem para usar o docker.io vamos criar uma instancia Ubuntu 12.04 no Linode e instale o kernel especifico conforme indica o [tutorial do próprio linode](http://goo.gl/OR8AP9)

```shell
  # Run this commando with root or sudo
  $ sudo apt-get install -y linux-virtual grub-legacy-ec2
```
Localize a seguinte linha no arquivo `/boot/grub/menu.list`:

```shell
  # defoptions=console=hvc
```

deixar ela assim:

```shell
  # defoptions=console=hvc0 rootflags=nobarrier
```

Regere o grub menu.list com o comando

```shell
  # Executar como root ou sudo
  $ sudo update-grub-legacy-ec2
```

Agora vá ao *Linode Manager Dashboad* e edite suas configurações de perfil da instancia para:

> **Kernel:** pv-grub-x86_64
> **Xenify Distro:** No

Efetue *reboot* do servidor após modificar as configurações.

Agora instale o docker com o seguinte script:

```shell
  $ sudo apt-get install python-software-properties
  $ sudo apt-get install linux-image-extra-`uname -r`
  $ sudo apt-get install software-properties-common
  $ sudo add-apt-repository ppa:dotcloud/lxc-docker
  $ sudo apt-get update
  $ sudo apt-get install lxc-docker
```

Prontinho
