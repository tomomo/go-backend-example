FROM mariadb:10.9

RUN apt update && apt install -y \
  vim nkf curl zip unzip \
  && \
  apt -yV autoremove && apt autoclean
RUN ln -sf /usr/share/zoneinfo/Asia/Tokyo /etc/localtime && \
  { \
    echo 'export PS1="\[\e[0;36m\][\u@\h \W]\\$ \[\e[m\]"'; \
  } >> "$HOME/.bashrc"

RUN { \
  echo '[mysqld]'; \
  echo 'character-set-server=utf8mb4'; \
  echo 'collation-server=utf8mb4_general_ci'; \
  echo '[client]'; \
  echo 'default-character-set=utf8mb4'; \
} >> /etc/mysql/conf.d/server.cnf
