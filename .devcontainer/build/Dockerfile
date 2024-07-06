FROM debian:12-slim
ARG WORKSPACE_DIR

# Install software
RUN apt-get -y update && apt-get -y install curl unzip procps default-jdk openssh-client zsh nano vim git

# Add an unprivileged user without password
RUN adduser main && passwd -d main

# Add workspace directory
RUN mkdir -p ${WORKSPACE_DIR} && chown -R main:main ${WORKSPACE_DIR}

# Set ZSH as shell
RUN chsh -s /bin/zsh main

USER main
RUN echo "Configured shell for user main: $SHELL"
USER root
