<!--
https://readme42.com
-->


[![](https://img.shields.io/pypi/v/django-configurations-celery-app.svg?maxAge=3600)](https://pypi.org/project/django-configurations-celery-app/)
[![](https://img.shields.io/badge/License-Unlicense-blue.svg?longCache=True)](https://unlicense.org/)
[![](https://github.com/andrewp-as-is/django-configurations-celery-app.py/workflows/tests42/badge.svg)](https://github.com/andrewp-as-is/django-configurations-celery-app.py/actions)

### Installation
```bash
$ [sudo] pip install django-configurations-celery-app
```

#### Examples
```python
from django_configurations_celery_app import app
```

```bash
$ celery -A django_configurations_celery_app worker -P gevent -c 20 -Q celery
```

P.S.: app source
```python
import os

from celery import Celery

os.environ.setdefault('DJANGO_SETTINGS_MODULE', 'settings')
os.environ.setdefault('DJANGO_CONFIGURATION', 'Dev')

import configurations
configurations.setup()

app = Celery()
app.config_from_object('django.conf:settings')
```

#### Links
+   [django-configurations](https://github.com/jazzband/django-configurations)

<p align="center">
    <a href="https://readme42.com/">readme42.com</a>
</p>