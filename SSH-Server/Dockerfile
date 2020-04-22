FROM sickp/alpine-sshd
# Set correct environment variables
ENV HOME /root
# Configure user nobody to match unRAID's settings

RUN apk update &&\
    apk add shadow inotify-tools rsync && \
    usermod -u 99 nobody && \
    usermod -g 100 nobody && \
    usermod -d /home nobody && \
    chown -R nobody:users /home && \
    passwd -d root
COPY alpine.pub /root/.ssh/authorized_keys
RUN "test -f /scripts/watchdog.sh" && { chmod +x /scripts/*.sh; /scripts/watchdog.sh; } || echo "no script in /scripts"
