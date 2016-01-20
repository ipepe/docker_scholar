FROM ubuntu:14.04

ENV DEBIAN_FRONTEND noninteractive
RUN echo 'debconf debconf/frontend select Noninteractive' | debconf-set-selections

RUN sudo apt-get update
RUN sudo apt-get install --yes wget
RUN sudo echo deb http://deb.opera.com/opera/ stable non-free >> /etc/apt/sources.list
RUN sudo wget -qO - http://deb.opera.com/archive.key | sudo apt-key add -
RUN sudo apt-get install --yes debian-archive-keyring
RUN sudo apt-get update
RUN sudo apt-get install --yes opera

# Replace 1000 with your user / group id
RUN export uid=1000 gid=1000 && \
    mkdir -p /home/developer && \
    echo "developer:x:${uid}:${gid}:Developer,,,:/home/developer:/bin/bash" >> /etc/passwd && \
    echo "developer:x:${uid}:" >> /etc/group && \
    echo "developer ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/developer && \
    chmod 0440 /etc/sudoers.d/developer && \
    chown ${uid}:${gid} -R /home/developer

USER developer
ENV HOME /home/developer
CMD /usr/bin/opera
