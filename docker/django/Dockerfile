FROM registry.access.redhat.com/ubi8/python-39

ADD ./app . 
RUN pip install -r requirements.txt

USER root
RUN touch /var/log/django.log
# RUN chown 1001:0 /var/log/django.log
RUN chgrp -R 0 /var/log && \
    chmod -R g+rwX /var/log
USER 1001

ENTRYPOINT /bin/bash docker-entrypoint.sh
