## Radware kubernetes waf installer
this playbook is meant to:
- configure a centos7 machine into a K8s cluster (support for a 3 node cluster will be added in the future)
- deploy a test application ([OWASP juice shop](https://owasp.org/www-project-juice-shop/))
- add protection with Radware Kwaf

---

### How-to use 

clone this repository to a directory on a dedicated CentOS 7 machine 

The Kwaf install archive is expected to be in the directory where you cloned this repo
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


