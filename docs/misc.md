Things I learned the hard way
=============================


1. Make sure you are on the Edge channel of Docker - at least in Docker for Mac
--------------------------------------------------------------------------------

If you are not on the Edge channel you can surely build `moby` and `linuxkit`, but things will silently and very subtly fail. For example, when I tried to run the simple SSH example from the docs of LinuxKit, everything would go fine: `moby` would build the image and `linuxkit` would start a VM, even busybox would work. But the networking was really weierd. It was not picking up any IP address sometimes, other times it would fail while running.

**Make sure you are on the Edge channel of Docker before you start playing around with LinuxKit!** That unless you want to spend 3-4 hours trying to figure out what is wrong.


2. As of this moment, creating a .vhd file as output doesn't work
------------------------------------------------------------------

I opened an [issue on the LinuxKit repo](https://github.com/linuxkit/linuxkit/issues/1836), but as of right now I was unable to build an image as .vhd with `moby build`.
So if you want to have a .vhd, you need to convert it using `qemu-img`:

```
qemu-img convert -f raw -O vpc -o subformat=fixed,force_size your-image.iso disk.vhd
```

3. Run the .vhd locally using `qemu`
------------------------------------

After you output a .vhd imag, you might want to test if it actually boots up. Now, the simplest way - without any networking, or opening any ports - is using qemu:

```
qemu-system-x86_64 disk.vhd -nographic
``

This way you should see the output from the VM you just created.
