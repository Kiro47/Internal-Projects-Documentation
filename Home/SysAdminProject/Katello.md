# Katello

## Pre-Setup

* CentOS 7 VM
* Minimal Install, no security policies set
* root user only, later administrative logins will be LDAP based

## Install
Installer page: https://theforeman.org

```
# Repos
yum -y install https://yum.puppet.com/puppet6-release-el-7.noarch.rpm
yum -y install http://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
yum -y install https://yum.theforeman.org/releases/1.22/el7/x86_64/foreman-release.rpm

# Packages
yum -y install foreman-installer
yum -y install vim tmux bash-completion

```

```
# Foreman Install
foreman-installer -i -v | tee /root/foreman-installer.log
```