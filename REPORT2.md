# Отчет по практической работе №2
## Выполнил: GMS
## Группа: 16
## Дата выполнения: 28.03.2026


### 1. Информация о кластере

#### 1.1 Статус Minikube

Команда `minikube status`:
![alt text](pics/image.png)

Бонус: команда `kubectl --version`
![alt text](pics/image-1.png)

#### 1.2 Узлы кластера

Доступ к GHCR настроен и новая ветка в репозитории создана:
![alt text](pics/image-2.png)

Команда `kubectl get nodes -o wide`
![alt text](pics/image-3.png)

Команда `kubectl api-resources | findstr pod`
![alt text](pics/image-4.png)

Команда `kubectl api-resources | findstr deployment`
![alt text](pics/image-5.png)

Команда `kubectl config view`
![alt text](pics/image-6.png)

Команда `kubectl config current-context`
![alt text](pics/image-7.png)

### 2. Созданные ресурсы

#### 2.1 Pods

Созданный файл 01-pod-nginx.yaml
![alt text](pics/image-8.png)

Применение манифеста
![alt text](pics/image-9.png)

Просмотр подов
![alt text](pics/image-10.png)

Детальная информация
(показана лишь нижняя половина вывода, все на скриншот не поместится)
![alt text](pics/image-11.png)


Логи
![alt text](pics/image-12.png)
![alt text](pics/image-13.png)

Выполнение команд в поде
![alt text](pics/image-14.png)

Просмотр метрик
![alt text](pics/image-15.png)

Удаление пода
![alt text](pics/image-16.png)

**Самостоятельное задание:**

Созданный файл:
![alt text](pics/image-17.png)

Создание пода:
![alt text](pics/image-18.png)

Проверка состояния:
![alt text](pics/image-19.png)

Логи:
![alt text](pics/image-20.png)

##### 2.1.1 Работа с ReplicaSet

Созданный 02-replicaset-nginx.yaml
![alt text](pics/image-21.png)

##### 2.1.2 Управление ReplicaSet

Создание ReplicaSet
![alt text](pics/image-22.png)

Просмотр ReplicaSet
![alt text](pics/image-23.png)

Просмотр созданных подов
![alt text](pics/image-24.png)

Масштабирование вручную
![alt text](pics/image-25.png)

Эксперимент с самовосстановлением:

удаление пода
![alt text](pics/image-26.png)
создание нового
![alt text](pics/image-27.png)


#### 2.2 Работа с Deployment

Созданный файл 03-deployment-app.yaml
![alt text](pics/image-29.png)

Примерение манифеста
![alt text](pics/image-28.png)

Просмотр Deployment
![alt text](pics/image-30.png)
![alt text](pics/image-31.png)

Просмотр созданного ReplicaSet
![alt text](pics/image-32.png)

Просмотр подов
![alt text](pics/image-33.png)

Просмотр истории обновлений
![alt text](pics/image-34.png)

Масштабирование через Deployment
![alt text](pics/image-35.png)

Обновление образа
![alt text](pics/image-36.png)

**Самостоятельное задание**

Файл postgres-deployment.yaml
![alt text](pics/image-37.png)

Запуск подов:
![alt text](pics/image-38.png)

Проверка:
![alt text](pics/image-39.png)

Проверка логов
![alt text](pics/image-40.png)
Как и ожидалось, go-app не может подключиться к PostgreSQL.

#### 2.3 Работа с Service

Файл 04-service-postgres.yaml
![alt text](pics/image-41.png)

Файл 05-service-app.yaml
![alt text](pics/image-42.png)

Файл 06-service-nginx.yaml
![alt text](pics/image-43.png)

Создание сервисов
![alt text](pics/image-44.png)

Просмотр сервисов
![alt text](pics/image-45.png)
![alt text](pics/image-46.png)

Детальная информация
![alt text](pics/image-47.png)

Проверка DNS-резолвинга:
![alt text](pics/image-48.png)

##### 2.3.1 Полный стек приложения

Созданный файл 07-postgres-deployment.yaml:
![alt text](pics/image-49.png)

Созданный файл 08-nginx-deployment.yaml
![alt text](pics/image-50.png)

##### 2.3.2 Валидация YAML

Сухая проверка (dry-run) в Kubernetes
![alt text](pics/image-51.png)

Получение объяснение по полям
![alt text](pics/image-52.png)
![alt text](pics/image-53.png)
![alt text](pics/image-54.png)


Валидация с помощью kubeconform
![alt text](pics/image-55.png)

##### 2.3.2 Отладка приложений

Просмотр событий в кластере
![alt text](pics/image-56.png)

Просмотр логов конкретного лога
![alt text](pics/image-57.png)

Просмотр логов предыдущей инстанции
![alt text](pics/image-58.png)

Порт-форвардинг для доступа к приложению без Service
![alt text](pics/image-59.png)

Интерактивная отладка - запуск временного пода в той же сети
![alt text](pics/image-60.png)


##### 2.3.3 Мониторинг через Dashboard

Запуск дашборда
![alt text](pics/image-61.png)

##### 2.3.4 Финальный запуск и проверка

Применение всех манифестов
![alt text](pics/image-62.png)

Проверка статуса
![alt text](pics/image-63.png)

Ожидание готовности
![alt text](pics/image-64.png)

Получение URL для доступа к приложению

![alt text](pics/image-65.png)

### 3. Скриншоты работы приложения

#### 3.1 Главная страница
![alt text](pics/image-66.png)

#### 3.2 Дашборд Kubernetes

![alt text](pics/image-67.png)


#### 3.3 Результат GET /api/users

![alt text](pics/image-68.png)

### 4. Эксперименты с масштабированием

#### 4.1 Масштабирование до 5 реплик
![alt text](pics/image-69.png)

#### 4.2 Проверка распределения нагрузки

Запросы
![alt text](pics/image-70.png)

Логи
![alt text](pics/image-71.png)
![alt text](pics/image-72.png)

### 5. Github actions

данный раздел практической работы будет выполнен тогда и только тогда, когда git actions наконец соизволит начать работать при git push моего проекта


### 6. Ответы на контрольные вопросы

**1. Pod vs Deployment**

Pod - это минимальная единица запуска в Kubernetes, работает как контейнер с настройками. Если упал, самостоятельно не восстанавливается. Deployment - это контроллер, который управляет подами: следит чтобы всегда работало нужное количество реплик, умеет делать откат к предыдущей версии.

**2. Service типа ClusterIP**

Даёт стабильный внутренний IP и DNS для доступа к подам внутри кластера.

**3. Самовосстановление ReplicaSet**

ReplicaSet постоянно следит за количеством реплик подов. Если под упал или удалён - контроллер это замечает и автоматически создаёт новый под.

**4. Удаление пода PostgreSQL**

Так как postgres запущен через Deployment, под пересоздастся автоматически. Но поскольку в конфиге используется `emptyDir` как хранилище - все данные потеряются, потому что `emptyDir` живёт только пока живёт под. 

### 7. Вывод

Научился работать с инструментами kubernetes. Понял, как пишутся настройки и конфигурации для подов и прочих объектов minikube. В ходе работы возникла преграда в виде нерешаемой проблемы git actions. С какого то момента все мои пуши в репозиторий не запускали workflow, и что бы я не делал, так и не смог разобраться, как это исправить.