# android-public-build
A GitHub Action to build my APKs and sign them with my public build keystore

# Usage
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
