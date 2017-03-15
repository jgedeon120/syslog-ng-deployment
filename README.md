# Syslog-ng Deployment

## Basic Install Notes:
On Ubuntu 16.04:

```apt-get install syslog-ng-core git```

Clone from git repository:

```git clone https://github.com/jgedeon120/syslog-ng-deployment.git /etc/syslog-ng/conf.d/```

Reload syslog-ng and check for errors or conflicts:

```systemctl reload syslog-ng
tail /var/log/syslog```

