Heat template: GlusterFS Practice Lab (2 nodes)
=======================================

Requirements
------------
* Access to an OpenStack Cloud with Heat. [Rackspace Public Cloud](https://www.rackspace.com/cloud/public) recommended.
* CentOS 7 cloud image.

Provides
------------
* multiple servers with attached cloud block storage (gluster_count: 2)
* common ssh-key distributed to root user on all hosts (key_name)
* lvm thinpool configuration of attached storage resource
* 4x 2G xfs bricks created on thinpool, persistently mounted on all hosts
* yum update of all hosts
* gluster SIG repo enabled
* glusterfs-server-3.10 installed, started, and enabled
* gluster service enabled in firewalld

Deploy Gluster 
------------

Create Gluster cluster

```
openstack --os-cloud rackspace stack create gluster -u https://raw.github.com/ryansyah/rs-heat-templates/devel/gluster/multi-gluster.yaml
```

To Do
------------
* implement /etc/hosts propagation between nodes
* re-implement with Ansible
