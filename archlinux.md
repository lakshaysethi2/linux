arch mirrorlist 
```
curl -sSL "https://archlinux.org/mirrorlist/?country=AU&country=NZ&protocol=https&use_mirror_status=on" | sed -e 's/^#Server/Server/' | sudo tee /etc/pacman.d/mirrorlist
```
install nvidia driver , nvidia-smi , cuda as dep for stuff
```
pacman -S nvidia-open  nvidia-utils cuda
```

make sudo user , one liner 
```
useradd -m -s /bin/bash username && passwd username && usermod -aG wheel username
```

install yay 

```
sudo pacman -S --needed git base-devel && git clone https://aur.archlinux.org/yay-bin.git && cd yay-bin && makepkg -si
```
