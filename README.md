[![Python application test with Github Actions](https://github.com/ChitraAiren/pytest-tips-tricks/actions/workflows/testing-ci.yml/badge.svg)](https://github.com/ChitraAiren/pytest-tips-tricks/actions/workflows/testing-ci.yml)

# pytest-tips-tricks
A primer on pytest


# Older testing-ci.yml
name: Python application test with Github Actions

on: [push]

jobs:
  build:

    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v2
    - name: Set up Python 3.10
      uses: actions/setup-python@v1
      with:
        python-version: 3.10.13
    - name: Install dependencies
      run: |
        make install
    - name: Lint with pylint
      run: |
        make lint
    - name: Test with pytest
      run: |
        make test
    - name: Format code
      run: |
        make format

