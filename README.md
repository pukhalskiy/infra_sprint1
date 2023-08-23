# Kittygram

 Социальная сеть для демонстрации ваших домашних питомцев.

## Функциональность
 - Создание профиля
 - Загрузка изображений питомцев
 - Указание достижений питомцев

## Используемые технологии
 - Django
 - Django Rest Framework
 - djoser
 - webcolors
 - Pillow

## Установка

Находясь в директории проекта:
```sh
python -m venv venv
pip install -r requirements.txt
python manage.py migrate
```
В настройках Django:
Добавьте в список ALLOWED_HOSTS внешний IP сервера, 127.0.0.1, localhost и домен в файл .env
Также установите в настройках STATIC_URL = 'static_backend'
Соберите статику:
```sh
python3 manage.py collectstatic
sudo cp -r путь_к_директории_с_бэкендом/static_backend /var/www/название_проекта
```
Находясь в директории фронтенд-приложением:
```sh
npm i
npm run build
```
Скопируйте статику фронтенд-приложения в директорию по умолчанию:
sudo cp -r путь_к_директории_с_фронтенд-приложением/build/. /var/www/имя_проекта/

Далее установите gunicorn и настройте конфиг:
```sh
pip install gunicorn==20.1.0
```
Из директории с manage.py:
```sh
gunicorn --bind 0.0.0.0:8000 kittygram_backend.wsgi
```
Скопируйте конфинг gunicorn из директории infra:
```sh
sudo cp -r ... /etc/systemd/system/gunicorn_название_проекта.service
sudo systemctl start gunicorn_название_проекта
sudo systemctl enable gunicorn_название_проекта
```
Запуск nginx:
```sh
sudo apt install nginx -y
sudo systemctl start nginx
```
Скопируйте конфиг nginx из директории infra:
```sh
sudo cp -r ...  /etc/nginx/sites-enabled/default
sudo systemctl reload nginx
```


## Об авторе 
Егор Пухальский, начинающий Python-разработчик.
