hola
holaa
hoojdjdjdj
d
d
d
d
d
ax

codi workflows

name: "Lint Markdown"

on:
  push:
    branches: ["main", "develop"]
  pull_request:
    branches: ["main", "develop"]

jobs:
  markdown-lint:
    runs-on: ubuntu-latest
    steps:
      - name: "Checkout"
        uses: actions/checkout@v4

      - name: "Run Markdownlint"
        uses: davidanson/markdownlint-cli2-action@v16
        with:
          config: '.markdownlint.json'
          globs: '**/*.md'