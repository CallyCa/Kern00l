# My First Kernel
=======

#### Build commands ####
```
nasm -f elf32 kernel.asm -o kasm.o
```

compile with the `-fno-stack-protector` option:
```
gcc -fno-stack-protector -m32 -c kernel.c -o bin/kc.o
```

#### Test on emulator ####
```
qemu-system-i386 -kernel kernel
```

#### Get to boot ####
GRUB requires your kernel executable to be of the pattern `kernel-<version>`.

So, rename the kernel:

```
mv kernel kernel-701
```

Copy it to your boot partition (assuming you are superuser):

```
cp kernel-701 /boot/kernel-701
```