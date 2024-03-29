## Разобрать каждое требование на составляющие (актор, команда, событие, query). Определить, как все бизнес цепочки будут выглядеть и на какие шаги они будут разбиваться

Синие блоки - это команды, зеленые это события.

![Flowchart](https://user-images.githubusercontent.com/23387046/193464411-97b3ef74-d964-44c5-920d-07743515d7f3.png)


- Просмотр списка задач для каждого попуга (query)

- Просмотр аналитики для попугов админов (query)

- Просмотр баланса для попугов (query)


## Построить модель данных для системы и модель доменов

![aTES current](https://user-images.githubusercontent.com/23387046/193459879-53bab04e-4c87-44af-9c61-5637d2ec1bba.png)

## Определить, какие общие данные нужны для разных доменов и как связаны данные между разными доменами
Общие данные помечены на диаграмме пунктирными линниями. Для каждого сервиса нужен account (ид, роль). Для accounting нужны еще и таски.

## Разобраться, какие сервисы, кроме тудушника, будут в нашей системе и какие между ними могут быть связи
Сервисы:

**Auth service**

**Task service**

**Accounting service**

**Notification service**

Сервис аналитики решил сделать внутри аккаунтинга.

Запросы от UI к нашим сервисам будут сихронные. Между сервисами все запросы будут асинхронными, потому что не так критично дожидаться результата выполнения команды. Задержка 
в данном случае приемлима.

## Выписать все CUD события и какие данные нужны для этих событий, которые необходимы для работы системы

| Событие  | Продюсер | Консумер |
| ------------- | ------------- | ------------- |
| CUD for Account	Auth  | Auth  | Task, Accounting, Notification |
| CUD for Task  | Task  | Accounting |

На этом судьба попугов не предрешена, эта схема будет обновляться.
