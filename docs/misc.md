Things I learned the hard way
=============================


1. Make sure you are on the Edge channel of Docker - at least in Docker for Mac
--------------------------------------------------------------------------------

If you are not on the Edge channel you can surely build `moby` and `linuxkit`, but things will silently and very subtly fail. For example, when I tried to run the simple SSH example from the docs of LinuxKit, everything would go fine: `moby` would build the image and `linuxkit` would start a VM, even busybox would work. But the networking was really weierd. It was not picking up any IP address sometimes, other times it would fail while running.

**Make sure you are on the Edge channel of Docker before you start playing around with LinuxKit!** That unless you want to spend 3-4 hours trying to figure out what is wrong.
