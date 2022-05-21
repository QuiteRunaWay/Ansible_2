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

![image](https://user-images.githubusercontent.com/92969676/169652442-dd6da0b4-fea8-4b39-9a8f-a811995df2e3.png)

### 5. На основе tasks из старого playbook заполните новую role. Разнесите переменные между `vars` и `default`. 

#### Ответ:

Разнёс:

vars:

![image](https://user-images.githubusercontent.com/92969676/169652654-ec25ecdb-a5e4-4c7e-b264-53d7e5906a0e.png)

Решил для себя сделать 1 параметр, это версия Vector, которую пользователь не может переопределять, значит её в vars помещаем, а всё остальное в defaults:

![image](https://user-images.githubusercontent.com/92969676/169652687-e125b108-a252-4b68-bc02-7e7fa8822b1e.png)

### 6. Перенести нужные шаблоны конфигов в `templates`.

#### Ответ:

Перенёс:

![image](https://user-images.githubusercontent.com/92969676/169652717-d38cf914-c076-40ff-9c6e-049389223a57.png)

### 7. Описать в `README.md` обе роли и их параметры.

#### Ответ:

### 8. Повторите шаги 3-6 для lighthouse. Помните, что одна роль должна настраивать один продукт.
#### Ответ:
### 9. Выложите все roles в репозитории. Проставьте тэги, используя семантическую нумерацию Добавьте roles в `requirements.yml` в playbook.
#### Ответ:
### 10. Переработайте playbook на использование roles. Не забудьте про зависимости lighthouse и возможности совмещения `roles` с `tasks`.
#### Ответ:
### 11. Выложите playbook в репозиторий.
#### Ответ:
### 12. В ответ приведите ссылки на оба репозитория с roles и одну ссылку на репозиторий с playbook.

---

### Как оформить ДЗ?

Выполненное домашнее задание пришлите ссылкой на .md-файл в вашем репозитории.

---
