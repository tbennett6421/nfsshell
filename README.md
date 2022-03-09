nfsshell
========

NFS shell that provides user level access to an NFS server, over UDP or TCP,
supports source routing and "secure" (privileged port) mounts. It's a
useful tool to manually check (or show) security problems after a security
scanner has detected them.

Originally released by Leendert van Doorn, updated to support NFSv3 by Michael Brown

# addendum
This takes a bit of work to compile in modern systems

## fixing compilation issues
You can search for the existing header files on your system

```sh
locate readline.h
locate rpc.h
```

if you have them, you can simply update the `Makefile`

Otherwise, ask apt
```sh
sudo apt-get update
sudo apt-get install apt-file -y
sudo apt-file update
apt-file search readline/readline.h

apt-file search readline/readline.h
apt-file search rpc/rpc.h

sudo apt-get install libtirpc-dev
sudo apt-get install libreadline-dev
```

After fixing the `Makefile`

```sh
make clean
make
./nfsshell
```
