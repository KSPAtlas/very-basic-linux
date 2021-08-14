# very-basic-linux
A Linux distribution with the intent of being able to fit everything into the bzImage.

# Compilation
This one is a bit complicated.

1) Acquire a copy of the Linux kernel source code. 
2) Edit the provided .config file to set CONFIG_INITRAMFS_SOURCE to where the folder "root" from the repo is located.
3) Copy said .config file into the root of the Linux source directory.
4) Build the kernel with `make`.
5) The finished image will be found at `<KERNEL SOURCE DIR>/arch/x86/boot/bzImage`.

# How to use
THIS IS NOT A DISK IMAGE. You cannot boot it directly. Instead, use a bootloader to load it. No kernel parameters are necessary (But can be used). You can, however,
boot with QEMU using `qemu-system-x86_64 -kernel <PATH_TO_BZIMAGE> <EXTRA_QEMU_PARAMS>`.
