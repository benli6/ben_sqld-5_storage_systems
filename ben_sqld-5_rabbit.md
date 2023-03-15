### Задание 1. Установка RabbitMQ

Используя Vagrant или VirtualBox, создайте виртуальную машину и установите RabbitMQ.
Добавьте management plug-in и зайдите в веб-интерфейс.

*Cкриншот веб-интерфейса RabbitMQ:*

![rabbit_1](https://github.com/benli6/ben_sqld-5_storage_systems/blob/main/screenshots/ben_rabbit_1.png)

---

### Задание 2. Отправка и получение сообщений

Используя приложенные скрипты, проведите тестовую отправку и получение сообщения.
Для отправки сообщений необходимо запустить скрипт producer.py.

*Скриншот веб-интерфейса с очередью под названием hello*

![rabbit_2](https://github.com/benli6/ben_sqld-5_storage_systems/blob/main/screenshots/ben_rabbit_2.png)

*Скриншот результата выполнения скрипта consumer.py*

![rabbit_3](https://github.com/benli6/ben_sqld-5_storage_systems/blob/main/screenshots/ben_rabbit_3.png)

---

### Задание 3. Подготовка HA кластера

Используя Vagrant или VirtualBox, создайте вторую виртуальную машину и установите RabbitMQ.
Добавьте в файл hosts название и IP-адрес каждой машины, чтобы машины могли видеть друг друга по имени.

Затем объедините две машины в кластер и создайте политику ha-all на все очереди.

 *Cкриншот из веб-интерфейса с информацией о доступных нодах в кластере*

![rabbit_4](https://github.com/benli6/ben_sqld-5_storage_systems/blob/main/screenshots/ben_rabbit_4.png)

 *Cкриншот из веб-интерфейса с включённой политикой*

![rabbit_5](https://github.com/benli6/ben_sqld-5_storage_systems/blob/main/screenshots/ben_rabbit_5.png)

*Скриншот вывода команды с двух нод:*

```shell script
$ rabbitmqctl cluster_status
```

![rabbit_6](https://github.com/benli6/ben_sqld-5_storage_systems/blob/main/screenshots/ben_rabbit_6.png)

*Скриншот выполнения команды на каждой из нод:*

```shell script
$ rabbitmqadmin get queue='hello'
```

![rabbit_7](https://github.com/benli6/ben_sqld-5_storage_systems/blob/main/screenshots/ben_rabbit_7.png)

*Скриншот результата работы второго скрипта на второй ноде*

![rabbit_8](https://github.com/benli6/ben_sqld-5_storage_systems/blob/main/screenshots/ben_rabbit_8.png)