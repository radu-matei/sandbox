LinuxKit on Azure
=================

What is this?
--------------
The goal of this repo is to get you started in running your custom, minimal and immutable Linux distribution on Azure. It is pretty much work in progress (or just started, whichever you want) and is not an official Microsoft or LinuxKit repository.

Here I will also be documenting my journey to getting started with LinuxKit and issues along the way. [You can find some things I learned the hard way Here.](docs/misc.md)

More specifically...
---------------------

In the end I want to build a great experience for creating and running your custom Linux distros in Azure. Below is a task-like list of things I will be doing in the following days:

- ~~get a basic LinuxKit distro (SSH server) running on a Mac~~

- manually creating the image and creating an Azure VM using `az`:
  - convert the image to .vhd
  - upload the image to Azure Storage
  - create a VM based on this image

- integrate this with the LinukKit tooling and the Azure Go SDK



Contributing
------------
If you want to contribute in any way: from writing the Go tooling all the way to documenting the efforts, you are welcomed to do so. Any help is greatly appreciated. Simply submit pull requests and hack away!