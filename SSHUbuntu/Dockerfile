# Use the official Ubuntu base image
FROM ubuntu:latest

# Update and install necessary packages
RUN apt-get update && apt-get install -y openssh-server

# Create SSH directory and set up a user
RUN mkdir /var/run/sshd && \
    useradd -m -s /bin/bash sshuser && \
    echo 'sshuser:sshpassword' | chpasswd

# Enable SSH login without strict host checking (for simplicity)
RUN echo "StrictHostKeyChecking no" >> /etc/ssh/ssh_config

# Expose SSH port
EXPOSE 22

# Start the SSH server
CMD ["/usr/sbin/sshd", "-D"]
