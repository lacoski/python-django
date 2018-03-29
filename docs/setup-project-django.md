# Thiết lập Django cơ bản
---
## 1. Thiết lập Django
### 1.1 Cài đặt Django
> Django 2.x yêu cầu python 3

__Cài đặt python 3__

> Cơ bản ubuntu 16.x đã có sẳn python, để có version mới nhất, cần update

```
sudo apt-get update -y
```

__Kiểm tra version Python__

```
$ python3 -V

Python 3.5.2
```

__Cài đặt Pip__

```
apt-get install -y python3-pip
```

__Cài đặt phiên bản mới nhất __Django__

```
sudo pip3 install Django==2.0
```

Kiểm tra version django

```
$ django-admin --version

2.0.2
```

### 2. Tạo Project mới với Django

__Tạo mới Project__

```
django-admin startproject mysite
```

__Cấu trúc project vừa tạo__

```
mysite/
    manage.py
    mysite/
        __init__.py
        settings.py
        urls.py
        wsgi.py
```     

__Chạy django server__
```
python3 manage.py runserver
```

__Kết quả__

```
http://127.0.0.1:8000/
```

> Xem thêm docs python để biết thêm chi tiết

> https://github.com/lacoski/python

## Nguồn
https://www.cyberciti.biz/faq/how-to-install-the-django-web-framework-2-on-ubuntu-16-04/

https://github.com/lacoski/python

https://docs.djangoproject.com/en/2.0/intro/tutorial01/
