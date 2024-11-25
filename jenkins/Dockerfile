FROM jenkins/jenkins:2.452.3-jdk17

USER root

# Install dependencies
RUN apt-get update && apt-get install -y lsb-release curl

# Add Docker repository and install Docker CLI
RUN curl -fsSLo /usr/share/keyrings/docker-archive-keyring.asc \
  https://download.docker.com/linux/debian/gpg
RUN echo "deb [arch=$(dpkg --print-architecture) \
  signed-by=/usr/share/keyrings/docker-archive-keyring.asc] \
  https://download.docker.com/linux/debian \
  $(lsb_release -cs) stable" > /etc/apt/sources.list.d/docker.list
RUN apt-get update && apt-get install -y docker-ce-cli

# Install Node.js
RUN curl -fsSL https://deb.nodesource.com/setup_22.x | bash - \
    && apt-get install -y nodejs

# Switch back to the Jenkins user
USER jenkins

# Optional: Install Jenkins plugins (uncomment if needed)
# RUN jenkins-plugin-cli --plugins "blueocean docker-workflow"
