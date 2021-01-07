## Radware kubernetes waf installer
this playbook is meant to:
- configure a centos7 machine into a K8s cluster (support for a 3 node cluster will be added in the future)
- deploy a test application ([OWASP juice shop](https://owasp.org/www-project-juice-shop/))
- add protection with Radware Kwaf

---

### How-to use 

provision a Centos 7 server machine


|Specs| CPU | RAM | Disk|
| --- | --- | --- | --- |
|Minimum | 6 | 12GB | 20GB|
|Recomended | 8 | 20GB | 30GB|

clone this repository to a directory on your *dedicated* CentOS 7 machine 

The Radware Kwaf install archive is expected to be in the parent directory where this installer resides
ex:
```
somedirectory _
               |-kwaf
               |  ├── files
               |  │   └── group_vars
               |  │       ├── all
               |  │       └── k8s-cluster
               |  ├── tasks
               |  └── vars
               |-KubernetesWAF-1-4-0.tgz
```

run the bootstrap.sh script as root 

follow the instructions 

expect the installer to run for a while (~1H) 

Enjoy !
