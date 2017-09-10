Linode Longview
===============

## Configuration
Place API-Key in /etc/linode/longview.key 

Linode/Longview/Util.pm:  $post_target   = 'https://longview.linode.com/post';

## Overview
Longview is a system level statistics collection and graphing service, powered by the Longview open source software agent that can be installed onto any Linux system. The Longview agent collects system statistics and sends them to us, where we store the data and present it in beautiful and meaningful ways.

## Requirements

### Perl

The Longview client requires perl 5.8 or higher.

### Kernel

The Longview client should be running with a 2.6 or higher kernel. 

### Operating system

The Longview client can be installed on any system running Linux. Linode provides packages for Debian, Ubuntu, CentOS, and Fedora. A tagged release tarball is provided for systems without a pre-rolled package.

## Client usage

### Installation

The client is normally installed by running a one-liner provided by the Linode Manager, which will automatically detect your operating system and drop your client's API key onto the filesystem.

The client installs itself to /opt/linode/longview and will drop the API key under /etc/linode/longview.key.

Alternately, you can obtain a full copy of the repository, which will allow the Extras/install-dependencies.sh script to install (using cpanm) all required perl modules in a lib directory in your local copy of the repository.

### Running the Longview client

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
