# api_tasks
An API endpoint based on Django REST Framework with resolving some issues
at  [The base project](https://github.com/GomaGoma676/api_tasks) with 

- Authorize user login with JWT token
- Provide task list management function (create/update/delete)
- Issue and resolution: 
  - Posix error on database name : parse with `str` (api_tasks/settings.py))
  - CSS loading error on admin console (api/urls.py)
    - Add `+ static(settings.STATIC_URL, document_root=settings.STATIC_ROOT)` to a list of `urlpatterns`
    - Collect static files by `python manage.py collectstatic`
  - Cross Origin Reference Error raised when receiving response
    - Add `CORS_ORIGIN_WHITELIST = [‘http://localhost:3000’]` and `CORS_ALLOW_CREDENTIALS = True`

## Installation

From Django Navigator, create an environment on python 3.8

```
pip install django==3.0.7
pip install djangorestframework==3.10
pip install djangorestframework-simplejwt==4.6.0
pip install PyJWT==2.0.0
pip install django djoser
pip install django-cors-headers==3.4.0
```

`db.sqlite3` will be created by `django`

## Urls: 
 
- Base url: http://localhost:8000/
- Admin console: http://localhost:8000/admin/

## TODO

Retrieve and display `profile.username` on task list view. 