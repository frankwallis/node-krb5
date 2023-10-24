FROM rockylinux:9

# Install epel (requirement for service nginx)
RUN yum install -y epel-release

RUN yum install -y scl-utils
RUN yum install -y gcc-toolset-12

# Install misc
RUN yum install -y wget git vim sudo make

# Install compilation tools
RUN yum install -y python3 make

# Install Kerberos libs
RUN yum install -y krb5-devel

# Install Node.js via n
ENV NPM_CONFIG_LOGLEVEL info
RUN git clone https://github.com/tj/n /n
RUN cd /n && make install
RUN n 16
RUN n 18

RUN mkdir -p /node-krb5
COPY ./run.sh /run.sh
ENTRYPOINT ["/run.sh"]
