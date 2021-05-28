# Configuration files for Halium 7.1
General configuration files necessary for builds.

## Usage
You must first download the repo ( or just wget each file ). Place the `samsung_j5xnlte` manifest in your Halium source and follow through the documentation.

## Manual Changes
For the build to succeed you must change a few things manually.

1. common.mk file in SettingsLib doesn't exist for some reason. You must download it.
```bash
cd frameworks/base/packages/SettingsLib/
wget https://raw.githubusercontent.com/ubuntu-j5xnlte/configuration/master/etc/common.mk
```
