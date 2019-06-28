# conda related tips

## Evironment

* Disable Base auto activation

```bash
conda config --set auto_activate_base false
```

* Create an environment

```bash
conda create -n <env_name>
```

## Channels

* Show channels

```bash
conda config --show channels
```

* Add the conda-forge channel

```bash
conda config --add channels conda-forge
```

* Set channel priority

Adding a channel will not remove any previous channels. Instead, it will
become the first channel that conda looks to find packages. Currently,
if it cannot find a package in conda-forge, it will then look in defaults
for it. But, if the same package exists in both, then it will choose
to install it from the channel with the newest version. For instance,
if conda-forge has pandas version 0.23 and the defaults has version 0.24
then conda will install pandas 0.24 from the defaults channel.
This behavior is unintuitive to me and it makes more sense to always
use the channel that appears first in the channels list regardless
of the version.

Conda gives us a way to change this with the following command:

```bash
conda config --set channel_priority strict
```
