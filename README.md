# Домашнее задание "`«Введение в Ansible»`"   

---

### Задания 1
Попробуйте запустить playbook на окружении из test.yml, зафиксируйте значение, которое имеет факт some_fact для указанного хоста при выполнении playbook.

Выполнение задания 1

![image.jpg](https://github.com/Byzgaev-I/Ansible-Intro/blob/main/1.png) 


### Задания 2
Найдите файл с переменными (group_vars), в котором задаётся найденное в первом пункте значение, и поменяйте его на all default fact.

Выполнение задания 2

 ```yml
---
  some_fact: "all default fact"
```

![image.jpg](https://github.com/Byzgaev-I/Ansible-Intro/blob/main/2.png) 


### Задания 3 
Воспользуйтесь подготовленным (используется docker) или создайте собственное окружение для проведения дальнейших испытаний.

Выполнение задания 3  
docker-compose.yml
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

### Задания 4
Проведите запуск playbook на окружении из prod.yml. Зафиксируйте полученные значения some_fact для каждого из managed host.

Выполнение задания 4 

![image.jpg](https://github.com/Byzgaev-I/Ansible-Intro/blob/main/4.png) 


### Задания 5
Добавьте факты в group_vars каждой из групп хостов так, чтобы для some_fact получились значения: для deb — deb default fact, для el — el default fact.

Выполнение задания 5

deb:examp.yml

 ```yml
---
  some_fact: "deb default fact"
```
el:examp.yml

 ```yml
---
  some_fact: "el default fact"
```

### Задания 6
Повторите запуск playbook на окружении prod.yml. Убедитесь, что выдаются корректные значения для всех хостов.

Выполнение задания 6

![image.jpg](https://github.com/Byzgaev-I/Ansible-Intro/blob/main/6.png)

### Задания 7
При помощи ansible-vault зашифруйте факты в group_vars/deb и group_vars/el с паролем netology.

Выполнение задания 7

![image.jpg](https://github.com/Byzgaev-I/Ansible-Intro/blob/main/7.png) 


### Задания 8
Запустите playbook на окружении prod.yml. При запуске ansible должен запросить у вас пароль. Убедитесь в работоспособности.

Выполнение задания 8

![image.jpg](https://github.com/Byzgaev-I/Ansible-Intro/blob/main/9.png)


### Задания 9
Посмотрите при помощи ansible-doc список плагинов для подключения. Выберите подходящий для работы на control node.

Выполнение задания 9

![image.jpg](https://github.com/Byzgaev-I/Ansible-Intro/blob/main/9.png)

### Задания 10
В prod.yml добавьте новую группу хостов с именем local, в ней разместите localhost с необходимым типом подключения.

Выполнение задания 10

prod.yml
 ```yml
---
  el:
    hosts:
      centos7:
        ansible_connection: docker
  deb:
    hosts:
      ubuntu:
        ansible_connection: docker
  local:
    hosts:
      localhost:
        ansible_connection: local
  fedora:
    hosts:
      fedora:
        ansible_connection: docker
```

### Задания 11
Запустите playbook на окружении prod.yml. При запуске ansible должен запросить у вас пароль. Убедитесь, что факты some_fact для каждого из хостов определены из верных group_vars.

Выполнение задания 11
![image.jpg](https://github.com/Byzgaev-I/Ansible-Intro/blob/main/11.png)


### Необязательная часть
При помощи ansible-vault расшифруйте все зашифрованные файлы с переменными.

Выполнение задания
![image.jpg](https://github.com/Byzgaev-I/Ansible-Intro/blob/main/Необяз%20-1.png)




















