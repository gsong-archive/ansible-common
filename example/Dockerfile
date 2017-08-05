FROM gsong/ansible:latest

ARG USER_ID=1000
ARG GROUP_ID=1000
RUN addgroup -g ${GROUP_ID} ansible
RUN adduser -s /bin/bash -u ${USER_ID} -G ansible -D -g "" ansible

USER ansible
RUN echo $'source /etc/bash.bashrc\n\
/usr/bin/keychain $(eval echo ${SSH_KEYS})\n\
source ${HOME}/.keychain/${HOSTNAME}-sh'\
>> $HOME/.bashrc
