### voiceUp project creation

```

work_shop> django-admin startproject voiceapp

```

### app creation

```
    cmd>python manage.py  startapp myapp 
```

### seerver run command

```

cmd> python manage,py runserver

```


#### django_model creation

*myapp_models.py*

```

from django.db import models

class FeedBack(models.Model):

    name = models.CharField(max_length=200)

    feed_back_text = models.TextField()

    phone_number = models.PositiveIntegerField()

    email = models.EmailField(unique=True)

    created_date = models.DateTimeField(auto_now_add=True)

```


### command for creating query file

```
cmd> python manage.py makemigrations
```

### command for apply migrations

```

cmd>python manage.py migrate

```