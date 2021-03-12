FROM ubuntu:21.04

RUN apt-get update && \
    apt-get -y install golang git libz3-dev && \
    cd  && \
    git clone https://github.com/system-pclub/GCatch.git

RUN cd ~/GCatch && \
    git checkout 8ea5eeac7219a581f656836d7ab22075d52d6312 && \
    rm GCatch/tools/go/go.* && \
    cd GCatch && \
    go mod init github.com/system-pclub/GCatch/GCatch && \
    go get github.com/aclements/go-z3@v0.0.0-20170612131502-18129d7fc687 && \
    echo "replace git.gradebot.org/zxl381/goconcurrencychecker/tools/github.com/aclements/go-z3/z3 => github.com/aclements/go-z3 v0.0.0-20170612131502-18129d7fc687" >> go.mod && \
    cd cmd/GCatch && \
    go get && \
    go build