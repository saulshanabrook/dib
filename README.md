# `dib`

`dib` (Docker Image Builder) makes it easy to programmatically build public
Docker images, from Dockerfiles. It supports multiple backends
([Quay](https://quay.io/repository/) and [DockerHub](https://hub.docker.com/))
that all allow free creation of unlimited public images.

## Quickstart

```go
import (
  "fmt"

  "github.com/saulshanabrook/dib"
)

b := dib.NewQuayBuilder("username", "password")
i := dib.Image{
  Repository: "saulshanabrook",
  Name: "cool-stuff",
  Tag: "1.2",
  Dockerfile: "FROM alpine\nCMD echo cool-stuff"
}

err := b.Build(&i)
fmt.Println(err)
```