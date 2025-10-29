FROM centos:7

# Cambiar mirrorlist -> vault (CentOS 7 EOL)
RUN sed -i 's|^mirrorlist=|#mirrorlist=|g' /etc/yum.repos.d/CentOS-*.repo && \
    sed -i 's|^#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-*.repo

# Instalar herramientas necesarias
RUN yum -y install \
      nftables \
      iproute \
      iputils \
      net-tools \
      socat \
    && yum clean all

# Mantener contenedor vivo (para evitar CrashLoopBackOff en K8s)
CMD ["sleep", "infinity"]
