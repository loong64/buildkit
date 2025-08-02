# BuildKit <!-- omit in toc -->

[![GitHub Release](https://img.shields.io/github/release/moby/buildkit.svg?style=flat-square)](https://github.com/moby/buildkit/releases/latest)
[![PkgGoDev](https://img.shields.io/badge/go.dev-docs-007d9c?style=flat-square&logo=go&logoColor=white)](https://pkg.go.dev/github.com/moby/buildkit/client/llb)
[![CI BuildKit Status](https://img.shields.io/github/actions/workflow/status/moby/buildkit/buildkit.yml?label=buildkit&logo=github&style=flat-square)](https://github.com/moby/buildkit/actions?query=workflow%3Abuildkit)
[![CI Frontend Status](https://img.shields.io/github/actions/workflow/status/moby/buildkit/frontend.yml?label=frontend&logo=github&style=flat-square)](https://github.com/moby/buildkit/actions?query=workflow%3Afrontend)
[![Go Report Card](https://goreportcard.com/badge/github.com/moby/buildkit?style=flat-square)](https://goreportcard.com/report/github.com/moby/buildkit)
[![Codecov](https://img.shields.io/codecov/c/github/moby/buildkit?logo=codecov&style=flat-square)](https://codecov.io/gh/moby/buildkit)

BuildKit is a toolkit for converting source code to build artifacts in an efficient, expressive and repeatable manner.

Key features:

-   Automatic garbage collection
-   Extendable frontend formats
-   Concurrent dependency resolution
-   Efficient instruction caching
-   Build cache import/export
-   Nested build job invocations
-   Distributable workers
-   Multiple output formats
-   Pluggable architecture
-   Execution without root privileges

Read the proposal from https://github.com/moby/moby/issues/32925

Introductory blog post https://blog.mobyproject.org/introducing-buildkit-17e056cc5317

Join `#buildkit` channel on [Docker Community Slack](https://dockr.ly/comm-slack)

> [!NOTE]
> If you are visiting this repo for the usage of BuildKit-only Dockerfile features
> like `RUN --mount=type=(bind|cache|tmpfs|secret|ssh)`, please refer to the
> [Dockerfile reference](https://docs.docker.com/engine/reference/builder/).

> [!NOTE]
> `docker build` [uses Buildx and BuildKit by default](https://docs.docker.com/build/architecture/) since Docker Engine 23.0.
> You don't need to read this document unless you want to use the full-featured
> standalone version of BuildKit.

## Quick start

```sh
docker run --privileged --rm ghcr.io/loong64/tonistiigi/binfmt --install all
docker buildx create --use --name mybuild --driver-opt image=ghcr.io/loong64/moby/buildkit:buildx-stable-1
docker buildx inspect --bootstrap --builder mybuild
```
