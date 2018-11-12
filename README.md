This is a customized version of [Drupal VM](https://github.com/geerlingguy/drupal-vm) for the Acquia Central Presales team.

This version of Drupal VM installs the following on an Ubuntu 16.04 (by default) linux VM:

  - Apache 2.4.x (or Nginx)
  - PHP 7.1.x (configurable)
  - MySQL 5.7.x (or MariaDB, or PostgreSQL)
  - Acquia Lightning (D8)

It should take 5-10 minutes to build or rebuild the VM from scratch on a decent broadband connection.

## Quick Start

This Quick Start will help you quickly build a Lightning Drupal 8 site on the Drupal VM using Composer.

  1. Install [Vagrant](https://www.vagrantup.com/downloads.html) and [VirtualBox](https://www.virtualbox.org/wiki/Downloads).
  2. Clone this project to your workstation.
  3. `cd` into this project directory and run `vagrant up`.

### 1 - Install Vagrant and VirtualBox

Download and install [Vagrant](https://www.vagrantup.com/downloads.html) and [VirtualBox](https://www.virtualbox.org/wiki/Downloads).

You can also use an alternative provider like Parallels or VMware. (Parallels Desktop 11+ requires the "Pro" or "Business" edition and the [Parallels Provider](http://parallels.github.io/vagrant-parallels/), and VMware requires the paid [Vagrant VMware integration plugin](http://www.vagrantup.com/vmware)).

  [Install Ansible](http://docs.ansible.com/intro_installation.html) on your host machine, so Drupal VM can run the provisioning steps locally instead of inside the VM.
  
  Install Vagrant's `vbguest` plugin: `vagrant plugin install vagrant-vbguest`.
  
  Install Vagrant's `vagrant-auto_network` plugin: `vagrant plugin install vagrant-auto_network`.
  
  - **Versions**: *Make sure you're running the latest releases of Vagrant, VirtualBox, and Ansible—as of early 2018, Drupal VM recommends: Vagrant 2.0.x, VirtualBox 5.2.x, and Ansible 2.4.x*

### 2 - Build the Virtual Machine

  1. Download this project and put it wherever you want.
  2. Open Terminal, `cd` to this directory (containing the `Vagrantfile` and this README file).
  3. Type in `vagrant up`, and let Vagrant do its magic.

Once the process is complete, you will have a Drupal codebase available inside the `drupal/` directory of the project.

Note: *If there are any errors during the course of running `vagrant up`, and it drops you back to your command prompt, just run `vagrant provision` to continue building the VM from where you left off. If there are still errors after doing this a few times, post an issue to this project's issue queue on GitHub with the error.*

### 3 - Access the VM.

Open your browser and access [http://dashboard.presales.central/](http://dashboard.presales.central/). The default login for the admin account is `admin` for both the username and password.

Note: *Since the `vagrant-auto_network` plugin was installed an IP address was assigned to the VM.  You can check what the IP address is by going to your `etc/hosts` file or by ssh'ing into the VM with `vagrant ssh` and running `hostname -I`*

## Other Notes

  - To shut down the virtual machine, enter `vagrant halt` in the Terminal in the same folder that has the `Vagrantfile`. To destroy it completely (if you want to save a little disk space, or want to rebuild it from scratch with `vagrant up` again), type in `vagrant destroy`.
  - To log into the virtual machine, enter `vagrant ssh`. You can also get the machine's SSH connection details with `vagrant ssh-config`.
  - When you rebuild the VM (e.g. `vagrant destroy` and then another `vagrant up`), make sure you clear out the contents of the `drupal` folder on your host machine, or Drupal will return some errors when the VM is rebuilt (it won't reinstall Drupal cleanly).
  - You can change the installed version of Drupal or drush, or any other configuration options, by editing the variables within `config.yml`.
  - Find out more about local development with Vagrant + VirtualBox + Ansible in this presentation: [Local Development Environments - Vagrant, VirtualBox and Ansible](http://www.slideshare.net/geerlingguy/local-development-on-virtual-machines-vagrant-virtualbox-and-ansible).
  - Learn about how Ansible can accelerate your ability to innovate and manage your infrastructure by reading [Ansible for DevOps](http://www.ansiblefordevops.com/).

## License

This project is licensed under the MIT open source license.

## About the Author

[Jeff Geerling](https://www.jeffgeerling.com/) created Drupal VM in 2014 for a more efficient Drupal site and core/contrib development workflow. This project is featured as an example in [Ansible for DevOps](https://www.ansiblefordevops.com/).
