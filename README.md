# Configuration files for Halium 7.1
General configuration files necessary for builds.

## Usage
You must first download the repo ( or just wget each file ). Place the `samsung_j5xnlte` manifest in your Halium source and follow through the documentation.

## Manual Changes
For the build to succeed you must change a few things manually.

1. Build uses Python2.7, best way to do this is using `virtualenv` but if you are lazy.
```bash
sudo rm /usr/bin/python
ln -s /usr/bin/python2.7 ~/.local/bin/python

# To change it back.
rm ~/.local/bin/python
ln -s /usr/bin/python3 ~/.local/bin/python
```

2. common.mk file in SettingsLib doesn't exist for some reason. You must download it.
```bash
cd frameworks/base/packages/SettingsLib/
wget https://raw.githubusercontent.com/ubuntu-j5xnlte/configuration/master/etc/common.mk
```
## Notes For Self.
  1. j5-common appeared out of nowhere in the vendors. the missing propriatery libraries might be a problem.
