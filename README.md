# ELK stack powered by Vagrant which includes Docker and Compose.

Vagrant appliance -> Docker -> Elasticsearch+Logstash+Kibana.
Tested at Windows 10 x86_64, should work at any other vagrant supported OSs including Linux.

3 simple installation steps:

1. Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads) or Vmware virtualization machine
1. Install Vagrant 
1. Enter to command prompt (with root/administor user) the following:
```bash
vagrant plugin install vagrant-docker-compose
```
Et voilà!

If you go to reps's folder and run `vagrant up` and go for tea brake - you'll get a full-functional ELK stack (check browser at https://localhost:5601)
