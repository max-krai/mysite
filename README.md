# mysite

My shop Project

# БД
## Cоздание пользователя
```SQL
CREATE USER mysite WITH PASSWORD 'mysite';
```
## Cоздание базы
```SQL
CREATE DATABASE mysite
   WITH OWNER = mysite
        ENCODING = 'UTF8'
        TABLESPACE = pg_default
        LC_COLLATE = 'Russian_Russia.1251'
        LC_CTYPE = 'Russian_Russia.1251'
        CONNECTION LIMIT = -1;
```
## Права на базу
```SQL
GRANT CONNECT, TEMPORARY ON DATABASE mysite TO public;
GRANT ALL ON DATABASE mysite TO postgres;
GRANT ALL ON DATABASE mysite TO mysite;
```

# Local.py example
```Python
from .dev import *

SECRET_KEY = 'your_secret_key'

ALLOWED_HOSTS = ('')

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'mysite',
        'USER': 'mysite',
        'PASSWORD': 'mysite',
        'HOST': 'localhost'
    }
}

