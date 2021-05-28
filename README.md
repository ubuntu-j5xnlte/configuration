# Configuration files for Halium 7.1
General configuration files necessary for builds.

## Usage
You must first download the repo ( or just wget each file ). Place the `samsung_j5xnlte` manifest in your Halium source and follow through the documentation.

## Build
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
3. `vendor/samsung/j5xnlte/j5xnlte-vendor.mk` has some dependencies not fufilled, if you find the files necessary you might place it in the `propriatery/` folder, for now it should be safe the remove the referances.
```bash
cd vendor/samsung/j5xnlte
rm j5xnlte-vendor.mk
wget https://raw.githubusercontent.com/ubuntu-j5xnlte/configuration/master/etc/j5xnlte-vendor.mk
```
4. Same problem occurs for `msm8916-common`. Same solution applies.
```bash
cd vendor/samsung/msm8916-common
rm msm8916-common-vendor.mk
wget https://raw.githubusercontent.com/ubuntu-j5xnlte/configuration/master/etc/msm8916-common-vendor.mk
```
