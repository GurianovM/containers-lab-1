# Отчет по практической работе №1
## Выполнил:
## Группа:
## Дата выполнения: 10.03.2026


### 1. Выполнение команды Docker
#### 1.1 Работа с образами

Поиск образов в Docker Hub
![alt text](pics/image.png)

Скачивание образа
![alt text](pics/image-1.png)

Просмотр локальных образов
![alt text](pics/image-2.png)

Просмотр истории слоев образа
![alt text](pics/image-3.png)

Удаление образа
![alt text](pics/image-4.png)

**Практическое задание**

Установка PostgresSQL:
![alt text](pics/image-5.png)

Установка golang:
![alt text](pics/image-6.png)

#### Жизненный цикл контейнеров

Запуск контейнера alpine в интерактивном режиме
![alt text](pics/image-7.png)


Запуск контейнера в фоновом режиме:
![alt text](pics/image-8.png)

Просмотр запущенных контейнеров
![alt text](pics/image-9.png)

Промотр всех контейнеров (включая остановленные)
![alt text](pics/image-10.png)

Просмотр логов контейнера
![alt text](pics/image-11.png)

Подключение к работающему контейнеру и выполнение команды
![alt text](pics/image-12.png)

Остановка контейнера
![alt text](pics/image-13.png)

Запуск остановленного контейнера
![alt text](pics/image-14.png)

Удаление контейнера
![alt text](pics/image-15.png)

**Практическое задание**
![alt text](pics/image-16.png)

#### 1.3 Работа с томами

Создание именованного тома
![alt text](pics/image-17.png)

Просмотр томов
![alt text](pics/image-18.png)

Информация о томе
![alt text](pics/image-19.png)

Запуск контейнера с томом
![alt text](pics/image-20.png)

Создание тестовой таблицы
![alt text](pics/image-21.png)

Остановка и удаление контейнера
![alt text](pics/image-22.png)

Запуск нового контейнера с тем же томом
![alt text](pics/image-23.png)

Проверка, что данные сохранились
![alt text](pics/image-24.png)

**Практическое задание**
![alt text](pics/image-25.png)
![alt text](pics/image-26.png)
Проверка в браузере:
![alt text](pics/image-27.png)

#### 1.4 Сеть в Docker

Создание сети
![alt text](pics/image-28.png)

Просмотр сетей
![alt text](pics/image-29.png)

Запуск контейнеров в одной сети
![alt text](pics/image-30.png)

Проверка связи между контейнерами
![alt text](pics/image-31.png)

**Практическое задание**
![alt text](pics/image-32.png)

#### Backend на Go
main.go
![alt text](pics/image-33.png)

go.mod
![alt text](pics/image-34.png)

#### Frontend и статика
index.html
![alt text](pics/image-35.png)

nginx.conf
![alt text](pics/image-36.png)

#### Скрипты инициализации БД
![alt text](pics/image-37.png)

#### Dockerfile для Go приложения
![alt text](pics/image-38.png)

#### Docker-compose для локальной разработки
![alt text](pics/image-39.png)

#### Создание Personal Access Token
![alt text](pics/image-40.png)

#### Настройка Secrets в репозитории

![alt text](pics/image-41.png)

#### Создание Github Actions workflow
![alt text](pics/image-42.png)

#### Текстовый docker-compose для CI

![alt text](pics/image-43.png)

### 2. Скриншоты работающего приложения

#### 2.1 Главная страница

![alt text](pics/image-44.png)

#### 2.2 Добавление пользователя

![alt text](pics/image-45.png)

#### 2.3 Список пользоватлей в БД

![alt text](pics/image-46.png)

### 3 Github Actions

#### 3.1 Успешный запуск workflow
![alt text](pics/image-47.png)

#### 3.2 Опубликованные образы в GHCR

![alt text](pics/image-48.png)

### 4. Выводы

В данной практической работы были получены навыки развертывания проекта на языке Go. В ходе работы былы развернуты PostgreSQL и nginx с помощью встроенных docker команд, а также все компоненты проекта были связаны общей сетью. Также были настроены отказоустойчивые хранилища данных - тома.

Не обошлось без трудностей. В процессе сборки проекта возникла проблема, при которой не выполнялось копирование index файла в папку static директории app. Из-за этого возникала ошибка выполнения docker-compose up.

Также в ходе практики опытным путем было выяснено, что docker крайне неустойчиво работает с путями к файлам, содержащими пробелы и кириллицу.

Также несколько раз возникали проблемы, когда требуемый для работы порт оказывался занят.