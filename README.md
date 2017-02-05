exo-spark-sm
=======

A set of Ansible playbooks to deploy a single master spark cluster on Exoscale.

[Apache Spark](https://spark.apache.org/) is an open-source cluster-computing framework. Originally developed at the University of California, Berkeley's AMPLab, the Spark codebase was later donated to the Apache Software Foundation, which has maintained it since.

- [Exoscale](https://www.exoscale.ch/) is a Switzerland cloud provider for the digital native based on the Apache Cloudstack API.

- [Ansible](https://www.ansible.com/) is the simplest way to automate apps and infrastructure, the DevOps way.

**Note:** This is perfect to play with spark and fiering a cluster on demand. For a production cluster it would rather use a multi master on with zookeeper and mesos as the cluster manager.

Getting Started
=======

First copy or create your cloudstack.ini with your exoscale credentials.

```
$ cat ./cloudstack.ini
[cloudstack]
endpoint = https://api.exoscale.ch/compute
key = cloudstack api key
secret = cloudstack api secret
method = post
```

Run the setup script to make sure the dependencies are met.
```
$ ./setup.sh
```

The script will do the following for you:
- Install or update Ansible, python module ansible
- Install or update your python cloudstack API, python module cs

Run the playbook to create the instance.
```
$ ansible-playbook create-cluster.yaml
```

Feel free to adapt *group_vars/all.yaml* and the playbooks to modify the parameters to your liking.


Authors
=======
Marc Guillen (marc.guillen@datsci.farm)

Licence
=======
Click on the [Link](LICENSE) to see the full text.
