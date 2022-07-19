# protoc-gen-connect-go-mux

protoc-gen-connect-go-mux is a plugin for the Protobuf compiler that generates
Go code. To use it, build this program and make it available on your PATH as
protoc-gen-connect-go-mux.

The `connect-go-mux` suffix becomes part of the arguments for the Protobuf
compiler. To generate the base Go types and Connect code using protoc:

```bash
protoc --go_out=gen --connect-go-mux_out=gen path/to/file.proto
```

With buf, your buf.gen.yaml will look like this:

```yaml
  version: v1
  plugins:
    name: go
    out: gen
    name: connect-go-mux
    out: gen
```

This generates helper for registering services with [gorilla.Mux](https://github.com/gorilla/mux).
