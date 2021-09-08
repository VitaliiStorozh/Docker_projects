FROM sv301185/centos_mingle

RUN git clone https://github.com/VitaliiStorozh/Mingle.git
WORKDIR /Mingle/mingle
RUN /bin/sh -c 'script/build'

CMD /bin/bash -c "source /root/.bashrc && script/tomcat"
EXPOSE 8080
