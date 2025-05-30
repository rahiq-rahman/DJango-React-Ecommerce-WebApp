# DJango-React-Ecommerce-WebApp

## Project Setup
### Step 1: (Create virtual environment) 
Run: python -m venv env
### Step 2: (Activate script) 
Run: env/Scripts/activate
### Step 3: (Make requirements.txt) 
asgiref
Django
django-cors-headers
djangorestframework
djangorestframework-simplejwt
PyJWT
pytz
sqlparse
psycopg2-binary
python-dotenv
## Step 4: 
Run: pip install -r requirements.txt
## Step 5:
django-admin startapp backend
## Step 6: (Setup Django/settings.py)
from datetime import timedelta
from dotenv import load_dotenv
import os

load_dotenv()

ALLOWED_HOSTS = ["*"]

REST_FRAMEWORK = {
    "DEFAULT_AUTHENTICATION_CLASSES": (
        "rest_framework_simplejwt.authentication.JWTAuthentication",
    ),
    "DEFAULT_PERMISSION_CLASSES": [
        "rest_framework.permissions.IsAuthenticated",
    ],
}

SIMPLE_JWT = {
    "ACCESS_TOKEN_LIFETIME": timedelta(minutes=30),
    "REFRESH_TOKEN_LIFETIME": timedelta(days=1),
}

INSTALLED_APPS = [
    "api",
    "rest_framework",
    "corsheaders",
]

MIDDLEWARE = [
    "corsheaders.middleware.CorsMiddleware",
]

CORS_ALLOW_ALL_ORIGINS = True
CORS_ALLOWS_CREDENTIALS = True

## Step 7: React Setup

npm create vite@latest frontend -- --template react
npm install axios react-router-dom jwt-decode

## Step 8: Axios Setup


