# Django Basic Startup setup

## Installation Instructions

1. Create a virtual environment:

```
python3 -m venv <env_name>
```
  For ubuntu
  ```
  source <env_name>/bin/activate
  ```
  If you are using window what is wrong with you.
  Find out yourself how to create and activate venv in your window and then you can watch your neighbours do... ....🙄
  [How To Set Up a Virtual Python Environment (Windows)](https://mothergeo-py.readthedocs.io/en/latest/development/how-to/venv-win.html)

2. Download the repository:

```
git clone https://github.com/kbzcraft/smart-send.git
```

3. Install the required packages:
```
pip install -r req.txt
```
4. Configure the environment variables:

  - Open the .env file and add your secret code there.

    To generate a secret key, you can run the following command:
    ```
    python -c 'from django.core.management.utils import get_random_secret_key; print(get_random_secret_key())'

    ```
    Copy the generated secret key and add it to the .env file.
    And you or good to go
    #OR
5 .Alternatively, you can replace the contents of the setting.py file with the following code:
  ```
  import os
  from dotenv import load_dotenv

  # Load environment variables from .env file
  load_dotenv()

  # Set secret key from environment variable
  SECRET_KEY = os.getenv('SECRET_KEY')

  # STATIC_URL = '/static/'
  STATICFILES_DIRS =(os.path.join(BASE_DIR, 'static'),)

  ```
5.Update the urls.py file:

  -Replace the contents of urls.py with the following code:
  ```
  from django.contrib import admin
  from django.urls import path
  from django.conf import settings
  from django.conf.urls.static import static

  urlpatterns = [
      path('admin/', admin.site.urls),
  ]+ static(settings.STATIC_URL, document_root=settings.STATIC_ROOT) + static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)

  ```
  Save the SECRET_KEY in a new .env file:

  Create a new .env file and save the SECRET_KEY value obtained from Step 4.

  That's it! You have successfully set up the django project, but its probably easy to copy in setting.py and urls.py but if it's your first time then just clone it.
