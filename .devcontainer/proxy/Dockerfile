FROM nginx:latest

RUN apt update && \
  apt -yV autoremove && apt autoclean
RUN ln -sf /usr/share/zoneinfo/Asia/Tokyo /etc/localtime && \
  { \
    echo 'export PS1="\[\e[0;36m\][\u@\h \W]\\$ \[\e[m\]"'; \
  } >> "$HOME/.bashrc"

COPY nginx.conf /etc/nginx/nginx.conf
