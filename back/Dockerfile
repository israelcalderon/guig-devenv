FROM python:3.8

WORKDIR /usr/src/app
# those are read only deployment keys please don't worry
COPY deploy_key /root/.ssh/id_rsa
COPY deploy_demo_key /root/.ssh/deploy_demo_key
RUN chmod -R 400 /root/.ssh/
RUN apt-get update && apt-get install -y git
RUN ssh-keyscan -t rsa github.com >> ~/.ssh/known_hosts
RUN ssh-agent bash -c 'ssh-add /root/.ssh/deploy_demo_key && git clone git@github.com:israelcalderon/fullstack-interview-test.git /usr/src/demo'
RUN git config --global user.name "Israel Calderon" && git config --global user.email "icalderon@somemail.com"
WORKDIR /usr/src/demo
RUN git config user.name "Israel Calderon" && git config user.email "icalderon@somemail.com"
RUN git checkout -b dev origin/dev && git checkout -b conflicts origin/conflicts && git checkout master
WORKDIR /usr/src/app
RUN git clone git@github.com:israelcalderon/guig-back.git
RUN pip install ./guig-back/
CMD [ "python", "./guig-back/src/app.py" ]