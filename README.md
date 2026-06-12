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

## Usage

Create `.github/workflows/your-check.yml` with the following:

```yaml
name: Your Check
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

### Skipping specific commits

You can skip specific commits by setting `filter_out_pattern`:

```yaml
    - name: Get PR Commits
      id: 'get-pr-commits'
      uses: actionshub/get-pr-commits@main
      with:
        token: ${{ secrets.GITHUB_TOKEN }}
        filter_out_pattern: '[[skip_dco_check]]'
```

This will skip any commits with `[[skip_dco_check]]` in the commit message. You
can further tweak the behavior of this with `filter_out_flags`, which sets the
regex flags on the match.

## History

This is a fork of
[tim-actions/get-pr-commits](https://github.com/tim-actions/get-pr-commits),
which is no longer maintained.
