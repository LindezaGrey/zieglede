# Building Customized OpenWRT Image for GL.iNet GL-AR750

First install buildtools

```
sudo apt-get install gcc binutils bzip2 flex python perl make grep unzip gawk subversion libz-dev
```

Run

```
./scripts/feeds update -a
```

to get all the latest package definitions
defined in feeds.conf / feeds.conf.default respectively
and

```
./scripts/feeds install -a
```

to install symlinks of all of them into
package/feeds/.

Use

```
make menuconfig
```

to configure your image.
If there are missing packages, install them.
Simply running
```
make
```
will build your firmware.