FROM ubuntu:22.10

RUN rm /bin/sh && ln -s /bin/bash /bin/sh

RUN apt-get update -y && apt-get upgrade -y

RUN apt-get install python3 -y

ARG user_name=ubuntu
ARG user_id=1942
ARG group_name=ubuntu
ARG group_id=1942

RUN groupadd -g ${group_id} ${group_name} && \
    useradd -u ${user_id} -g ${group_id} -d /home/${user_name} --create-home --shell /bin/bash ${user_name} && \
    mkdir /home/${user_name}/src
RUN echo "${user_name} ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers && chown -R ${user_name}:${group_name} /home/${user_name}

USER ${user_name}
WORKDIR /chatbot
