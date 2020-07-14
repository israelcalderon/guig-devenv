FROM node:lts-buster

WORKDIR /app

RUN apt-get update && apt-get install -y git
# this is a deployment read only key too
COPY deploy_key /root/.ssh/id_rsa
RUN chmod -R 400 /root/.ssh/
RUN ssh-keyscan -t rsa github.com >> ~/.ssh/known_hosts
RUN ssh-agent bash -c 'ssh-add /root/.ssh/id_rsa && git clone git@github.com:israelcalderon/guig-front.git /app'
RUN npm install -g http-server
RUN npm install
RUN npm run build

EXPOSE 8080
CMD [ "http-server", "dist" ]