## Ansible For HAProxy
Setup Load Balancing dengan HAPoxy dengan 2 Web Server Nginx, dengan Bantuan Vagrant untuk Provision VM.

### Steps: 
#### 1. Vagrant
Buat Vagrantfile, untuk Provision 3 VM, 1 untuk HAProxy dan 2 Untuk Web Server (Nginx), dengan OS Ubuntu. Didalam Vagrantfile, saya menambahkan script untuk ganti password root, update repository dan install aplikasi sshpas. Vagrantfile saya copas dari repo github.com/lukmanlab :v.
#### 2. Ansible
##### File hosts.yml
- Sesuaikan IP Server.
- Sesuaikan User dan Password Server.

##### Jalankan Ansible
`$ ansible-playbook -i hosts.yml haproxy-nginx-install.yml`