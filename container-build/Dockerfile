# Use the httpd-parent image as base
FROM quay.io/redhattraining/httpd-parent

LABEL io.openshift.expose-service="8080:http" \
	io.k8s.description="A basic Apache HTTP Server child image, uses ONBUILD" \
	io.k8s.display-name="Apache HTTP Server" \
	io.openshift.tags="apache, httpd"


RUN sed -i "s/Listen 80/Listen 8080/g" /etc/httpd/conf/httpd.conf


# This stuff is needed to ensure a clean start
RUN chgrp -R 0 	/var/log/httpd /var/run/httpd && \
	chmod -R 770 /var/log/httpd /var/run/httpd

#rm -rf /run/httpd && mkdir /run/httpd

# Run as the root user
USER 1001

