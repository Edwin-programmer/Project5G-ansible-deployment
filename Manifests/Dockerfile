FROM golang:1.12.9

WORKDIR /root/

RUN apt update -y
RUN apt -y install wget git

WORKDIR $GOPATH/src
RUN git clone https://github.com/zhujq/free5gc-stage-3.git free5gc

WORKDIR $GOPATH/src/free5gc
RUN chmod +x ./install_env.sh
RUN ./install_env.sh
RUN tar -C $GOPATH -zxvf free5gc_libs.tar.gz
RUN go build -o bin/amf -x src/amf/amf.go
RUN go build -o bin/ausf -x src/ausf/ausf.go
RUN go build -o bin/nrf -x src/nrf/nrf.go
RUN go build -o bin/nssf -x src/nssf/nssf.go
RUN go build -o bin/pcf -x src/pcf/pcf.go
RUN go build -o bin/smf -x src/smf/smf.go
RUN go build -o bin/udm -x src/udm/udm.go
RUN go build -o bin/udr -x src/udr/udr.go
