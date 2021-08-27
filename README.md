# actions-gh-pr-create

This is a composite GitHub Actions for my projects; it's responsible for running gh-pr-create(1).


```yaml
on:
  push:
    branches:
      - main
jobs:
  pr:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - run: |
          DO SOMETHING
      - uses: yykamei/actions-git-push@main
        with:
          commit-message: DO SOMETHING
          branch: do-something
      - uses: yykamei/actions-gh-pr-create@main
        with:
          token: ${{ secrets.GITHUB_TOKEN }}
          branch: do-something
          title: TITLE FOR THE PR
          body: |
            YOUR NICE DESCRIPTION!

            - [x] OK
            - [ ] 😎
```
