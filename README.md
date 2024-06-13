# Push to Gitlab Server

This GitHub action pushes changes from a GitHub repository to a GitLab server.

## Usage

Add the following to your workflow file:

```yml
name: push alert

on: [push, create]

jobs:
  push:
    name: Push to Github
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
        with:
          fetch-depth: 0
    - uses: saderi/push-to-gitlab@v1
        with:
            gitlab_repository: '<your-gitlab-repository-url>' # do not include https://
            gitlab_token: ${{ secrets.GITLAB_TOKEN }}
```
