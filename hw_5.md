Домашняя работа Zabbix/Alerting

## Задание

Необходимо сформировать скрипт генерирующий метрики формата:
- otus_important_metrics[metric1]
- otus_important_metrics[metric2]
- otus_important_metrics[metric3]
  
С рандомным значение от 0 до 100

Создать правила LLD для обнаружения этих метрик и автоматического добавления триггеров. Триггер должен срабатывать тогда когда значение больше или равно 95.

Реализовать автоматическую отправку уведомлений в телеграмм канал.

В качестве результаты выполнения дз Вы должны предоставить скрипт генерации метрик, скриншоты графиков полученных метрик, ссылку на телеграмм канал с уже отпраленными уведомлениями.


## Решение

Послеовательность действий была такая:
1. Создать скрипт
2. Создать шаблон
3. В шаблоне создать элемент (item), который станет основным (родительским) для прототипов
4. Создать подчиненный прототип элементы (item prototype)
5. Создать подчиненный триггер, связанный с прототипом элемента из п. 4
6. Настроить пользователя для получения алертов. Бот и чат уже есть из прошлых ДЗ.
7. Убедиться, что все работает, наделать скриншотов и оформить страчку на GitHub.

## Скриншоты подтверждения

### Скрипт

`from random import randrange
import json
def get_numbers():
    metric1 = randrange(0,101)
    metric2 = randrange(0,101)
    metric3 = randrange(0,101)

    json_result = [
        {"metric_name":"metric1", "metric_value":metric1 },
        {"metric_name":"metric2", "metric_value":metric2 },
        {"metric_name":"metric3", "metric_value":metric3 }
    ]
    return json.dumps(json_result)
if __name__ == "__main__":
    print(get_numbers())`

![Скрипт](hw_5/01_python_script.png)


### Шаблон

![Шаблон](hw_5/02_template.png)

### Основной элемент шаблона

![Основной элемент шаблона](hw_5/03_template_main_item.png)

### Макрос шаблона
![Макрос шаблона](hw_5/04_template_macro.png)

### Правило обнаружения (discovery)
![Правило обнаружения (discovery)](hw_5/05_discovery_rule.png)

### Предобработка элемента данных 
![Предобработка элемента данных](hw_5/06_item_prototype_preprocessing.png)


### Макрос LLD
![Макрос LLD](hw_5/07_discovery_rules_lld_macro.png)


### Прототип элемента данных
![Прототип элемента данных](hw_5/08_item_prototype.png)


### Прототип триггера
![Прототип триггера](hw_5/09_trigger_prototype.png)


### График для metric1
![График для metric1](hw_5/010_metric1_graph.png)


### График для metric2
![График для metric2](hw_5/011_metric2_graph.png)


### График для metric3
![График для metric3](hw_5/012_metric3_graph.png)


### Оповещения в телеграмм
![Оповещения в телеграмм](hw_5/013_telegram_alerts.png)
