FROM gsong/ansible-common

ARG USER_ID=1000
ARG GROUP_ID=1000
RUN addgroup --gid ${GROUP_ID} ansible
RUN adduser --shell /bin/bash --uid ${USER_ID} --ingroup ansible --disabled-password --gecos "" ansible

USER ansible
RUN echo 'export HISTFILE=${HOME}/.bash_history/history' >> ${HOME}/.bashrc
RUN echo '/usr/bin/keychain $(eval echo ${SSH_KEYS})' >> ${HOME}/.bashrc
RUN echo 'source ${HOME}/.keychain/${HOSTNAME}-sh' >> ${HOME}/.bashrc
