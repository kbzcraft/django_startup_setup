# smart-send
step 1 : create a virtual env

# python3 -m venv <env_name>

download repo

# git clone https://github.com/kbzcraft/smart-send.git

install req.txt

# pip install -r req.txt

go to .env file and and add your secretcode there
  - to get secret key you can run following command
  # python -c 'from django.core.management.utils import get_random_secret_key; print(get_random_secret_key())'
 
and thats all another way would be
replace setting.py file and urls.py
and create .env file and save SECRET_KEY in it


The code i have added in setting.py files are:
  # import os
  # from dotenv import load_dotenv

  Load environment variables from .env file
  # load_dotenv()
  set secret key from environment variable
  # SECRET_KEY = os.getenv('SECRET_KEY')
  
  # STATIC_URL = '/static/'
  # STATIC_ROOT = os.path.join(BASE_DIR, 'static')
And in urls.py:
  # from django.conf import settings
  # from django.conf.urls.static import static
  
  # urlpatterns = [
      path('admin/', admin.site.urls),
    ]+ static(settings.STATIC_URL, document_root=settings.STATIC_ROOT) + static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)

  MEDIA_URL = '/media/'
  **MEDIA_ROOT = os.path.join(BASE_DIR, 'media')
