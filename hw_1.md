# Задание

**Установка и настройка Prometheus, использование exporters, настройка алертов**

**Цель:**
Установить и настроить Prometheus.
Результатом выполнения данного дз будет являться публичный репозиторий в системе контроля версий (Github, Gitlab, etc.) в котором будет находится Readme с описание выполненых действий. Файлы конфигурации prometheus и alertmanager должны находится в директории GAP-1.


** Описание / Пошаговая инструкция выполнения домашнего задания:**
На виртуальной машине установите любую open source CMS которая включает в себя следующие компоненты: nginx, php-fpm, database (MySQL or Postgresql)
На этой же виртуальной машине установите Prometheus exporters для сбора метрик со всех компонентов системы (начиная с VM и заканчивая DB, не забудьте про blackbox exporter который будет проверять доступность вашей CMS)
На этой же или дополнительной виртуальной машине установите Prometheus задачей которого будет раз в 5 секунд собирать метрики с экспортеров
Задание со звездочкой 1 (повышенная сложность) - на VM с установленной CMS слишком много “портов экспортеров торчит наружу” и они доступны всем, попробуй настроить доступ только по одному и добавить авторизацию
Если вы выполнили задание со звездочкой номер 1 то - добавить SSL =)
В качестве результата дз принимаются - файл конфигурации Prometheus

**Критерии оценки:**
0 баллов - задание не выполнено
1 балл - задание выполнено успешно

**Рекомендуем сдать до: 16.07.2023**


# Решение
1. Установил Virtualbox + Ubuntu Server 22.04
2. Установил Docker, docker-compose, git, zsh и др. для удобства работы. 

