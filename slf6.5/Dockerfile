## create a Scientific Linux Fermi container from the Centos one
##
FROM centos:6
MAINTAINER dbox@fnal.gov
RUN mkdir -p /etc/yum/vars
RUN echo 6.5 > /etc/yum/vars/releasever
RUN rpm -ivh --force http://linux1.fnal.gov/linux/fermi/slf6.5/x86_64/os/FermiPackages/slf-release-6.5-1.x86_64.rpm
ADD dot-bashrc                    /root/.bashrc
ADD dot-bash_profile              /root/.bash_profile
RUN yum -y erase centos-release
RUN yum -y erase all
RUN yum -y distro-sync
RUN mv /bin/uname /bin/uname.2
ADD uname /bin/uname
RUN chmod +x /bin/uname
RUN yum -y install upsupdbootstrap-fnal
ENV HOME /root
## EOF
