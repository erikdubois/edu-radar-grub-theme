# Radar Grub theme

Educational tutorial

all credits to the developer of darkmatter grub


### ✔️ Installation on ArcoLinux

```shell
git clone --depth 1 https://github.com/erikdubois/radar-grub-theme.git && cd radar-grub-theme
sudo python3 radar-theme.py --install
```


Copyright at the end of this file

coming from 

https://gitlab.com/VandalByte/darkmatter-grub-theme


Learn, have fun and enjoy.


# Websites

Information : https://arcolinux.info

Tutorials about ArcoLinux iso (Xfce, Openbox and i3) : https://arcolinux.com

Tutorials about ArcoLinuxD iso (any desktop) : https://arcolinuxd.com

Tutorials about ArcoLinuxB iso (any desktop) : https://arcolinuxb.com

Tutorials about Carli project (any desktop) : https://arcolinuxiso.com

Forum : https://arcolinuxforum.com


# Social Media

Facebook : https://www.facebook.com/arcolinuxd/

Facebook : https://www.facebook.com/groups/arcolinux/

Twitter  : https://twitter.com/arcolinux

Instagram: https://www.instagram.com/arcolinux/

Linked in: https://www.linkedin.com/in/arcolinux

Youtube  : https://www.youtube.com/erikdubois


# Arcolinux keys for anything Arch Linux based


Get keys and mirrors from ArcoLinux

The ArcoLinux repos are added to your /etc/pacman.conf


`wget bit.ly/get-arcolinux-keys && chmod +x ./get-arcolinux-keys && sudo ./get-arcolinux-keys`


Get keys and mirrors from ArcoLinux and install <b>archlinux-tweak-tool-git</b>

The ArcoLinux repos are added to your /etc/pacman.conf


`wget bit.ly/get-arcolinux-keys && chmod +x ./get-arcolinux-keys  && sudo ./get-arcolinux-keys && sudo pacman -Syu archlinux-tweak-tool-git`


# ArchLinux Tweak Tool info

Install the ATT from the AUR

yay archlinux tweak

paru archlinux tweak

select the correct number and install it

You can get the keys and mirrors in via the ATT

You can find all information about the ATT here

https://github.com/arcolinux/archlinux-tweak-tool


Watch the videos on ATT

https://www.youtube.com/playlist?list=PLlloYVGq5pS5nvFc_LYRE82Gh3XWA6rVH


<div align="center">
  <img width=90% src="https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/banner.png" alt="banner" />
</div>

<div align="center">
  <a href="https://gitlab.com/VandalByte/darkmatter-grub-theme/-/raw/main/LICENSE">
    <img src="https://img.shields.io/badge/License-008a8a?style=for-the-badge" alt="license" />
  </a>
  <a href="https://www.pling.com/p/1603282">
    <img src="https://img.shields.io/badge/Download-green?style=for-the-badge" alt="license" />
  </a>
  <a href="https://github.com/VandalByte/darkmatter-grub2-theme">
    <img src="https://img.shields.io/badge/github%20(mirror)-303030?style=for-the-badge" alt="license" />
  </a>
</div>

### ✔️ Installation

```shell
git clone --depth 1 https://gitlab.com/VandalByte/darkmatter-grub-theme.git && cd darkmatter-grub-theme
sudo python3 darkmatter-theme.py --install
```

### ✔️ Manual Installation

