# Simple Docker build and publish action

```yml
name: Build and publish Docker image

on:
  push:
    branches:
      - master

jobs:
  test:
    name: Checkout, build and push
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Build and push
        uses: einsenundnullen/build-action@master
        with:
          docker-user: ${{ github.repository_owner }}
          docker-password: ${{ secrets.GITHUB_TOKEN }}
          docker-image-name: test-service
          working-directory: ./optional-working-directory
```
