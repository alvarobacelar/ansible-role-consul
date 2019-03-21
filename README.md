
ansible-role-consul
=========

[![Build Status](https://travis-ci.org/alvarobacelar/ansible-role-consul.svg?branch=master)](https://travis-ci.org/alvarobacelar/ansible-role-consul)

Role de instalação e configuração do consul e consul-template.

Requirements
------------

Para instalar o consul é necessário que tenha instalado e configurado o seu ambiente com docker e nginx

Role Variables
--------------

As variáveis abaixo são os valores defaults, caso haja a necessidade de mudar, pode-se criar um arquivo de host_vars ou group_vars (ou até mesmo passar no arquivo de playbook): 
```yml
path_nginx: /etc/nginx
path_nginx_config: /conf.d
sys_user: root
path_consul: /etc/consul
name_upstream: upstream
name_location: location
consul_port: 8500
nginx_service_consul: nginx
```

A variável que você terá que informar é na verdade uma array, informando quais serviores farão parte do seu cluster do consul, Ex: 
```yml
datacenter_consul: 'lab01'
srv_hostname_consul: # coloque aqui os IPs que farão parte do seu cluster
  - 10.100.20.10
  - 10.100.20.11
```

As variáveis abaixo são valores fixos e só devem mudar caso mude a versão do consul: 
```yml
_link_consul: https://releases.hashicorp.com/consul/1.2.2/consul_1.2.2_linux_amd64.zip
_link_consul_template: https://releases.hashicorp.com/consul-template/0.19.5/consul-template_0.19.5_linux_amd64.tgz
```

Dependencies
------------

N/A

Example Playbook
----------------

Includiing an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - consul

License
-------

BSD

Author Information
------------------
Alvaro Bacelar - Analytics DevOps
