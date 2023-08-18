# Kittygram

### Социальная сеть для демонстрации ваших домашних питомцев.

### Функции
 - Создание профиля
 - Загрузка изображений питомцев
 - Указание достижений питомцев

### Используемые технологии
 - Django
 - Django Rest Framework
 - djoser
 - webcolors
 - Pillow

### Установка
```sh
Находясь в дирректории проекта:
python -m venv venv
pip install -r requirements.txt
python manage.py migrate
В настройках Django:
Добавьте в список ALLOWED_HOSTS внешний IP сервера, 127.0.0.1 localhost и домен в файл .env
Так же установите в настройках STATIC_URL = 'static_backend'
Соберите статику:
python3 manage.py collectstatic
sudo cp -r путь_к_директории_с_бэкендом/static_backend /var/www/название_проекта
Находясь в дирректории фронтенl-приложением:
npm i
npm run build
Скопируйте статику фронтенд-приложения в директорию по умолчанию:
sudo cp -r путь_к_директории_с_фронтенд-приложением/build/. /var/www/имя_проекта/
Далее установите gunicorn и настройте конфиг:
pip install gunicorn==20.1.0
Из директории с manage.py gunicorn --bind 0.0.0.0:8000 kittygram_backend.wsgi
Введите в конфиг свои данные:
sudo nano /etc/systemd/system/gunicorn_название_проекта.service
sudo systemctl start gunicorn_название_проекта
sudo systemctl enable gunicorn_название_проекта
Запуск nginx:
sudo apt install nginx -y
sudo systemctl start nginx
Настройте конфиг sudo nano /etc/nginx/sites-enabled/default
sudo systemctl reload nginx
```

### Об авторе 
Егор Пухальский, начинающий Python-разработчик.
