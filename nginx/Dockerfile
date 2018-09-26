# install base image, amazon linux
FROM amazonlinux:2017.12.0.20180330

# install packages
RUN yum -y update && yum clean all && \
    yum -y install \
    wget \
    git \
    awscli \
    openssh \
    openssh-server \
    tar \
    gcc \
    make \
    zlib-devel \
    openssl-devel \
    which \
    zip \
    unzip \
    glibc-langpack-ja

# set timezone
RUN ln -sf /usr/share/zoneinfo/Asia/Tokyo /etc/localtime

# install python 3.6.6
ENV HOME /root
ENV PYENV_ROOT $HOME/.pyenv
ENV PATH $PYENV_ROOT/bin:$PATH
RUN git clone https://github.com/yyuu/pyenv.git $HOME/.pyenv
RUN echo 'eval "$(pyenv init -)"' >> ~/.bashrc && \
    eval "$(pyenv init -)"
RUN pyenv install 3.6.6 && \
    pyenv global 3.6.6

# install nginx
RUN yum install -y http://nginx.org/packages/centos/7/noarch/RPMS/nginx-release-centos-7-0.el7.ngx.noarch.rpm
RUN yum install -y --enablerepo=nginx nginx
RUN yum swap -y fakesystemd systemd && yum clean all
#RUN service nginx restart
RUN systemctl enable nginx
ENTRYPOINT ["/usr/sbin/nginx", "-g", "daemon off;", "-c", "/etc/nginx/nginx.conf"]
EXPOSE 80
# set LANG
ENV LANG ja_JP.UTF-8