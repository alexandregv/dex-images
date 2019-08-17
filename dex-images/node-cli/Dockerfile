FROM node:alpine

LABEL maintainer="contact@alexandregv.fr"
LABEL docker.cmd="docker run alexandregv/node-cli <command>"
LABEL docker.cmd.help="docker run alexandregv/node-cli help"

LABEL org.dockerland.dex.api=v1
LABEL org.dockerland.dex.docker_volumes="\$(pwd):/app"

WORKDIR /app

RUN echo -e '#!/bin/sh\n\
echo "\033[0;36m"\n\
echo "----- [ General usage ] -----"\n\
echo "docker run -v \${PWD}:/app node-cli <command>"\n\
echo "docker run -v \${PWD}:/app node-cli npm <subcommand>"\n\
echo "docker run -v \${PWD}:/app node-cli npx <subcommand>"\n\
echo "docker run -v \${PWD}:/app node-cli yarn <subcommand>"\n\
echo "\n----- [ Examples ] -----"\n\
echo "docker run -v \${PWD}:/app node-cli npx create-react-app <name>"\n\
echo "docker run -v \${PWD}:/app node-cli npx install --save <package>"\n\
echo "docker run -v \${PWD}:/app node-cli yarn create react-app <name>"\n\
echo "docker run -v \${PWD}:/app node-cli yarn add <package>"\n\
echo "\033[0;36m"\n\'\
> /usr/local/bin/help
RUN chmod +x /usr/local/bin/help

RUN chown -R node:node /app
USER node
