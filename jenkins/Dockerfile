FROM jenkins/jenkins:lts

RUN cp /etc/hosts /tmp/hosts
RUN mkdir -p -- /lib-override && cp /lib/x86_64-linux-gnu/libnss_files.so.2 /lib-override
RUN sed -i 's:/etc/hosts:/tmp/hosts:g' /lib-override/libnss_files.so.2
ENV LD_LIBRARY_PATH /lib-override
RUN echo "10.129.142.9	gitlab.saicstack.com" >> /tmp/hosts \
    && echo "10.133.99.240 registry.nj-prod-dce.saicstack.com" >> /tmp/hosts