# a527-bullseye-test

[![Update packages](https://github.com/radxa-repo/a527-bullseye-test/actions/workflows/update.yaml/badge.svg)](https://github.com/radxa-repo/a527-bullseye-test/actions/workflows/update.yaml)

## Content

* [Published GitHub Releases](https://radxa-repo.github.io/a527-bullseye-test/pkgs.json)
* [File index](https://radxa-repo.github.io/a527-bullseye-test/files.list)

## Report issues

The issue list for this repository should be strictly related to the package repository service itself.  
If your issue is related to a specific package's usage, you should file issues under package's repository over at [`radxa-pkg`](https://github.com/radxa-pkg).

## Usage

```bash
# Install signing keyring
keyring="$(mktemp)"
version="$(curl -L https://github.com/radxa-pkg/radxa-archive-keyring/releases/latest/download/VERSION)"
curl -L --output "$keyring" "https://github.com/radxa-pkg/radxa-archive-keyring/releases/latest/download/radxa-archive-keyring_${version}_all.deb"
sudo dpkg -i "$keyring"
rm -f "$keyring"
# Add apt package repo
sudo tee /etc/apt/sources.list.d/70-radxa.list <<< "deb [signed-by=/usr/share/keyrings/radxa-archive-keyring.gpg] https://radxa-repo.github.io/a527-bullseye-test/ a527-bullseye-test main"
sudo apt-get update
```
