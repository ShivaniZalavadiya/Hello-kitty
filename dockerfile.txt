# Use an outdated base image with known vulnerabilities
FROM ubuntu:16.04

# Run commands as root (bad practice)
RUN apt-get update && apt-get install -y \
    curl \
    wget \
    nano

# Hardcoded credentials (vulnerability)
ENV DB_USERNAME=root
ENV DB_PASSWORD=password

# Expose ports without restricting IPs
EXPOSE 8080
