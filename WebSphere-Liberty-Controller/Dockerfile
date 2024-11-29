# Use the base image WebSphere Liberty
FROM websphere-liberty:latest

MAINTAINER robert.pesout@tietoevry.com

USER root

# Set the working directory
WORKDIR /tmp

# Copy necessary files
COPY entrypoint.sh /tmp

# Install collective controller and configure server
RUN apt-get update && apt-get install -y vim && \
    ./installUtility install collectivecontroller-1.0 --acceptLicense && \
    mkdir -p /.ssh && touch /.ssh/authorized_keys && \
    chmod 700 /.ssh && chmod 777 /.ssh/authorized_keys && \
    ./server create controller && \
    chmod +x /tmp/entrypoint.sh && chown 1001:0 /tmp/entrypoint.sh

# Copy server configuration
COPY --chown=1001:0 server.xml /opt/ibm/wlp/usr/servers/controller/

# Switch to non-root user
USER 1001

# Expose necessary ports
EXPOSE 9080 9443

# Set entrypoint
ENTRYPOINT ["/tmp/entrypoint.sh"]

# Start server
CMD ["/opt/ibm/wlp/bin/server", "start", "controller"]
