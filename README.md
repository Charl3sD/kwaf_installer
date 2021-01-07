## Radware kubernetes waf installer
this installer is meant to deploy automaticaly a radware kubernetes waf for Lab and demo purposes and does the following:
- configure a centos7 machine into a K8s cluster (support for a 3 node cluster will be added in the future)
- deploy 2 instances of a demo application ([OWASP juice shop](https://owasp.org/www-project-juice-shop/))
- protect 1 of those instances with Radware Kwaf

---

### How-to use 

provision a Centos 7 server machine and configure networking


|Specs| CPU | RAM | Disk|
| --- | --- | --- | --- |
|Minimum | 6 | 12GB | 25GB|
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

Enjoy !
