# android-public-build
A GitHub Action to build my APKs and sign them with my public build keystore

# APK Signing
Signing is done with my own [FOSS public key](https://github.com/tytydraco/public-keystore). Note that it is not a secure signature; this means that anyone can sign with this key. It is public so that my FOSS apps can be compiled with a FOSS key.

# Usage
`.github/workflows/build.yml`
```yml
name: Build

on:
  workflow_dispatch:
  push:

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v2
      - uses: tytydraco/android-public-build@main
        with:
            token: ${{ secrets.GITHUB_TOKEN }}
```
