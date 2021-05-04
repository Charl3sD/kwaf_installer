## Radware kubernetes waf installer
this installer is meant to deploy automaticaly a radware kubernetes waf for Lab and demo purposes and does the following:
- configure a centos7 machine into a K8s cluster (support for a 3 node cluster will be added in the future)
- deploy 2 instances of a few demo applications
  * ([OWASP juice shop](https://owasp.org/www-project-juice-shop/))
  * ([BWAPP](http://www.itsecgames.com/))
- protect 1 instance of each app with Radware Kwaf

---

### How-to use 

provision a Centos 7 server minimal machine and configure networking (netinstall issues are under inverstigation)


|Specs| CPU | RAM | Disk|
| --- | --- | --- | --- |
|Minimum | 6 | 16GB | 25GB|
|Recomended | 8 | 20GB | 35GB|

clone this repository to a directory on your *dedicated* CentOS 7 machine 

The Radware Kwaf install archive is expected to be in the parent directory where this installer resides
ex:
```
somedirectory _
               |-kwaf_installer
               |             ├── files
               |             │   └── group_vars
               |             │       ├── all
               |             │       └── k8s-cluster
               |             ├── tasks
               |             └── vars
               |-KubernetesWAF-1-4-0.tgz
```

run the bootstrap.sh script as root 

follow the instructions 

expect the installer to run for a while (~1H) 

note that you can run parts of the install using tags defined in the prequisites.yml and deployment.yml Ansible playbooks:

```
ansible-playbook -i,127.0.0.1 deployment.yml -u root --private-key=~/.ssh/id_rsa --tags kwaf_patch 
```

Upgrades are possible using the playbook to this effect.
Note that you must first edit the vars/k8s.yaml file to reflect the target version and new Kwaf tgz archive

```
ansible-playbook -i,127.0.0.1 upgrade.yml -u root --private-key=~/.ssh/id_rsa
```

Enjoy !
