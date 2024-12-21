# voidlinux-kernel-zen-6.12.6
Kernel 6.12.6 with patch zen , template for VoidLinux


This repository contains the xsrc folder necesary to build the linux 6.12.6-zen and linux6.12.6-zen-headers, as well the template to install kernel 6.12.6 an the path for it from zen-kernel repository.


## NOTE

If you **ONLY** want to use the template you need to download the patch from zen repository (https://github.com/zen-kernel/zen-kernel/releases/tag/v6.12.6-zen1) , place it in the patches folder and create the symbolic link linux6.12.6-zen-headers.
```bash
Linux6.12.6-zen
├── files
│   ├── arm64-dotconfig
│   ├── currentx86_64-dotconfig
│   ├── i386-dotconfig
│   ├── mv-debug
│   └── x86_64-dotconfig
├── patches
│   ├── fix-musl-btf-ids.patch
│   ├── fix-musl-objtool.patch
│   ├── fixdep-largefile.patch
│   ├── linux-v6.12.6-zen1.patch
│   └── x13s-camera.patch
└── template```

![image2](/assets/images/image2.png)
![image2](https://github.com/user-attachments/assets/ed17184b-294b-40c8-8be1-1d9fdce435a5)
