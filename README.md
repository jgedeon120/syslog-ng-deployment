# Syslog-ng Deployment

## Basic Install Notes:
On Ubuntu 16.04:

```
apt-get install syslog-ng-core git
```

Clone from git repository:

```
git clone https://github.com/jgedeon120/syslog-ng-deployment.git /etc/syslog-ng/conf.d/
```

Reload syslog-ng and check for errors or conflicts:

```
systemctl reload syslog-ng
tail /var/log/syslog
```


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

## Config Folders

### Destinations

This folder contains all the destination configurations.  The destination is where the syslog messages are to be written to.

### Filters

This folder contains all the filter configurations.  The filters are used to define the messages that are coming in.

### Logs

This folder contains the logging statements for the messages coming in. Where the message is coming from, the filters to match with and where to write the message.  Most will end with the configuration of flags(final), which tells syslog-ng there is nothing more to do with that message.

### Parsers

This folder contains the parsers so that syslog-ng can understand common structured data that is coming in via syslog.  Like CEF and LEEF.

### Rewrites

This folder contains the rewrite configurations for syslog-ng.  An example is matching the network the syslog sending device is coming from and setting the site name the device is at. This information is used by the logging statement to adjust the writing path of the message.

### Templates

This folder contains the templates used by the destination configuration on how to write the message using the syslog-ng macros.
