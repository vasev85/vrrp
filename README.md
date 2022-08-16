# Домашнее задание к занятию "10.1. Keepalived/vrrp"
**

 Домашнее задание выполните в Google Docs и отправьте в личном кабинете на проверку ссылку на ваш документ.

Название файла должно содержать номер лекции и фамилию студента. Пример названия: "10.1 Keepalived/vrrp - Александр Александров"

Перед тем как выслать ссылку, убедитесь, что ее содержимое не является приватным (открыто на просмотр всем, у кого есть ссылка). Если необходимо прикрепить дополнительные ссылки, просто добавьте их в свой Google Docs.

Любые вопросы по решению задач задавайте в чате учебной группы.

---

### Задание 1. 

Требуется развернуть топологию из лекции и выполнить установку и настройку сервиса Keepalived. 

```
vrrp_instance test {

state "name_mode"

interface "name_interface"

virtual_router_id "number id"

priority "number priority"

advert_int "number advert"

authentication {

auth_type "auth type"

auth_pass "password"

}

unicast_peer {

"ip address host"

}

virtual_ipaddress {

"ip address host" dev "interface" label "interface":vip

}

}

```

*Пришлите скриншот рабочей конфигурации и состояния сервиса для каждого нода.*
![alt text](https://github.com/vasev85/vrrp/blob/main/ex1.png?raw=true) 
![alt text](https://github.com/vasev85/vrrp/blob/main/ex1_1.png?raw=true)
![alt text](https://github.com/vasev85/vrrp/blob/main/ex1_21.png?raw=true) 
![alt text](https://github.com/vasev85/vrrp/blob/main/ex1_31.png?raw=true) 
## Дополнительные задания (со звездочкой*)

Эти задания дополнительные (не обязательные к выполнению) и никак не повлияют на получение вами зачета по этому домашнему заданию. Вы можете их выполнить, если хотите глубже и/или шире разобраться в материале.
 
### Задание 2*.

Проведите тестирование работы ноды, когда один из интерфейсов выключен. Для этого:
- добавьте еще одну виртуальную машину и включите ее в сеть;
- на машине установите wireshark и запустите процесс прослеживания интерфейса;
- запустите процесс ping на виртуальный хост;
- выключите интерфейс на одной ноде (мастер), остановите wireshark;
- найдите пакеты ICMP, в которых будет отображён процесс изменения MAC адреса одной ноды на другой. 

 *Пришлите скриншот до и после выключения интерфейса из Wireshark.*
 ![alt text](https://github.com/vasev85/vrrp/blob/main/ex2.png?raw=true)
 ![alt text](https://github.com/vasev85/vrrp/blob/main/ex2_1.png?raw=true) 
