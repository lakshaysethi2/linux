arch ISO space ram 
```
mount -o remount,size=28G /run/archiso/cowspace
```


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
useradd -m -s /bin/bash username && echo "username:1234" | chpasswd && echo "username ALL=(ALL) ALL" > /etc/sudoers.d/username
```

install yay 

```
sudo pacman -S --needed git base-devel && git clone https://aur.archlinux.org/yay-bin.git && cd yay-bin && makepkg -si
```


touch pad fix 
```
sudo pacman -S xorg-xinput
```
```
xinput set-prop "$(xinput list --id-only "$(xinput list | grep -i touchpad | head -n1 | sed 's/.*↳ //;s/[[:space:]]\+id=.*//')")" "libinput Tapping Enabled" 1
```
above is basically touchpad id extract eg 12: 
```
xinput set-prop 12 "libinput Tapping Enabled" 1
```
with output if 12 from
```
xinput list
```

