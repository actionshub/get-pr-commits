# get-pr-commits

[![Build](
https://github.com/actionshub/get-pr-commits/actions/workflows/build.yaml/badge.svg
)](https://github.com/actionshub/get-pr-commits/actions/workflows/build.yaml)
[![CodeQL](
https://github.com/actionshub/get-pr-commits/actions/workflows/codeql.yml/badge.svg
)](https://github.com/actionshub/get-pr-commits/actions/workflows/codeql.yml)
[![Lint](
https://github.com/actionshub/get-pr-commits/actions/workflows/lint.yaml/badge.svg
)](https://github.com/actionshub/get-pr-commits/actions/workflows/lint.yaml)

A GitHub Action that get commits in current pull-request

*NOTE*: This is a fork of
[tim-actions/get-pr-commits](https://github.com/tim-actions/get-pr-commits),
which is no longer maintained.

## Usage

Add .github/workflows/sanity-check.yml with the following:

```yaml
name: Sanity check
on: [pull_request]

jobs:
  commits_check_job:
    runs-on: ubuntu-latest
    name: Commits Check
    steps:
    - name: Get PR Commits
      id: 'get-pr-commits'
      uses: actionshub/get-pr-commits@main
      with:
        token: ${{ secrets.GITHUB_TOKEN }}

```
