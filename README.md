# Testing

1. Go to the testing checklist here: https://docs.google.com/spreadsheet/ccc?key=0AryL2uG4GZZ8dEsxUEtWMmVtaHJkTFJBdEtBZklacHc
1. Add issues using the [issues tab](https://github.com/nuevomundo/pnm-joomla/issues)

# Development Setup

It's helpful to work on the pnm-joomla project inside of a virtual machine. This allows for everyone to work in the exact same build environment without installing anything on the root-level of your local machine.

## Mac OSX Instructions

### Homebrew
[Homebrew](http://brew.sh/) is "the missing package manager for OS X."
```
$ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
$ brew install caskroom/cask/brew-cask
```
### Vagrant
[Vagrant](http://sourabhbajaj.com/mac-setup/Vagrant/README.html) is an amazing tool for managing virtual machines via a simple to use command line interface.
```
$ brew cask install virtualbox
$ brew cask install vagrant
$ brew cask install vagrant-manager
```
### Joomlatools Vagrant box
The [Joomlatools Vagrant box](https://github.com/joomlatools/joomla-vagrant) automates the setup of a Joomla development environment. It is capable of running a full featured LAMP stack with a single command so that you can start working on your Joomla projects quickly.

Get the latest version of joomla-vagrant from github
```
$ git clone git@github.com:joomlatools/joomla-vagrant.git
```
Now let's start the virtual machine (this will take a while the first time)
```
$ cd joomla-vagrant
$ vagrant up
```
Next, let's ssh inside of the virtual machine
```
$ vagrant ssh
```
From inside of the virtual machine, create a new joomla site
```
$ phpmanager use 5.3.29
$ joomla site:create pnm --joomla=3.3.6
```
Next, let's grab a copy of the site backup from the production server. 
```
(Ask someone about where and how to get this)
```

Add the following line to `/etc/hosts` so that we can access the virtual machine from the browser easily.
```
33.33.33.58 joomla.dev webgrind.joomla.dev phpmyadmin.joomla.dev
```

