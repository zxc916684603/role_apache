Ansible Role: Apache
=========

本 Role 用于在PHP运行环境下安装 [Apache](https://www.apache.org/)，以及一些紧耦合的应用，包括：certbot等。

## Requirements

运行本 Role，请确认符合如下的必要条件：

| **Items**      | **Details** |
| ------------------| ------------------|
| Operating system | CentOS7.x Ubuntu18.04 AmazonLinux |
| Python 版本 | Python2  |
| Python 组件 |    |
| Runtime |  |


## Related roles

本 Role 在运行时需要确保已经运行：common。以 LAMP 为例：

```
roles:
    - {role: role_common, tags: "role_common"}
    - {role: role_apache, tags: "role_apache"}
```


## Variables

本 Role 主要变量以及使用方法如下：

| **Items**      | **Details** | **Format**  | **是否初始化** |
| ------------------| ------------------|-----|-----|
| apache_vhost_mode | default.conf template, selected from [reverse,www,alias]  | String | No |
| apache_reverse_proxy_port | when use reverse template, this var must used  | String | No |
| apache_listen_port | "80"  | String | No |
| apache_appanme | joomla  | String | Yes |



## Example

```
- name: LAMP
  hosts: all
  become: yes
  become_method: sudo 
  vars_files:
    - vars/main.yml 

  roles:
    - { role: role_common }
    - { role: role_apache }
    ...
```

## FAQ


