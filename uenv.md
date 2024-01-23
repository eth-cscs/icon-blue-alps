# User Environments

The first step on all vClusters is to install the `uenv` CLI tools.

```bash
git clone git@github.com:eth-cscs/uenv.git && ./uenv/install
```

For slightly more information, see the uenv [online does](https://eth-cscs.github.io/uenv/).

## Vial

On vial we have two environments:

* v1:
    * includes eccodes
* v2:
    * no eccodes
    * boost 1.68

They can be loaded as follows:

```bash
# for v1
uenv start /capstor/scratch/cscs/bcumming/images/blue-v1.squashfs

# for v2
uenv start /capstor/scratch/cscs/bcumming/images/blue-v2.squashfs
```

Once started, you can double check that you are in a uenv session:

```bash
uenv status
```

The simplest way to proceed from there is to load an environment view:

```bash
uenv view default
```

You can check that PATH has been set, and the correct versions of tools are being picked up:

```
┌ vial:nid001048 /capstor/scratch/cscs/bcumming/images
└── which cmake
/user-environment/env/default/bin/cmake
┌ vial:nid001048 /capstor/scratch/cscs/bcumming/images
└── python --version
Python 3.10.12
```

The root path for all the software, for passing into the ICON configure script, is just `/user-environment/env/default`.
