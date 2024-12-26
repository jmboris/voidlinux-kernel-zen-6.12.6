# How to Install

> [!NOTE]
> This document is for the cloning repository method , if you only want to use the template is because you are a more experinced user so you dont need this instructions.





1. To install any package of the "XBPS source packages collection" you need to have installed the void-packages git repository ,  this process have to be done only once , if you have already done it , skip it and continue in the next step.


you can choose any folder where you want to keep the repository. I choose  ~/.local/share/pkgs so:

```
mkdir -p ~/.local/share/pkgs
```

Then , clone the void-packages git repository

```
$ git clone https://github.com/void-linux/void-packages.git
$ cd void-packages
$ ./xbps-src binary-bootstrap
```

You can read more abou this in the Official github of Void Linux https://github.com/void-linux/void-packages


2. Go to your Downloads folder and clone this linux zen repository.

```
$ cd ~/Downloads
$ git clone https://github.com/jmboris/voidlinux-kernel-zen-6.12.6.git
$ cd voidlinux-kernel-zen-6.12.6/linux6.12.6-zen/
```

then we need to copy the folder linux6.12.6-zen to the void-packages repository.

cp -r linux6.12.6-zen <location_of_your_void_pacakeges>/srcpkgs/linux6.12.6-zen

in my case:
```
$ cp -r linux6.12.6-zen/ ../../../.local/share/pkgs/void-packages/srcpkgs/
```

3. Go to where the void-packages is located. In my case ~/.local/share/pkgs/void-packages
```
$ cd ~/.local/share/pkgs/void-packages
```

4. Because we want to compile a kernel , we need the linux headers too , so we create a symbolic link fo them.The template to create the kernel needs it.
```
$ ln -s srcpkgs/linux6.12.6-zen srcpkgs/linux6.12.6-zen-headers
```

5. Build the kernel
```
$ ./xbps-src pkg linux6.12.6-zen
```
During this process the zen patch will ask you a few questions about configurations you want to use ... you must choose what you want/need.


6. When it is compiled without errors , you can install the kernel and the headers
```
# xbps-install --repository hostdir/binpkgs linux6.12.6-zen linux6.12.6-zen-headers
```

Alternatively, packages can be installed with the xi utility, from the xtools package. xi takes the repository of the current working directory into account.
```
$ xi linux6.12.6-zen linux6.12.6-zen-headers
```
