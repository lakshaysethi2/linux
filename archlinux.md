make sudo user , one liner 
```
useradd -m -s /bin/bash username && passwd username && usermod -aG wheel username
```

install yay 

```
sudo pacman -S --needed git base-devel && git clone https://aur.archlinux.org/yay-bin.git && cd yay-bin && makepkg -si
```
