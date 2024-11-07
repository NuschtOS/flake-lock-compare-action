# flake.lock compare action

This action can be used to help reviewing input changes in `flake.lock` files.

It functions by comparing the changed `flake.lock` file with the previous version
and using these information to post a continuously updated comment with compare links.

## Example usage

```yaml
name: Post compare link when flake.lock changes

permissions:
  issues: write
  pull-requests: write

on:
  pull_request:
    paths: ['flake.lock']

jobs:
  post-compare-link:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
        with:
          fetch-depth: 0
      - uses: NuschtOS/flake-lock-compare-action@main
```
