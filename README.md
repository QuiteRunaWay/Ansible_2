# Домашнее задание к занятию "08.02 Работа с Playbook"

## Подготовка к выполнению

1. Создайте свой собственный (или используйте старый) публичный репозиторий на github с произвольным именем.
2. Скачайте [playbook](./playbook/) из репозитория с домашним заданием и перенесите его в свой репозиторий.
3. Подготовьте хосты в соответствии с группами из предподготовленного playbook.

## Основная часть

1. Приготовьте свой собственный inventory файл `prod.yml`.
### Ответ: файл подготовлен. В качестве ВМ сразу будем использовать ВМ в Yandex Cloud.

![image](https://user-images.githubusercontent.com/92969676/167303761-973ed1fe-a9b4-49dd-b33b-0fcaf207bb08.png)

2. Допишите playbook: нужно сделать ещё один play, который устанавливает и настраивает [vector](https://vector.dev).
### Ответ:

![image](https://user-images.githubusercontent.com/92969676/167306257-7c9ea19c-8bf5-41e2-ab66-5155919c19f4.png)



3. При создании tasks рекомендую использовать модули: `get_url`, `template`, `unarchive`, `file`.
### Ответ:

4. Tasks должны: скачать нужной версии дистрибутив, выполнить распаковку в выбранную директорию, установить vector.
### Ответ:

![image](https://user-images.githubusercontent.com/92969676/167307210-73b78cfd-581d-401f-9e4d-d80acac24693.png)

5. Запустите `ansible-lint site.yml` и исправьте ошибки, если они есть.
### Ответ:

Ошибки были, исправил. 

![image](https://user-images.githubusercontent.com/92969676/167308099-6edef02f-4397-40b5-9527-cc2a37ad7fbb.png)


6. Попробуйте запустить playbook на этом окружении с флагом `--check`.
### Ответ:

7. Запустите playbook на `prod.yml` окружении с флагом `--diff`. Убедитесь, что изменения на системе произведены.
### Ответ:

8. Повторно запустите playbook с флагом `--diff` и убедитесь, что playbook идемпотентен.
### Ответ:

9. Подготовьте README.md файл по своему playbook. В нём должно быть описано: что делает playbook, какие у него есть параметры и теги.
### Ответ:

10. Готовый playbook выложите в свой репозиторий, поставьте тег `08-ansible-02-playbook` на фиксирующий коммит, в ответ предоставьте ссылку на него.

