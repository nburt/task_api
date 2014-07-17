# Simple JSON API server in Golang

This is a small sample project I used to help me learn go. It will expand and change as I try to add more functionality

- First iteration uses a text file to store json
- Next steps:
    - Implement Tests
    - Refactor to multiple files
    - implement Postgresql
    
Working in conjunction with 
- Scott Skender
- Mike Gehard

## Get and Post tasks

our little server handles POST commands to `/task/new` with in the following format:

```
{"Name":"Wash Dishes","Description":"Is the name not clear enough?"}

```

you can also get all tasks with `/tasks`

## Take a look online!

With the help of Mike Gehard, we were able to deploy our server below!
http://107.170.31.184:8080/tasks

## Get it running!

I would write a little intro here to get things up and running on your machine... but the Golang docs doa  good job at that:

http://golang.org/doc/

## Deployment
Deploying the service is done via [Ansible](http://www.ansible.com/home).
Right now two groups are supported, local and production.

* The local group runs against a Ubuntu 14.04 server that runs on your development
machine.
* The production group goes against a Digital Ocean machine.

Currently the Ansible scripts can run the ping/pong command using `ansible local -m ping -i deployment/hosts`
or `ansible production -m ping -i deployment/hosts`.

To set up a local development server:

1. Install VirtualBox and Vagrant
1. Run `vagrant box add ubuntu1404 https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box`
1. Run `vagrant init ubuntu1404`
1. Run `vagrant up` and the box should be up and running.
1. Test that by running `ansible local -m ping -i deployment/hosts --private-key=~/.vagrant.d/insecure_private_key`.