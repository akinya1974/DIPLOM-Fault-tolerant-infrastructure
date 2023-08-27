# DIPLOM-Fault-tolerant-infrastructure


SERVER1  http://158.160.28.27

SERVER2  http://158.160.106.254

ZABBIX   http://158.160.11.222

KIBANA   http://84.252.136.192
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

![Link](https://github.com/akinya1974/DIPLOM-Fault-tolerant-infrastructure/blob/main/JPG/МОНИТОРИНГ/Zabbix-hosts.jpg)


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

![Link](https://github.com/akinya1974/DIPLOM-Fault-tolerant-infrastructure/blob/main/JPG/ДИСКИ/Снимки%20дисков-new.jpg)


![Link](https://github.com/akinya1974/DIPLOM-Fault-tolerant-infrastructure/blob/main/JPG/ДИСКИ/Расписание%20снимков%20дисков.jpg)


## Остаток

![Link](https://github.com/akinya1974/DIPLOM-Fault-tolerant-infrastructure/blob/main/JPG/ОСТАТОК.jpg)


## Terraform file (Пример)

```
terraform {
  required_providers {
    yandex = {
      source  = "yandex-cloud/yandex"
      version = ">= 0.47.0"
    }
  }
}

provider "yandex" {
  zone = "ru-central1-a"
}

variable "folder_id" {
  description = "ID of the folder where resources will be created"
  default     = "<folder_ID>"
}

resource "yandex_iam_service_account" "ig-sa" {
  name        = "ig-sa"
}

resource "yandex_resourcemanager_folder_iam_member" "editor" {
  folder_id = var.folder_id
  role      = "editor"
  member    = "serviceAccount:${yandex_iam_service_account.ig-sa.id}"
}

resource "yandex_vpc_network" "network-1" {
  name = "network1"
}

resource "yandex_vpc_subnet" "subnet-1" {
  name           = "subnet1"
  zone           = "ru-central1-a"
  network_id     = yandex_vpc_network.network-1.id
  v4_cidr_blocks = ["192.168.1.0/24"]
}

resource "yandex_vpc_subnet" "subnet-2" {
  name           = "subnet2"
  zone           = "ru-central1-b"
  network_id     = yandex_vpc_network.network-1.id
  v4_cidr_blocks = ["192.168.2.0/24"]
}

resource "yandex_vpc_subnet" "subnet-3" {
  name           = "subnet3"
  zone           = "ru-central1-c"
  network_id     = yandex_vpc_network.network-1.id
  v4_cidr_blocks = ["192.168.3.0/24"]
}

resource "yandex_vpc_security_group" "alb-sg" {
  name        = "alb-sg"
  network_id  = yandex_vpc_network.network-1.id

  egress {
    protocol       = "ANY"
    description    = "any"
    v4_cidr_blocks = ["0.0.0.0/0"]
  }

  ingress {
    protocol       = "TCP"
    description    = "ext-http"
    v4_cidr_blocks = ["0.0.0.0/0"]
    port           = 80
  }

  ingress {
    protocol       = "TCP"
    description    = "ext-https"
    v4_cidr_blocks = ["0.0.0.0/0"]
    port           = 443
  }

  ingress {
    protocol       = "TCP"
    description    = "healthchecks"
    v4_cidr_blocks = ["198.18.235.0/24", "198.18.248.0/24"]
    port           = 30080
  }
}

resource "yandex_vpc_security_group" "alb-vm-sg" {
  name        = "alb-vm-sg"
  network_id  = yandex_vpc_network.network-1.id

  ingress {
    protocol          = "TCP"
    description       = "balancer"
    security_group_id = yandex_vpc_security_group.alb-sg.id
    port              = 80
  }

  ingress {
    protocol       = "TCP"
    description    = "ssh"
    v4_cidr_blocks = ["0.0.0.0/0"]
    port           = 22
  }
}

resource "yandex_compute_image" "lemp" {
  source_family = "lemp"
}

resource "yandex_compute_instance_group" "alb-vm-group" {
  name               = "alb-vm-group"
  folder_id          = var.folder_id
  service_account_id = yandex_iam_service_account.ig-sa.id
  instance_template {
    platform_id        = "standard-v2"
    service_account_id = yandex_iam_service_account.ig-sa.id
    resources {
      core_fraction = 5
      memory        = 1
      cores         = 2
    }

    boot_disk {
      mode = "READ_WRITE"
      initialize_params {
        image_id = yandex_compute_image.lemp.id
        type     = "network-hdd"
        size     = 3
      }
    }

    network_interface {
      network_id         = yandex_vpc_network.network-1.id
      subnet_ids         = [yandex_vpc_subnet.subnet-1.id,yandex_vpc_subnet.subnet-2.id,yandex_vpc_subnet.subnet-3.id]
      nat                = true
      security_group_ids = [yandex_vpc_security_group.alb-vm-sg.id]
    }

    metadata = {
      user-data = "#cloud-config\nusers:\n  - name: <username>\n    groups: sudo\n    shell: /bin/bash\n    sudo: ['ALL=(ALL) NOPASSWD:ALL']\n    ssh-authorized-keys:\n      - ${file("<path_to_the_public_SSH_key>")}"
    }
  }

  scale_policy {
    fixed_scale {
      size = 3
    }
  }

  allocation_policy {
    zones = ["ru-central1-a", "ru-central1-b", "ru-central1-c"]
  }

  deploy_policy {
    max_unavailable = 1
    max_expansion   = 0
  }

  application_load_balancer {
    target_group_name = "alb-tg"
  }
}

resource "yandex_alb_backend_group" "alb-bg" {
  name                     = "alb-bg"

  http_backend {
    name                   = "backend-1"
    port                   = 80
    target_group_ids       = [yandex_compute_instance_group.alb-vm-group.application_load_balancer.0.target_group_id]
    healthcheck {
      timeout              = "10s"
      interval             = "2s"
      healthcheck_port     = 80
      http_healthcheck {
        path               = "/"
      }
    }
  }
}

resource "yandex_alb_http_router" "alb-router" {
  name   = "alb-router"
}

resource "yandex_alb_virtual_host" "alb-host" {
  name           = "alb-host"
  http_router_id = yandex_alb_http_router.alb-router.id
  authority      = ["alb-example.com"]
  route {
    name = "route-1"
    http_route {
      http_route_action {
        backend_group_id = yandex_alb_backend_group.alb-bg.id
      }
    }
  }
}

resource "yandex_alb_load_balancer" "alb-1" {
  name               = "alb-1"
  network_id         = yandex_vpc_network.network-1.id
  security_group_ids = [yandex_vpc_security_group.alb-sg.id]

  allocation_policy {
    location {
      zone_id   = "ru-central1-a"
      subnet_id = yandex_vpc_subnet.subnet-1.id
    }

    location {
      zone_id   = "ru-central1-b"
      subnet_id = yandex_vpc_subnet.subnet-2.id
    }

    location {
      zone_id   = "ru-central1-c"
      subnet_id = yandex_vpc_subnet.subnet-3.id
    }
  }

  listener {
    name = "alb-listener"
    endpoint {
      address {
        external_ipv4_address {
        }
      }
      ports = [ 80 ]
    }
    http {
      handler {
        http_router_id = yandex_alb_http_router.alb-router.id
      }
    }
  }
}

resource "yandex_dns_zone" "alb-zone" {
  name        = "alb-zone"
  description = "Public zone"
  zone        = "alb-example.com."
  public      = true
}

resource "yandex_dns_recordset" "rs-1" {
  zone_id = yandex_dns_zone.alb-zone.id
  name    = "alb-example.com."
  ttl     = 600
  type    = "A"
  data    = [yandex_alb_load_balancer.alb-1.listener[0].endpoint[0].address[0].external_ipv4_address[0].address]
}

resource "yandex_dns_recordset" "rs-2" {
  zone_id = yandex_dns_zone.alb-zone.id
  name    = "www"
  ttl     = 600
  type    = "CNAME"
  data    = ["alb-example.com"]
}
```