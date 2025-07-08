# Установка Jenkins с использованием Docker Compose

Этот репозиторий содержит конфигурацию Docker Compose для быстрой установки Jenkins.  
Данная настройка **не предназначена для использования в продакшене**.

> 📌 Основано на [официальной документации](https://www.jenkins.io/doc/book/installing/docker/), но упрощено с использованием `docker-compose.yml`.

---

## Установка Docker

### Шаг 1

Установите Docker локально (самый простой способ — использовать Docker Desktop).

### Шаг 2

Склонируйте этот репозиторий или скачайте его содержимое.

### Шаг 3

Откройте терминал в директории, где находится `Dockerfile` из этого репозитория.  
Соберите Docker-образ Jenkins:

```bash
docker build -t my-jenkins .
```

### Шаг 4

Запустите Jenkins:

```bash
docker compose up -d
```

### Шаг 5

Откройте Jenkins, перейдя по адресу: [http://localhost:8080/](http://localhost:8080/) и завершите установку.

### Шаг 6

Если вы хотите остановить Jenkins и вернуться к нему позже, выполните:

```bash
docker compose down
```

Чтобы снова запустить Jenkins, выполните ту же команду из шага 4:

```bash
docker compose up -d
```

---

## Удаление Jenkins

Когда вы закончите работу с Jenkins, выполните следующую команду, чтобы остановить Jenkins и удалить все тома и образы:

```bash
docker compose down --volumes --rmi all
```
