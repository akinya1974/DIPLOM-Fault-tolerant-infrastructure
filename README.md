# DIPLOM-Fault-tolerant-infrastructure


## Сайт

1. `Создал две машины.`

![Link](https://github.com/akinya1974/DIPLOM-Fault-tolerant-infrastructure/blob/main/JPG/САЙТ/1.1%20Создал%20две%20машины.jpg)

2. `Создал сервер-1.`

![Link](https://github.com/akinya1974/DIPLOM-Fault-tolerant-infrastructure/blob/main/JPG/САЙТ/1.2%20Создал%20сервер-1.jpg)


3. `Создал сервер-2.`

![Link](https://github.com/akinya1974/DIPLOM-Fault-tolerant-infrastructure/blob/main/JPG/САЙТ/1.3%20Создал%20сервер-2.jpg)

4. `Создал целевую группу.`

![Link](https://github.com/akinya1974/DIPLOM-Fault-tolerant-infrastructure/blob/main/JPG/САЙТ/1.4%20Создал%20целевую%20группу.jpg)

5. `Создал группу бэкендов.`

![Link](https://github.com/akinya1974/DIPLOM-Fault-tolerant-infrastructure/blob/main/JPG/САЙТ/1.5%20Создал%20%20группу%20бэкендов.jpg)

6. `Создал роутер.`

![Link](https://github.com/akinya1974/DIPLOM-Fault-tolerant-infrastructure/blob/main/JPG/САЙТ/1.6%20Создал%20%20роутер.jpg)

7. `Создал балансировщик.`

![Link](https://github.com/akinya1974/DIPLOM-Fault-tolerant-infrastructure/blob/main/JPG/САЙТ/1.7%20Создал%20%20балансировщик.jpg)

8. `Протестировал сайт.`

![Link](https://github.com/akinya1974/DIPLOM-Fault-tolerant-infrastructure/blob/main/JPG/САЙТ/1.8%20Протестировал%20Сайт.jpg)



## Мониторинг


1. `Создал машину с Zabbix сервером и установил Zabbix-agent2 на оба сервера, установил подключение их друг к другу.`

![Link](hhttps://github.com/akinya1974/DIPLOM-Fault-tolerant-infrastructure/blob/main/JPG/МОНИТОРИНГ/Zabbix-hosts.jpg)

2. `Настроил темплейты к группе серверов и настроил дашборды.`

![Link](https://github.com/akinya1974/DIPLOM-Fault-tolerant-infrastructure/blob/main/JPG/МОНИТОРИНГ/2.1%20Создал%20мониторинг%20Zabbix.jpg)


## Логи


1. `Создал машину с Elastic и Kibana, установил filebeat на все сервера, сконфигурировал подключение их друг к другу и отправку логов Nginx.`

![Link](https://github.com/akinya1974/DIPLOM-Fault-tolerant-infrastructure/blob/main/JPG/ЛОГИ/ELASTIK-KIBANA.jpg)


## Сеть

1. `Создал публичную и приватную сеть, группы безопасности, настроил правила, подключил машины к данным группам.`

![Link](https://github.com/akinya1974/DIPLOM-Fault-tolerant-infrastructure/blob/main/JPG/СЕТЬ/Группа-публичная.jpg)


![Link](https://github.com/akinya1974/DIPLOM-Fault-tolerant-infrastructure/blob/main/JPG/СЕТЬ/Группа-приват.jpg)


![Link](https://github.com/akinya1974/DIPLOM-Fault-tolerant-infrastructure/blob/main/JPG/СЕТЬ/Группы%20безопасности.jpg)


![Link](https://github.com/akinya1974/DIPLOM-Fault-tolerant-infrastructure/blob/main/JPG/СЕТЬ/Балансировщик.jpg)


![Link](https://github.com/akinya1974/DIPLOM-Fault-tolerant-infrastructure/blob/main/JPG/СЕТЬ/Сервер1.jpg)


![Link](https://github.com/akinya1974/DIPLOM-Fault-tolerant-infrastructure/blob/main/JPG/СЕТЬ/Сервер2.jpg)


![Link](https://github.com/akinya1974/DIPLOM-Fault-tolerant-infrastructure/blob/main/JPG/СЕТЬ/Сервера%20elastic_kibana.jpg)


![Link](https://github.com/akinya1974/DIPLOM-Fault-tolerant-infrastructure/blob/main/JPG/СЕТЬ/Сервера%20zabbix.jpg)


![Link](https://github.com/akinya1974/DIPLOM-Fault-tolerant-infrastructure/blob/main/JPG/СЕТЬ/Сети.jpg)


2. `Создать bastion host к сожалению не получилось, поскольку по инструкции на шаге создания виртуальной машины, необходимо было к ней добавить две сети, внешнюю и внутреннюю, однако при ее создании яндекс не дал создать вторую сеть, такой кнопки, как было указано в инструкции вообще не было, наверное в связи с ограничениями и квотами!!! Скрины прилагаются)`


![Link](https://github.com/akinya1974/DIPLOM-Fault-tolerant-infrastructure/blob/main/JPG/Создание%20бастиооной%20машины%20инструкция.jpg)


![Link](https://github.com/akinya1974/DIPLOM-Fault-tolerant-infrastructure/blob/main/JPG/Создание%20бастиооной%20машины.jpg)


## Резервное копирование

1. `Создал snapshot дисков всех ВМ. Ограничил время жизни snaphot в неделю. Сами snaphot настроил на ежедневное копирование.`

![Link](https://github.com/akinya1974/DIPLOM-Fault-tolerant-infrastructure/blob/main/JPG/ДИСКИ/Снимки%20дисков.jpg)


![Link](https://github.com/akinya1974/DIPLOM-Fault-tolerant-infrastructure/blob/main/JPG/ДИСКИ/Расписание%20снимков%20дисков.jpg)