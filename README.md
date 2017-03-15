# Syslog-ng Deployment

## Basic Install Notes:
On Ubuntu 16.04:

```apt-get install syslog-ng-core git```

Clone from git repository:

```git clone https://github.com/jgedeon120/syslog-ng-deployment.git /etc/syslog-ng/conf.d/```

Reload syslog-ng and check for errors or conflicts:

```systemctl reload syslog-ng
tail /var/log/syslog```

## Config Files
The following are global or default config files for syslog-ng-deployment.

### 0000-config_path_define.conf

Contains the file path for syslog-ng configs, default is /etc/syslog-ng/

### 0000-options.conf

Contains the system default options for syslog-ng.  These are basically the global options for syslog-ng found in the syslog-ng.conf file.  The installed syslog-ng.conf does not need to be edited now.

### 0000-s_net_source.conf

This file sets the parameters for the syslog receiver to receive syslog messages over the network.

### 0000-log_path_define.conf

This file sets the base log path where syslog messages are to be written to.  This definition includes a site location if needed and defined in the site filter configuration file in the filters directory.

### 0100-includes.conf

This file has the include statements needed for syslog-ng to read the configuration files in the directories for this project.
