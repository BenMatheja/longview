Linode Longview
===============

## Configuration
* Place API-Key in /etc/linode/longview.key 

* Linode/Longview/Util.pm:  $post_target   = 'https://longview.linode.com/post';

## Installation
```bash 
sudo apt-get install build-essential
cd opt
git clone https://github.com/BenMatheja/longview.git
./opt/longview/Extras/install-dependencies.sh
```
Install Dependencies via CPAN
```bash 
cpan -fi Net::HTTP
cpan -fi LWP::UserAgent
cpan -fi LWP::Protocol
```
Deploy Linode Key
```bash 
mkdir /etc/linode
vi /etc/linode/longview.key
```
Start Linode
## Overview
Longview is a system level statistics collection and graphing service, powered by the Longview open source software agent that can be installed onto any Linux system. The Longview agent collects system statistics and sends them to us, where we store the data and present it in beautiful and meaningful ways.

## Requirements

Provide >512MB of Memory

### Perl

The Longview client requires perl 5.8 or higher.

### Kernel

The Longview client should be running with a 2.6 or higher kernel. 

### Operating system

The Longview client can be installed on any system running Linux. Linode provides packages for Debian, Ubuntu, CentOS, and Fedora. A tagged release tarball is provided for systems without a pre-rolled package.

## Client usage

### Running the Longview client
ToDo:

The Longview client runs automatically after being installed and configures itself to run at boot time. You can also start it by running:

    service longview start

The client logs information to /var/log/linode/longview.log. The Longview client logs error messages by default. If you'd like more verbose logs, you can manually start the client in debug mode by running:

    /opt/linode/longview/Linode/Longview.pl debug

The client will daemonize itself and print each stage of data collection to the log file, along with the response received by the server. This can be extremely helpful in diagnosing restrictive firewall issues and assisting Linode support in getting Longview to cooperate on any system.

### Stopping the Longview client

The Longview client can be stopped in a similar fashion to starting it:

    service longview stop

This will halt data collection and the graphs on the Linode Manager's "Longview" tab will not continue to update.

#### Removing the Longview client

The client will stop itself once you remove it from the Linode Manager. You can uninstall it by using your package manager. 

## Misc
* Prefer IPV4 over IPV6 on Machine (https://askubuntu.com/questions/272796/connecting-to-archive-ubuntu-com-takes-too-long)
* https://stackoverflow.com/questions/13672215/cpan-installs-fail-on-ec2-linux-ami-couldnt-untar