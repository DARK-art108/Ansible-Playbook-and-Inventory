# Ansible-Playbook-and-Inventory
Listing some basic Ansible Playbooks!

The install-nginx.yml will install the nginx server on multiple server at a time and boot it up, with inventory as a localhost, so our nginx with run on a localhost system we are not making any SSH connection right now so it will be run on a local system.

install-nginx.yml

```yml
---
- hosts: web-servers
  tasks:
    - name: "install nginx"
      package: name=nginx state=latest
    - name: "start nginx"
      service: name: nginx state: started
```

inventory-file

```
[web-servers]
localhost connection=local
```
