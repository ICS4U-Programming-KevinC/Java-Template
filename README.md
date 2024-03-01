# Java-Template
---
###############################################
# Run GitHub's Super Linter against code base #
###############################################

name: "KRevin's Super Linter"

on:
  push:
  pull_request:

jobs:
  run-linters:
    name: "KRevin's Super Linter"
    runs-on: ubuntu-latest

    steps:
      - name: "Check out Git repository"
        uses: actions/checkout@master
      
      - name: "Run GitHub Super Linter"
        uses: github/super-linter@main
        env:
          VALIDATE_ALL_CODEBASE: true
          VALIDATE_JAVASCRIPT_STANDARD: false
          VALIDATE_CLANG_FORMAT: false
          DEFAULT_BRANCH: main
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
