FROM grafana/fluent-plugin-loki:main

# Set working directory
WORKDIR /app

# Copy configuration files
COPY fluent.conf /fluentd/etc/

# Volume mounts
VOLUME ["/var/log", "/etc/machine-id", "/dev/log", "/var/run/systemd/journal/"]

# Environment variables
ENV LOKI_URL=http://loki:3100/loki/api/v1/push
# Add any other environment variables if needed

# Expose ports
EXPOSE 24224

# Define entry point and command
ENTRYPOINT ["fluentd"]
CMD ["-v", "-p", "/fluentd/plugins"]
