# desafiofullcycledocker

Codigo Fonte em GO: fullcyclerock.go

```
package main

import "fmt"

func main() {
 fmt.Println("Full Cycle Rocks")
}
```

**Imagem 1**: Criamos uma imagem BASE, contendo a linguagem golang: `Dockerfile.um`

```
FROM golang:1.21

WORKDIR /usr/src/golang

COPY fullcyclerock.go .

RUN go mod init github.com/horaciovasconcellos/desafiofullcycledocker && \
    go mod tidy && \
    go build fullcyclerock.go

CMD [ "./fullcyclerock" ]
```

*  `docker build -t hctvjr/go . -f Dockerfile.um`

```
REPOSITORY               TAG       IMAGE ID       CREATED         SIZE
hctvjr/go                latest    ee39e77cd0f8   2 minutes ago   849MB
```

* `docker run hctvjr/go`

```
Full Cycle Rocks
```

