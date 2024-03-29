# Пример RPA в 1С на примере автоматической отправки документов через Диадок
Внешняя обработка, демонстрирующая управление сеансом, запущенным в режиме клиента тестирования. Выполняет подключенной обработки обмена данными через Диадок и отправку исходящих документов.

## Содержание
- [Использование](#использование)
- [Требования](#требования)
- [Ссылки](#ссылки)
- [Автор](#автор)

## Использование
Перед использованием обработки необходимо:
- В макете "Настройки" указать адреса электронной почты для оповещений;
- В модуле формы обработки указать в процедуре УстановитьНастройки() токен бота и ID чата для оповещений в Telegram. Как их получить можно почитать [здесь](https://infostart.ru/1c/tools/1943735/);
- Также в том же модуле можно реализовать процедуру ЗапуститьСеансКлиентскогоПриложения(), которая должна запускать сеанс клиента тестирования.

Запускать обработку необходимо в сеансе менеджера тестирования.

В форме необходимо указать интервал времени, в котором должна работать отправка документов, и периодичность отправки в минутах.  

Что делает обработка:
- Подключается к сеансу клиента тестирования;
- Открывает обработку работы с ЭДО Диадок (она должно быть первой в списке доп. обработкок раздела Продажи);
- Выбирает период отбора документов - сегодняшний день; 
- Отмечает все документы для отправки, запускает отправку;
- Отправляет email с таблицей отправленных документов;
- Закрывает все окна.
- В случае проблем - отправляет сообщение в Telegram.
Если соединение с сеансом клиента тестирования установить не удается, то запускает его.

## Требования
Автоматизированное тестирование появилось в платформе 1С: Предприятие версии 8.3.

## Ссылки 
- [Про механизм автоматизированное тестирование на сайте 1С](https://v8.1c.ru/platforma/avtomatizirovannoe-testirovanie/)
- [Пример автоматизированного тестирования на ИТС](https://its.1c.ru/db/metod8dev/content/5011/hdoc)
- [Статья про автоматизированное тестирование на Инфостарт](https://infostart.ru/1c/articles/262904/)

## Зачем вы разработали этот проект?
- [Историю создания данной разработки рассказывал у себя в ТГ-канале](https://t.me/prosto_pro1c)

## Автор
- [Харин Владимир](https://t.me/prosto_pro1c)
