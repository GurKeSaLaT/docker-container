FROM sickp/alpine-sshd
# Set correct environment variables
ENV HOME /root
# Configure user nobody to match unRAID's settings
RUN usermod -u 99 nobody
RUN usermod -g 100 nobody
RUN usermod -d /home nobody
RUN chown -R nobody:users /home
RUN passwd -d root
COPY alpine.pub /root/.ssh/authorized_keys
RUN chmod +x /scripts/watchdog.sh
RUN /scripts/watchdog.sh