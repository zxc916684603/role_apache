Ansible Role: xxx
=========

在CentOS或者Ubuntu服务器上安装和配置xxxx 或xxx

Requirements
------------

无特殊要求,此 role 需要 root 用户权限,可以在playbook全局加入 `become: yes`,或者如下调用 role:

```
- hosts: all
  roles:
    - role: role_xxx
      become: yes
```

Role Variables
--------------

下面列出了可用变量和默认值(请参见"defaults/main.yml"):

```



```



Dependencies
------------

None

Example Playbook
----------------

```
- hosts: all
  become: yes
  vars_files:
    - vars/main.yml
  roles:
    - { role: role_xxx }
```

`vars/main.yml` :
```



```

License
-------

BSD

Ansible Role: phpmyadmin
=========

本 Role 用于在PHP运行环境下安装 [Apache](https://www.apache.org/)。

## Requirements

运行本 Role，请确认符合如下的必要条件：

| **Items**      | **Details** |
| ------------------| ------------------|
| Operating system | CentOS7.x |
| Python 版本 | Python2  |
| Python 组件 |    |
| Runtime |  LAMP or LNMP |


## Related roles

本 Role 在运行时需要确保已经运行： common 等 Role。以 LAMP 为例：

```
roles:
    - {role: role_common, tags: "role_common"}
    - {role: role_apache, tags: "role_apache"}
```


## Variables

本 Role 主要变量以及使用方法如下：

| **Items**      | **Details** | **Format**  | **是否初始化** |
| ------------------| ------------------|-----|-----|
| apache_ius_url | [ https://repo.ius.io/ius-release-el7.rpm ] | 字符串 |是|

注意：



## Example

```
- name: LAMP
  hosts: all
  become: yes
  become_method: sudo 
  vars_files:
    - vars/main.yml 
  
  vars:
    phpmyadmin_webs: 'apache'
    phpmyadmin_mysql_password: '123456'
    phpmyadmin_php_version: '7.2'

  roles:
    - { role: role_common }
    - { role: role_apache }
    ...
```

## FAQ


