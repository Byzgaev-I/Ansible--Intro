# Домашнее задание "`«Введение в Ansible»`"   

---

### Задания 1
Попробуйте запустить playbook на окружении из test.yml, зафиксируйте значение, которое имеет факт some_fact для указанного хоста при выполнении playbook.

Выполнения задания 1

![image.jpg](https://github.com/Byzgaev-I/Ansible-Intro/blob/main/1.png) 


### Задания 2
Найдите файл с переменными (group_vars), в котором задаётся найденное в первом пункте значение, и поменяйте его на all default fact.

Выполнения задания 2

 ```yml
---
  some_fact: "all default fact"
```

![image.jpg](https://github.com/Byzgaev-I/Ansible-Intro/blob/main/2.png) 


### Задания 3 
Воспользуйтесь подготовленным (используется docker) или создайте собственное окружение для проведения дальнейших испытаний.

 ```yml
version: '3'
services:
  centos7:
    image: pycontribs/centos:7
    container_name: centos7
    restart: unless-stopped
    entrypoint: "sleep infinity"

  ubuntu:
    image: pycontribs/ubuntu
    container_name: ubuntu
    restart: unless-stopped
    entrypoint: "sleep infinity"

  fedora:
    image: pycontribs/fedora
    container_name: fedora
    restart: unless-stopped
    entrypoint: "sleep infinity"
```

![image.jpg](https://github.com/Byzgaev-I/Ansible-Intro/blob/main/3.png) 






