<details>
 <summary><b>Debian ✨ Ubuntu ✨ Arch</b></summary>
 
  #### 1️⃣ Download your favourite version of the theme from [**Pling**](https://www.pling.com/p/1603282/)

  Now extract your downloaded .zip file.

  Either manually extract it or use the command below. ( *Here I'm using debian version of my theme as an example* )
  ```shell
  unzip dark-matter-debian.zip
  ```
  *The rest of the commands are the same for all theme styles.*

  #### 2️⃣ Copy the theme directory.
  ```shell
  sudo cp -r dark-matter /boot/grub/themes/
  ```
  #### 3️⃣ Make changes to the GRUB config file.

  ```shell
  sudo nano /etc/default/grub
  ```
  Find the line `GRUB_THEME=` then change it to `GRUB_THEME="/boot/grub/themes/dark-matter/theme.txt"`

  Then save the file.

  #### 4️⃣ Finally, update the grub.
  ```shell
  sudo grub-mkconfig -o /boot/grub/grub.cfg
  ```
  Now the theme should be installed successfully, enjoy !!
</details>

<details>
 <summary><b>Fedora ✨ Redhat</b></summary>
 
  #### 1️⃣ Download your favourite version of the theme from [**Pling**](https://www.pling.com/p/1603282/)

  Now extract your downloaded .zip file.

  Either manually extract it or use the command below. ( *Here I'm using debian version of my theme as an example* )
  ```shell
  unzip dark-matter-debian.zip
  ```
  *The rest of the commands are the same for all theme styles.*

  #### 2️⃣ Copy the theme directory.
  ```shell
  sudo cp -r dark-matter /boot/grub2/themes/
  ```
  #### 3️⃣ Make changes to the GRUB config file.

  ```shell
  sudo nano /etc/default/grub
  ```
  Find the line `GRUB_THEME=` then change it to `GRUB_THEME="/boot/grub2/themes/dark-matter/theme.txt"`
 
  Change the line `GRUB_TERMINAL_OUTPUT=console` to this *(comment it out)* `#GRUB_TERMINAL_OUTPUT=console`

  Then save the file.

  #### 4️⃣ Finally, update the grub.
  ```shell
  sudo grub2-mkconfig -o /boot/grub2/grub.cfg
  ```
  Now restart your computer the grub theme should be installed successfully, enjoy !!
</details>

<details>
 <summary><b>NixOS</b></summary>
 
  #### 1️⃣ Add darkmatter-grub-theme to your flake as nixos module

  ```nix
  {
    inputs = {
      nixpkgs.url = github:NixOS/nixpkgs/nixos-unstable;

      darkmatter-grub-theme = {
        url = gitlab:VandalByte/darkmatter-grub-theme;
        inputs.nixpkgs.follows = "nixpkgs";
      };
    };

    outputs = inputs @ { self, nixpkgs, darkmatter-grub-theme }: {
      nixosConfigurations.mysystem = nixpkgs.lib.nixosSystem {
        system = "x86_64-linux";
        modules = [
          darkmatter-grub-theme.nixosModule
          ./path/to/your/configuration.nix
        ];
      };
    };
  }
  ```

  #### 2️⃣ Enable and configure grub theme

  ```nix
  boot = {
    # Use the GRUB 2 boot loader.
    loader.grub = {
      enable = true;
      version = 2;

      darkmatter-theme = {
        enable = true;
        style = "nixos";
        icon = "color";
        resolution = "1080p";
      };
    };
  };
  ```
  #### 3️⃣ Save changes and rebuild your nixos

  ```fish
  sudo nixos-rebuild boot --flake .#mysystem
  ```

  Now the theme should be installed successfully, enjoy !!
</details>


> **To request a theme for a specific Linux distro, open an issue with the `feature request` label and let me know**

### ❌ Uninstallation
```shell
sudo python3 darkmatter-theme.py --uninstall
```
**With a little effort the theme's text colours, progress bar colours, progress bar text, and so on can all be customised in `theme.txt` to your liking 💕**
<div align="center">
  <b>Please consider 🤗 giving this project a star ⭐ if you liked it</b>
</div>

<div align="center">
  <b>To stay up to date on all future updates, follow me on 💬 <a href="https://github.com/VandalByte">Github</a>, 💬 <a href="https://gitlab.com/VandalByte">GitLab</a> or 💬 <a href="https://twitter.com/VandalByte">Twitter</a></b>
</div>

  
### 📸 Preview

|    |    |    |
|:-------:|:-------:|:---------:|
|![Arch](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-arch.png)|![Arch Strike](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-archstrike.png)|![Artix](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-artix.png)|
|**Arch Linux**|**Arch Strike**|**Artix Linux**|
|![Black Arch](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-blackarch.png)|![CentOS](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-centos.png)|![Chrome OS](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-chromeos.png)|
|**Black Arch**|**CentOS**|**Chrome OS**|
|![Debian](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-debian.png)|![Deepin](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-deepin.png)|![Devuan](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-devuan.png)|
|**Debian**|**Deepin**|**Devuan**|
|![Elementary OS](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-elementary.png)|![Endeavour OS](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-endeavour.png)|![Fedora](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-fedora.png)|
|**Elementary OS**|**Endeavour OS**|**Fedora**|
|![FreeBSD](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-freebsd.png)|![Garuda](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-garuda.png)|![Gentoo](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-gentoo.png)|
|**FreeBSD**|**Garuda Linux**|**Gentoo Linux**|
|![Kali Linux](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-kali.png)|![KDE neon](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-kdeneon.png)|![Kubuntu](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-kubuntu.png)|
|**Kali Linux**|**KDE neon**|**Kubuntu**|
|![Linux](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-linux.png)|![Linux Lite](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-linuxlite.png)|![Linux Mint](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-linuxmint.png)|
|**Linux**|**Linux Lite**|**Linux Mint**|
|![Lubuntu](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-lubuntu.png)|![Manjaro](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-manjaro.png)|![MX Linux](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-mx.png)|
|**Lubuntu**|**Manjaro**|**MX Linux**|
|![OpenSUSE](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-opensuse.png)|![Parrot OS](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-parrot.png)|![Pentoo](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-pentoo.png)|
|**OpenSUSE**|**Parrot OS**|**Pentoo**|
|![PopOS](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-popos.png)|![Red Hat](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-redhat.png)|![Slackware](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-slackware.png)|
|**PopOS**|**Red Hat**|**Slackware**|
|![Solus](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-solus.png)|![Sparky](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-sparky.png)|![SteamOS](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-steamos.png)|
|**Solus**|**Sparky Linux**|**SteamOS**|
|![Ubuntu](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-ubuntu.png)|![Mate](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-ubuntumate.png)|![Void](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-voidlinux.png)|
|**Ubuntu**|**Ubuntu Mate**|**Void Linux**|
|![Windows](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-windows10.png)|![Windows](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-windows11.png)|![Zorin](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-zorin.png)|
|**Windows 10**|**Windows 11**|**Zorin OS**|
|![NixOS](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-nixos.png)|![GuixSD](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-guixsd.png)|![DTOS](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-dtos.png)|
|**NixOS**|**GuixSD**|**DTOS**|
|![Xubuntu](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-xubuntu.png)|![PLACEHOLDER](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-nobara.png)|![PLACEHOLDER](https://raw.githubusercontent.com/VandalByte/darkmatter-grub2-theme/main/media/previews/preview-arcolinux.png)|
|**Xubuntu**|**Nobara**|**ArcoLinux**|
