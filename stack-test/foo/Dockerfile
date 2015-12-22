FROM 0d3ddec4b8b3

USER root
RUN mkdir -p /home/stack/bin
RUN cp /root/.local/bin/stack /home/stack/bin/
RUN chown -R stack /home/stack/bin/

USER stack
ENV PATH "/home/stack/bin/:$PATH"

