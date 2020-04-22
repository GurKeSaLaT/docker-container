FROM sickp/alpine-sshd
RUN passwd -d root
COPY alpine.pub /root/.ssh/authorized_keys
RUN chmod +x /scripts/watchdog.sh
RUN /scripts/watchdog.sh