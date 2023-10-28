# ДЗ №7

## Цель: Установить beats

## Описание/Пошаговая инструкция выполнения домашнего задания:

Для успешного выполнения дз вам нужно сконфигурировать hearthbeat, filebeat и metricbeat.

Heartbeat должен проверять доступность следующих ресурсов: otus.ru, google.com.

Metricbeat должен формировать метрики на основе показателей загрузки процессора и оперативной памяти.

Filebeat должен собирать логи ssh сервера. По собственному усмотрению вы можете собирать логи других сервисов которые присутствуют в системе ^_^

В качестве результата приложите конфиги hearthbeat, filebeat и metricbeat. Скриншот полученных данных отображенных в Kibana.

# Выполнение

1. Установил deb-пакеты, настроил по мануалам с официального сайта. 

Файлы конфигов:
- [heartbeat.yml](hw_7/heartbeat.yml)
- [metricbeat.yml](hw_7/metricbeat.yml)
- [filebeat.yml](hw_7/filebeat.yml)

  ## Скриншоты


![Filebeat](hw_7/filebeat.png)

![Модули Filebeat](hw_7/filebeat-modules.png)

![Filebeat SSH](hw_7/filebeat-ssh.png)

![Heartbeat](hw_7/heartbeat.png)

![Heartbeat Kibana HTTP](hw_7/kibana-heartbeat-http.png)

![Heartbeat Kibana ICMP](hw_7/kibana-heartbeat-icmp.png)

![Metricbeat](hw_7/metricbeat.png)

