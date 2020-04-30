# Ansible for install Nginx, PHP, MySQL

## Supported OS
* Centos 7

## Functional
* Install Nginx, crete virtual host (domain name must be specified in ansible extra vars).
* Install PHP, and other php packages such as php-fpm.
* Install mysql (percona-release)

## How to install

### 1. Clone this repo
```
git clone https://github.com/intens1ty/ansible.lemp
cd ansible.lemp
```

### 2. Change, or add the desired variables:
* roles/nginx/vars/main.yml
* roles/php/vars/main.yml
* roles/mysql/vars/main.yml

Default values:
* php version - 7.4
* php packages - php, php-cli, php-common, php-fpm, php-mysqlnd
* mysql version - 5.7

### 3. Add your hosts in inventory file
* inventory/hosts.ini

### 4. Start ansible with extra-var - domain name for nginx
```
ansible-playbook -i inventory/hosts.ini -l my_host --extra-var "domain_name=example.local" playbook.yml
```
