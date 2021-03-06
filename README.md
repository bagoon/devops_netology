# Домашнее задание к занятию "5.1. Введение в виртуализацию. Типы и функции гипервизоров. Обзор рынка вендоров и областей применения."
## Как сдавать задания

Обязательными к выполнению являются задачи без указания звездочки. Их выполнение необходимо для получения зачета и диплома о профессиональной переподготовке.

Задачи со звездочкой (*) являются дополнительными задачами и/или задачами повышенной сложности. Они не являются обязательными к выполнению, но помогут вам глубже понять тему.
Домашнее задание выполните в файле readme.md в github репозитории. В личном кабинете отправьте на проверку ссылку на .md-файл в вашем репозитории.

Любые вопросы по решению задач задавайте в чате Slack.

---


## Задача 1

Вкратце опишите, как вы поняли - в чем основное отличие полной (аппаратной) виртуализации, паравиртуализации и виртуализации на основе ОС.

Полная или аппаратная виртуализация сразу может использовать аппаратные ресурсы сервера и не нуждаетя в операционной системе для управления виртуальными машинами.
Паравиртуализация - программное обеспечение, использующее операционную систему для разделения ресурсов между виртуальными машинами.
Виртуализация на основе ОС позволяет запускать изолированные контейнеры на хосте, которые по сути являются небольшими отдельными копиями хостовой ОС.


## Задача 2

Выберите тип один из вариантов использования организации физических серверов, 
в зависимости от условий использования.

Организация серверов:
- физические сервера
- паравиртуализация
- виртуализация уровня ОС

Условия использования:

- Высоконагруженная база данных, чувствительная к отказу
- Различные web-приложения
- Windows системы для использования Бухгалтерским отделом 
- Системы, выполняющие высокопроизводительные расчеты на GPU

Опишите, почему вы выбрали к каждому целевому использованию такую организацию.

1. Высоконагруженная база данных, чувствительная к отказу - (Физические сервера):  высокая производительность, 
отказоустойчивость.
2. Различные web-приложения - (Виртуализация уровня ОС): простота маштабируемости при увеличении нагрузки на приложения.
3. Windows системы для использования Бухгалтерским отделом - (паравиртуализация): простота настройки и обслуживания.
4. Системы, выполняющие высокопроизводительные расчеты на GPU - (Физические сервера): высокая производительность, 
отказоустойчивость.

## Задача 3

Выберите подходящую систему управления виртуализацией для предложенного сценария. Детально опишите ваш выбор.

Сценарии:

- 100 виртуальных машин на базе Linux и Windows, общие задачи, нет особых требований. Преимущественно Windows based инфраструктура,
требуется реализация программных балансировщиков нагрузки, репликации данных и автоматизированного механизма создания резервных копий.
- Требуется наиболее производительное бесплатное open source решение для виртуализации небольшой (20-30 серверов) 
инфраструктуры на базе Linux и Windows виртуальных машин.
- Необходимо бесплатное, максимально совместимое и производительное решение для виртуализации Windows инфраструктуры.
- Необходимо рабочее окружение для тестирования программного продукта на нескольких дистрибутивах Linux.

1. VMWare, высокая производительность с готовыми средствами балансировщиков нагрузки, репликации, созданию резервных копий, 
совместимость с различными ОС.
2. KVM, наиболее производительное и бесплатное решение.
3. Hyper-V, бесплатное решение с хорошей производительностью и совместимость с Windows инфраструктурой.
4. KVM, отлично совместим с большим количеством дистрибутивов Linux.

## Задача 4
Опишите возможные проблемы и недостатки гетерогенной среды виртуализации (использования нескольких систем управления 
виртуализацией одновременно) и что необходимо сделать для минимизации этих рисков и проблем. Если бы у вас был выбор,
то создавали бы вы гетерогенную среду или нет? Мотивируйте ваш ответ примерами.

- сложность администрирования;
- необходимое наличие высококвалифицированных специалистов;
- повышенный риск отказа и недоступности;
- завышенная стоимость обслуживания;

Действия для минимизации рисков и проблем:
- если гетерогенность не оправдана, то рассмотреть возможность отказа от нее;
- если она оправдана, то часть инфраструктуры можно перенести на IaaS (AWS), а саму инфраструктуру вывести в IaC (Terraform);
- максимальное автоматизировать развертывание и тестирование инфраструктуры, чтобы она была единая.
