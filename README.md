Sample usage:

```
name: Build and Push

on:
  push:
    branches:
      - staging
      - production

jobs:
  build-deploy:
    uses: bitbool-actions/workflows-docker/.github/workflows/build-deploy-dcd.yml@main
    permissions:
      contents: read
    with:
      DOCKER_USER: "<docker_user>"
      DOCKER_REPO: "<docker_user>/<repo_name>"
      DOCKER_REGISTRY: "<docker registry>"
    secrets:
      DOCKER_PASSWORD: ${{ secrets.DOCKER_PASSWORD }}
      AUTH_TOKEN: ${{ secrets.AUTH_TOKEN }}
      # AUTH_TOKEN: ${{ secrets[format('AUTH_TOKEN_{0}', github.ref_name)] }}
```