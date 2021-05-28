# Configuration files for Halium 7.1
General configuration files necessary for builds.

## Usage
You must first download the repo ( or just wget each file ). Place the `samsung_j5xnlte` manifest in your Halium source and follow through the documentation.

## Build
For the build to succeed you must change a few things manually.

1. Get the manifest file in `halium/devices/manifests`.
```
cd halium/devices/manifests
wget https://raw.githubusercontent.com/ubuntu-j5xnlte/configuration/master/samsung_j5xnlte.xml
```
2. Sync by using `./halium/devices/setup j5xnlte`

3. Build uses Python2.7, best way to do this is using `virtualenv` but if you are lazy.
```bash
sudo rm /usr/bin/python
ln -s /usr/bin/python2.7 ~/.local/bin/python

# To change it back.
rm ~/.local/bin/python
ln -s /usr/bin/python3 ~/.local/bin/python
```

4. common.mk file in SettingsLib doesn't exist for some reason. You must download it.
```bash
cd frameworks/base/packages/SettingsLib/
wget https://raw.githubusercontent.com/ubuntu-j5xnlte/configuration/master/etc/common.mk
```
5. `vendor/samsung/j5xnlte/j5xnlte-vendor.mk` has some dependencies not fufilled, if you find the files necessary you can place them in the `propriatery/` folder, for now it should be safe the remove the references.
```bash
cd vendor/samsung/
rm -rf j5-common
cd j5xnlte
rm j5xnlte-vendor.mk
wget https://raw.githubusercontent.com/ubuntu-j5xnlte/configuration/master/etc/j5xnlte-vendor.mk
```
6. Same problem occurs for `msm8916-common`. Same solution applies.
```bash
cd vendor/samsung/msm8916-common
rm msm8916-common-vendor.mk
wget https://raw.githubusercontent.com/ubuntu-j5xnlte/configuration/master/etc/msm8916-common-vendor.mk
```
7. Supplied arguments in `hardware/qcom/audio-caf/msm8916/hal/audio_extn/audio_extn.c` and `hardware/qcom/audio-caf/msm8916/hal/msm8916/platform.c` does not match the argument types needed. Small fix is to change `%ld` to `%d`.
```bash

```

