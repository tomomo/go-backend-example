FROM golang:1-bullseye

RUN apt update && apt install -y \
  git git-lfs \
  zip unzip \
  && \
  apt -yV autoremove && apt autoclean
RUN ln -sf /usr/share/zoneinfo/Asia/Tokyo /etc/localtime && \
  { \
    echo 'export PS1="\[\e[0;36m\][\u@\h \W]\\$ \[\e[m\]"'; \
  } >> "$HOME/.bashrc"

RUN \
  go install golang.org/x/tools/cmd/goimports@latest && \
  go install golang.org/x/tools/gopls@latest && \
  go install github.com/stamblerre/gocode@latest && \
  # NOTE: for VSCode
  go install github.com/ramya-rao-a/go-outline@latest

RUN go install github.com/cosmtrek/air@latest

WORKDIR /go/src
