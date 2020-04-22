FROM sickp/alpine-sshd
# Set correct environment variables
ENV HOME /root
# Configure user nobody to match unRAID's settings
RUN apk --no-cache add shadow
RUN usermod -u 99 nobody
RUN usermod -g 100 nobody
RUN usermod -d /home nobody
RUN chown -R nobody:users /home
RUN passwd -d root
COPY alpine.pub /root/.ssh/authorized_keys
RUN test -f /scripts/watchdog.sh && { chmod +x /scripts/watchdog.sh; /scripts/watchdog.sh; }
