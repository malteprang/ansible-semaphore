FROM ubuntu:18.04

RUN apt-get update
RUN apt-get install -y python3-pip git wget mariadb-client
RUN pip3 install ansible
RUN wget https://github.com/ansible-semaphore/semaphore/releases/download/v2.5.1/semaphore_2.5.1_linux_amd64.deb
RUN dpkg -i semaphore_2.5.1_linux_amd64.deb
ADD https://github.com/ufoscout/docker-compose-wait/releases/download/2.2.1/wait /wait
ADD script/add_admin /add_admin
ADD script/update_conf /update_conf
RUN chmod +x /wait
RUN chmod +x /add_admin
RUN chmod +x /update_conf
ENTRYPOINT [ "/bin/bash" ]
CMD ["-c", "/wait && semaphore -migrate /semaphore/config.json" ]