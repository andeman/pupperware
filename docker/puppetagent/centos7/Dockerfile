FROM centos/systemd:latest

RUN rpm -Uvh https://yum.puppetlabs.com/puppet6-release-el-7.noarch.rpm && \
    #yum upgrade -y && \
    #yum update -y && \
    yum -y install puppet-agent && \
    yum clean all && \
    /opt/puppetlabs/bin/puppet config set server puppet && \
    /opt/puppetlabs/bin/puppet config set certname $(hostname -f) && \
    /opt/puppetlabs/bin/puppet config set environment production && \
    /opt/puppetlabs/bin/puppet config set runinterval 1h && \
    /opt/puppetlabs/bin/puppet resource service puppet ensure=running enable=true

ENV PATH=/opt/puppetlabs/server/bin:/opt/puppetlabs/puppet/bin:/opt/puppetlabs/bin:$PATH

