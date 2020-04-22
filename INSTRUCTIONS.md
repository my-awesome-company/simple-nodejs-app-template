

# CodeQL Action

```
name: "CodeQL analysis"

on: [push]

jobs:
  build:

    strategy:
      fail-fast: false

    runs-on: ubuntu-latest # you can try windows too but macos is not yet supported

    steps:
    - uses: actions/checkout@v1
    - uses: Anthophila/codeql-action/codeql/init@master
      with:
        languages: javascript # comma separated list of values from {go, python, javascript, java, cpp, csharp} (not YET ruby, sorry!)
    - uses: Anthophila/codeql-action/codeql/finish@master
    - uses: Anthophila/codeql-action/codeql/upload-sarif@master
      env:
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }} 

```
