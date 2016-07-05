# Golang Docker Image

This docker image encapsulates the entire golang runtime for use in
developing Go applications.

## Getting Started

Run it with the following command:

```
docker run \
  --rm \
  -v $(PWD):/go/src/PATH/TO/YOUR/PROJECT \
  -w /go/src/PATH/TO/YOUR/PROJECT \
  scottbrown/golang
```

The entrypoint is the `go` command, so you can put any arguments after
the image name and it will be run against that command.

