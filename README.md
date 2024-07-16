# desafiofullcycledocker

Codigo Fonte em GO: fullcyclerock.go

```
package main

import "fmt"

func main() {
 fmt.Println("Full Cycle Rocks")
}
```

**Imagem 1**: Criamos uma imagem BASE, contendo a linguagem golang: 

FROM golang:1.21

WORKDIR /usr/src/golang

COPY fullcyclerock.go .

RUN go mod init github.com/horaciovasconcellos/desafiofullcycledocker && \
    go mod tidy && \
    go build fullcyclerock.go

CMD [ "./fullcyclerock" ]

