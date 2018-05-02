# TUS

TUS is temporary URL shorting service.

---

## Dev configuration

### 1. Create python virtual environment

```sh
virtualenv -p `which python3` .env
source .env/bin/activate
```

### 2. Install packages

```sh
pip install -r requirements.txt
```

### 3. Security issues

Create the file `local_settings.py` and redefine security variables: `SECRET_KEY, COOKIE_SALT, ALLOWED_HOSTS, DATABASES`.

```sh
touch tus/local_settings.py
```

### 4. Prepare database

```sh
python manage.py migrate
python manage.py createsuperuser
python manage.py migrate shorter
python manage.py collectstatic --noinput
```

### 5. Run develop server

```
python manager.py runserver
```

Open address `http://127.0.0.1:8000/`.