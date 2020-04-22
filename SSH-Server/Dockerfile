FROM sickp/alpine-sshd
# Set correct environment variables
ENV HOME /root
# Configure user nobody to match unRAID's settings
RUN \
    usermod -u 99 nobody && \
    usermod -g 100 nobody && \
    usermod -d /home nobody && \
    chown -R nobody:users /home && \
    passwd -d root
COPY alpine.pub /root/.ssh/authorized_keys
RUN chmod +x /scripts/watchdog.sh
RUN /scripts/watchdog.sh