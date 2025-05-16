### Задание 1

На лекции рассматривались режимы репликации master-slave, master-master, опишите их различия.

*Ответить в свободной форме.*


В режиме master-slave все изменения (записи и обновления) происходят только на одном ведущем сервере (master), а остальные (slaves) получают данные в режиме только для чтения. Это упрощает настройку и позволяет масштабировать чтение, но создаёт единую точку отказа — если master выходит из строя, запись становится невозможной до переключения.

В режиме master-master запись разрешена на нескольких серверах, и они синхронизируют изменения друг с другом. Такой подход повышает отказоустойчивость и позволяет обрабатывать запись с разных точек, но требует более сложной настройки и механизмов разрешения конфликтов при одновременной записи.
---

### Задание 2

Выполните конфигурацию master-slave репликации, примером можно пользоваться из лекции.

*Приложите скриншоты конфигурации, выполнения работы: состояния и режимы работы серверов.*

![Result 1](https://github.com/hovhannisyan-code/sdb12-06/blob/master/img/screenshot_0.png)
[Master Sql](https://github.com/hovhannisyan-code/sdb12-06/blob/master/mysql_repl_master_slave/master/master.sql)
[Slave Sql](https://github.com/hovhannisyan-code/sdb12-06/blob/master/mysql_repl_master_slave/slave/slave.sql)
[Docker Compose](https://github.com/hovhannisyan-code/sdb12-06/blob/master/mysql_repl_master_slave/docker-compose.yml)
---

## Дополнительные задания (со звёздочкой*)
Эти задания дополнительные, то есть не обязательные к выполнению, и никак не повлияют на получение вами зачёта по этому домашнему заданию. Вы можете их выполнить, если хотите глубже шире разобраться в материале.

---

### Задание 3* 

Выполните конфигурацию master-master репликации. Произведите проверку.

*Приложите скриншоты конфигурации, выполнения работы: состояния и режимы работы серверов.*

[Master 1](https://github.com/hovhannisyan-code/sdb12-06/blob/master/mysql_repl_master_master/master_1/init_m1.sql)
[Master 2](https://github.com/hovhannisyan-code/sdb12-06/blob/master/mysql_repl_master_master/master_2/init_m2.sql)
[Docker Compose](https://github.com/hovhannisyan-code/sdb12-06/blob/master/mysql_repl_master_master/docker-compose.yml)