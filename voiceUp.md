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


### command for creating query file (convert model in to sql query file)

```
cmd> python manage.py makemigrations
```

### command for apply migrations (execute qury file)

```

cmd>python manage.py migrate

```

### command for creating django admin

```
 
 python manage.py createsuperuser

```


### my_app>views.py

```
from django.shortcuts import render
from .models import FeedBack
from django.views.generic import View

# Create your views here.
class FeedBackView(View):
    def get(self,request):
        feedbacks = Feedback.objects.all()
        return render(request,'feedback.html', {'feedbacks': feedbacks})
```


#### my_app > templates > feedback.html

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>

{% for feedback in feedbacks %}
----------------------------
     <h3>{{feedback.name}}</h3>
     <h4>{{feedback.feed_back_text}}</h4>
     ---------------------
{% endfor %}

</body>
</html>
```