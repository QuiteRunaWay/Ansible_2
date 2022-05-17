# Домашнее задание к занятию "08.03 Использование Yandex Cloud"

## Подготовка к выполнению

1. Подготовьте в Yandex Cloud три хоста: для `clickhouse`, для `vector` и для `lighthouse`.

#### Хосты подготовлены:

![image](https://user-images.githubusercontent.com/92969676/168757814-9c342fc4-c2bc-4b6f-b991-2d5763d54fc6.png)


## Основная часть

1. Допишите playbook: нужно сделать ещё один play, который устанавливает и настраивает lighthouse.
#### Ответ: дописал:

![image](https://user-images.githubusercontent.com/92969676/168758335-9e0d4f90-96a9-4658-b30b-786f7ff2cf1a.png)

2. При создании tasks рекомендую использовать модули: `get_url`, `template`, `yum`, `apt`.
#### Ответ: 

Для создания tasks тспользовал ```git``` для вычитки необходимых для установки файлов из репозитория http://github.com/VKCOM/lighthouse.git.
  ```template``` использовали для дальнейшей настройки ```lighthouse``` в связки с ```nginx```, это шаблон ```lighthouse.conf.j2```, ```yum (ansible.builtin.yum)``` использовали при установки репозитория ```epel-release``` и непосредственно самого ```nginx```.

3. Tasks должны: скачать статику lighthouse, установить nginx или любой другой webserver, настроить его конфиг для открытия lighthouse, запустить webserver.
#### Ответ: 

Tasks устанавливает окружение epel-releas, устанавливает Nginx по умолчанию и заменяет конфиг тем, который мы ему даем ```nginx.conf.j2``` (конфиг стандартный, только убрал лишнее). Далее Ставим Lighthouse. Далее так же конфиг подсовываем в конфиг Nginx:

![image](https://user-images.githubusercontent.com/92969676/168788132-3f5bfb8c-ec86-41fc-83a3-ff23dc64d5df.png)

Установка Nginx:

![image](https://user-images.githubusercontent.com/92969676/168758866-ac8b7bba-0168-48d9-b9bf-a68a95e31bba.png)

Установка Lighthouse:

![image](https://user-images.githubusercontent.com/92969676/168758994-1ac7ddc5-d39c-4343-8927-766b8df055af.png)

4. Приготовьте свой собственный inventory файл `prod.yml`.

#### Ответ: файл подготовлен, в нем установка Nginx, Lighthouse, Clickhouse и Vector

![image](https://user-images.githubusercontent.com/92969676/168759140-0254668c-ca84-4a83-9664-4c507da2a1b2.png)



5. Запустите `ansible-lint site.yml` и исправьте ошибки, если они есть.

#### Ответ: 

6. Попробуйте запустить playbook на этом окружении с флагом `--check`.

#### Ответ: 

![image](https://user-images.githubusercontent.com/92969676/168760485-54779a3e-980a-44eb-aeac-8e4aa9099963.png)

![image](https://user-images.githubusercontent.com/92969676/168760604-6297a6a1-b75f-464a-9c94-265a220ac3f7.png)


7. Запустите playbook на `prod.yml` окружении с флагом `--diff`. Убедитесь, что изменения на системе произведены.

#### Ответ: 

8. Повторно запустите playbook с флагом `--diff` и убедитесь, что playbook идемпотентен.

#### Ответ: 

9. Подготовьте README.md файл по своему playbook. В нём должно быть описано: что делает playbook, какие у него есть параметры и теги.

#### Ответ: 

10. Готовый playbook выложите в свой репозиторий, поставьте тег `08-ansible-03-yandex` на фиксирующий коммит, в ответ предоставьте ссылку на него.

Ссылка на commit: https://github.com/QuiteRunaWay/Ansible_2/releases/tag/08-ansible-03-yandex
