# YooKassa ASync API Python Client Library

[![Build Status](https://travis-ci.org/yoomoney/yookassa-sdk-python.svg?branch=master)](https://travis-ci.org/yoomoney/yookassa-sdk-python)
[![Latest Stable Version](https://img.shields.io/pypi/v/yookassa-async.svg)](https://pypi.org/project/yookassa-async/)
[![Total Downloads](https://img.shields.io/pypi/dm/yookassa-async.svg)](https://pypi.org/project/yookassa-async/)
[![License](https://img.shields.io/pypi/l/yookassa-async.svg)](https://git.yoomoney.ru/projects/SDK/repos/yookassa-sdk-python)

Russian | [English](README.en.md)

Клиент для работы с платежами по [API ЮKassa](https://yookassa.ru/developers/api)
Подходит тем, у кого способ подключения к ЮKassa называется API.

Асинхронная версия.

## Требования

1. Python >=3.7
2. pip

## Установка
### C помощью pip

1. Установите pip.
2. В консоли выполните команду
```bash
pip install --upgrade yookassa
```

### С помощью easy_install
1. Установите easy_install.
2. В консоли выполните команду
```bash
easy_install --upgrade yookassa
```

### Вручную

1. В консоли выполните команды:
```bash
wget https://pypi.python.org/packages/5a/be/5eafdfb14aa6f32107e9feb6514ca1ad3fe56f8e5ee59d20693b32f7e79f/yookassa-1.0.0.tar.gz#md5=46595279b5578fd82a199bfd4cd51db2
tar zxf yookassa-1.0.0.tar.gz
cd yookassa-1.0.0
python setup.py install
```

## Начало работы

1. Импортируйте модуль
```python
import yookassa
```
2. Установите данные для конфигурации
```python
from yookassa import Configuration

Configuration.configure('<Идентификатор магазина>', '<Секретный ключ>')
```

или

```python
from yookassa import Configuration

Configuration.account_id = '<Идентификатор магазина>'
Configuration.secret_key = '<Секретный ключ>'
```

или через oauth

```python
from yookassa import Configuration

Configuration.configure_auth_token('<Oauth Token>')
```

Если вы согласны участвовать в развитии SDK, вы можете передать данные о вашем фреймворке, cms или модуле:
```python
from yookassa import Configuration
from yookassa.domain.common.user_agent import Version

Configuration.configure('<Идентификатор магазина>', '<Секретный ключ>')
Configuration.configure_user_agent(
    framework=Version('Django', '2.2.3'),
    cms=Version('Wagtail', '2.6.2'),
    module=Version('Y.CMS', '0.0.1')
)
```

3. Вызовите нужный метод API. [Подробнее в документации к API ЮKassa](https://yookassa.ru/developers/api)

## Примеры использования SDK

#### [Настройки SDK API ЮKassa](./docs/examples/01-configuration.md)
* [Аутентификация](./docs/examples/01-configuration.md#Аутентификация)
* [Статистические данные об используемом окружении](./docs/examples/01-configuration.md#Статистические-данные-об-используемом-окружении)
* [Получение информации о магазине](./docs/examples/01-configuration.md#Получение-информации-о-магазине)
* [Работа с Webhook](./docs/examples/01-configuration.md#Работа-с-Webhook)
* [Входящие уведомления](./docs/examples/01-configuration.md#Входящие-уведомления)

#### [Работа с платежами](./docs/examples/02-payments.md)
* [Запрос на создание платежа](./docs/examples/02-payments.md#Запрос-на-создание-платежа)
* [Запрос на создание платежа через билдер](./docs/examples/02-payments.md#Запрос-на-создание-платежа-через-билдер)
* [Запрос на частичное подтверждение платежа](./docs/examples/02-payments.md#Запрос-на-частичное-подтверждение-платежа)
* [Запрос на отмену незавершенного платежа](./docs/examples/02-payments.md#Запрос-на-отмену-незавершенного-платежа)
* [Получить информацию о платеже](./docs/examples/02-payments.md#Получить-информацию-о-платеже)
* [Получить список платежей с фильтрацией](./docs/examples/02-payments.md#Получить-список-платежей-с-фильтрацией)

#### [Работа с возвратами](./docs/examples/03-refunds.md)
* [Запрос на создание возврата](./docs/examples/03-refunds.md#Запрос-на-создание-возврата)
* [Запрос на создание возврата через билдер](./docs/examples/03-refunds.md#Запрос-на-создание-возврата-через-билдер)
* [Получить информацию о возврате](./docs/examples/03-refunds.md#Получить-информацию-о-возврате)
* [Получить список возвратов с фильтрацией](./docs/examples/03-refunds.md#Получить-список-возвратов-с-фильтрацией)

#### [Работа с чеками](./docs/examples/04-receipts.md)
* [Запрос на создание чека](./docs/examples/04-receipts.md#Запрос-на-создание-чека)
* [Запрос на создание чека через билдер](./docs/examples/04-receipts.md#Запрос-на-создание-чека-через-билдер)
* [Получить информацию о чеке](./docs/examples/04-receipts.md#Получить-информацию-о-чеке)
* [Получить список чеков с фильтрацией](./docs/examples/04-receipts.md#Получить-список-чеков-с-фильтрацией)
