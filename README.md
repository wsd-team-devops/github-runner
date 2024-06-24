# GitHub Actions Runner

This branch is for solvians side self-hostes GitHub runner config setup, we have to use Dockerfile to build up our custom image

Runner version : 2.317.0
ImageOS: ubuntu22

Software installed:
1. Yarn
2. Nodejs
3. Git
4. Self-signed Solvians CA cert
5. buildah
6. podman
7. yq

Upgrade Process:
1. Upgrade arc controller
helm upgrade arc -n arc-systems oci://ghcr.io/actions/actions-runner-controller-charts/gha-runner-scale-set-controller
2. Upgrade arc runner
helm upgrade action-runner-dind -f dind.yaml oci://ghcr.io/actions/actions-runner-controller-charts/gha-runner-scale-set -n arc-runners

Runner releases:

![linux](docs/res/linux_sm.png)  [Pre-reqs](docs/start/envlinux.md) | [Download](https://github.com/actions/runner/releases)

