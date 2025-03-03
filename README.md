# Домашнее задание " Пользователи и группы. Авторизация и аутентификация "

*Задание: Запретить всем пользователям кроме группы admin логин в выходные (суббота и воскресенье), без учета праздников

Задание выполнялось на VM Ubuntu 22.04.

Playbook Ansible pam_playbook.yml:

 - создает пользователей otus, otusadm, группу admin
 - аутентификация пользователей ssh проходит по ключу
 - копирует скрипт login.sh из текущей директории запуска ansible в папку /usr/local/bin/  на VM
 - копирует модифицированный файл sshd из текущей директории запуска ansible в папку /etc/pam.d/

Проверка использования pam и скрипта:

Отказ в доступе ssh в воскресенье для пользователя otus:

![Image alt](https://github.com/AlexndrVakulenko/homework16/blob/main/01_%D0%9D%D0%B5%D1%83%D1%81%D0%BF%D0%B5%D1%88%D0%BD%D1%8B%D0%B9_%D0%BB%D0%BE%D0%B3%D0%B8%D0%BD_otus.png)

Успешный вход  по ssh в воскресенье для пользователя otusadm:

![Image alt](https://github.com/AlexndrVakulenko/homework16/blob/main/02_%D0%A3%D1%81%D0%BF%D0%B5%D1%88%D0%BD%D1%8B%D0%B9_%D0%BB%D0%BE%D0%B3%D0%B8%D0%BD_otusadm.png)
