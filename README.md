# Домашнее задание к занятию "8.4 Работа с Roles"

## Подготовка к выполнению
1. Создайте два пустых публичных репозитория в любом своём проекте: vector-role и lighthouse-role.
2. Добавьте публичную часть своего ключа к своему профилю в github.

## Основная часть

Наша основная цель - разбить наш playbook на отдельные roles. Задача: сделать roles для clickhouse, vector и lighthouse и написать playbook для использования этих ролей. Ожидаемый результат: существуют три ваших репозитория: два с roles и один с playbook.

### 1. Создать в старой версии playbook файл `requirements.yml` и заполнить его следующим содержимым:

   ```yaml
   ---
     - src: git@github.com:AlexeySetevoi/ansible-clickhouse.git
       scm: git
       version: "1.11.0"
       name: clickhouse 
   ```
#### Ответ:

Создал файл:

![image](https://user-images.githubusercontent.com/92969676/169652043-7c87e918-979a-4702-a684-8c721468f1fe.png)

### 2. При помощи `ansible-galaxy` скачать себе эту роль.

#### Ответ: 

![image](https://user-images.githubusercontent.com/92969676/169652345-aa9a9207-dbf2-4f89-8392-5a9a7224c8ee.png)

### 4. Создать новый каталог с ролью при помощи `ansible-galaxy role init vector-role`.
#### Ответ:

Скачал, пока она пустая:

![image](https://user-images.githubusercontent.com/92969676/169804112-2139afaa-a728-4859-980d-a68a9dedf62b.png)

### 5. На основе tasks из старого playbook заполните новую role. Разнесите переменные между `vars` и `default`. 

#### Ответ:

Разнёс:

vars:

![image](https://user-images.githubusercontent.com/92969676/169804317-a1878d9c-cb50-4c62-aefc-55189b6eff13.png)

Решил для себя сделать 1 параметр, это версия Vector, которую пользователь не может переопределять, значит её в vars помещаем, а всё остальное в defaults:

![image](https://user-images.githubusercontent.com/92969676/169804272-981a50a1-ede6-4b82-a120-0c414d8ad3a1.png)


### 6. Перенести нужные шаблоны конфигов в `templates`.

#### Ответ:

Перенёс:

![image](https://user-images.githubusercontent.com/92969676/169804411-afd70a62-c226-4cbc-ab39-6b622ebc3ade.png)


### 7. Описать в `README.md` обе роли и их параметры.

#### Ответ:

### 8. Повторите шаги 3-6 для lighthouse. Помните, что одна роль должна настраивать один продукт.
#### Ответ:

var defaults:

![image](https://user-images.githubusercontent.com/92969676/169804571-2c34d415-232b-4e4d-b06d-b308c313bc21.png)

var:

![image](https://user-images.githubusercontent.com/92969676/169804656-1be953c5-2086-406c-9f97-463a604522a2.png)


templates:

![image](https://user-images.githubusercontent.com/92969676/169804801-e5115663-377a-4c30-85ee-666978aae3d6.png)

### 9. Выложите все roles в репозитории. Проставьте тэги, используя семантическую нумерацию Добавьте roles в `requirements.yml` в playbook.
#### Ответ:

Выложил

Vector-role: https://github.com/QuiteRunaWay/vector-role

Lighthouse-role: https://github.com/QuiteRunaWay/lighthouse-role

### 10. Переработайте playbook на использование roles. Не забудьте про зависимости lighthouse и возможности совмещения `roles` с `tasks`.
#### Ответ:



### 11. Выложите playbook в репозиторий.
#### Ответ:


### 12. В ответ приведите ссылки на оба репозитория с roles и одну ссылку на репозиторий с playbook.
