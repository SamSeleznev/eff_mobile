
1. Docker-конфигурация
Создан Dockerfile для установки и настройки веб-сервера Nginx и PHP на основе официального образа PHP-FPM.
Создан файл конфигурации для Nginx, который указывает, как обрабатывать запросы и где находится корневой каталог веб-приложения.
Описали docker-compose.yml, который определяет два сервиса:  веб-приложение (web) и базу данных MySQL (db).

2. Ansible Playbook и Роли:
Создан playbook под названием site.yml, который использует две роли для автоматизации процесса развертывания.
Роль docker-setup устанавливает Docker и Docker Compose на удаленном сервере.
Роль app-setup копирует необходимые файлы для нашего веб-приложения на удаленный сервер и запускает контейнеры с помощью docker-compose.

3. Развертывание на удаленном сервере:
Создан Terraform конфиг описывающий инфраструктуру удаленного сервера на aws, также создан CI/CD пайплайн в Github Action запускающий Terraform конфиг который разворачивает удаленный сервер, после чего происходит деплой веб-приложения и базы данных с помощью Ansible
