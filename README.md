# 🌸 Django + Tailwind CLI + DaisyUI Setup Guide# 🌸 Django + Tailwind CLI + DaisyUI Setup Guide



> **Complete setup guide for Django with TailwindCSS, DaisyUI, Alpine.js, and HTMX - All without Node.js or npm!**> **Complete setup guide for Django with TailwindCSS, DaisyUI, Alpine.js, and HTMX - All without Node.js or npm!**



[![Django](https://img.shields.io/badge/Django-5.0+-green.svg)](https://www.djangoproject.com/)[![Django](https://img.shields.io/badge/Django-5.0+-green.svg)](https://www.djangoproject.com/)

[![TailwindCSS](https://img.shields.io/badge/TailwindCSS-3.4+-blue.svg)](https://tailwindcss.com/)[![TailwindCSS](https://img.shields.io/badge/TailwindCSS-3.4+-blue.svg)](https://tailwindcss.com/)

[![DaisyUI](https://img.shields.io/badge/DaisyUI-4.0+-purple.svg)](https://daisyui.com/)[![DaisyUI](https://img.shields.io/badge/DaisyUI-4.0+-purple.svg)](https://daisyui.com/)

[![Python](https://img.shields.io/badge/Python-3.10+-yellow.svg)](https://www.python.org/)[![Python](https://img.shields.io/badge/Python-3.10+-yellow.svg)](https://www.python.org/)



------



## 📋 Table of Contents## 📋 Table of Contents



- [What You'll Get](#-what-youll-get)1. [What You'll Get](#-what-youll-get)

- [Prerequisites](#-prerequisites)2. [Prerequisites](#-prerequisites)

- [Quick Start](#-quick-start-tldr)3. [Project Setup](#️-step-1-project-setup)

- [Detailed Setup](#detailed-setup-steps)4. [Install Packages](#-step-2-install-all-packages-at-once)

- [DaisyUI Components](#-using-daisyui-components)5. [Create Django Project](#-step-3-create-django-project)

- [Alpine.js Examples](#-alpinejs-examples)6. [MySQL Setup](#️-step-4-mysql-database-setup)

- [HTMX Examples](#-htmx-examples)7. [Django Settings](#️-step-5-django-settings-configuration)

- [Troubleshooting](#-troubleshooting)8. [TailwindCSS + DaisyUI](#-step-6-tailwindcss--daisyui-setup)

- [Development Tips](#-development-tips)9. [Alpine.js & HTMX](#-step-7-alpinejs--htmx-setup)

- [Additional Resources](#-additional-resources)10. [Base Template](#-step-8-create-base-template-with-seo)

11. [URLs Configuration](#-step-9-configure-urls-for-static-and-media-files)

---12. [Static Files](#️-step-10-collect-static-files)

13. [Run Migrations](#-step-11-run-migrations-and-create-superuser)

## 🎯 What You'll Get14. [Start Server](#️-step-12-run-development-server)

15. [DaisyUI Components](#-step-13-using-daisyui-components)

✅ **Django 5.0+** - Modern Python web framework  16. [Alpine.js Examples](#-step-14-alpinejs-examples)

✅ **TailwindCSS** - Utility-first CSS framework (no Node.js!)  17. [HTMX Examples](#-step-15-htmx-examples)

✅ **DaisyUI** - Beautiful UI components for Tailwind (28+ themes)  18. [Additional Resources](#-additional-resources)

✅ **Alpine.js** - Lightweight JavaScript framework  

✅ **HTMX** - High-power tools for HTML  ---

✅ **MySQL** - Production-ready database  

✅ **SEO Optimized** - Comprehensive meta tags  ## 🎯 What You'll Get

✅ **Dark/Light Mode** - Built-in theme switcher  

✅ **Auto Reload** - Browser auto-refresh on changes  ✅ **Django 5.0+** - Modern Python web framework  

✅ **Security** - Honeypot, CSRF, XSS protection  ✅ **TailwindCSS** - Utility-first CSS framework (no Node.js!)  

✅ **DaisyUI** - Beautiful UI components for Tailwind  

---✅ **Alpine.js** - Lightweight JavaScript framework  

✅ **HTMX** - High-power tools for HTML  

## ✅ Prerequisites✅ **MySQL** - Production-ready database  

✅ **SEO Optimized** - Comprehensive meta tags  

Before starting, make sure you have:✅ **Dark/Light Mode** - Built-in theme switcher  

✅ **Auto Reload** - Browser auto-refresh on changes  

- **Python 3.10+** installed ([Download](https://www.python.org/downloads/))✅ **Security** - Honeypot, CSRF, XSS protection  

- **uv** package installer ([Install guide](https://github.com/astral-sh/uv))

- **MySQL Server** ([Download](https://dev.mysql.com/downloads/installer/))---

- **Git** (optional, for version control)

## ✅ Prerequisites

---

Before starting, make sure you have:

## 🚀 Quick Start (TL;DR)

- **Python 3.10+** installed ([Download](https://www.python.org/downloads/))

```bash- **uv** package installer ([Install guide](https://github.com/astral-sh/uv))

# 1. Create and setup project- **MySQL Server** ([Download](https://dev.mysql.com/downloads/installer/))

mkdir myproject && cd myproject- **Git** (optional, for version control)

uv init

uv venv---

.venv\Scripts\activate

## ⚙️ Step 1: Project Setup

# 2. Install all packages

uv pip install django pillow django-extensions django-cotton django-tailwind-cli honeypot mysqlclient django-htmx django-browser-reload### 1️⃣ Create project folder and initialize environment

```bash

# 3. Create Django projectmkdir myproject

django-admin startproject config .cd myproject

python manage.py startapp coreuv init

mkdir templates static media static\css```



# 4. Setup TailwindCSS### 2️⃣ Create virtual environment

uv run manage.py tailwind setup```bash

uv run manage.py tailwind builduv venv

.venv\Scripts\activate

# 5. Run migrations```

uv run manage.py migrate

uv run manage.py createsuperuser---



# 6. Start development server## 📦 Step 2: Install All Packages at Once

uv run manage.py tailwind runserver

```### Install all required packages with uv

```bash

Visit: **http://127.0.0.1:8000/** 🎉uv pip install django pillow django-extensions django-cotton django-tailwind-cli honeypot mysqlclient django-htmx django-browser-reload

```

---

**Packages installed:**

# Detailed Setup Steps- `django` - Web framework

- `pillow` - Image processing

## ⚙️ Step 1: Project Setup- `django-extensions` - Useful Django extensions

- `django-cotton` - Component-based templates

### 1️⃣ Create project folder and initialize environment- `django-tailwind-cli` - TailwindCSS without Node.js (with DaisyUI support)

```bash- `honeypot` - Security against spam bots

mkdir myproject- `mysqlclient` - MySQL database connector

cd myproject- `django-htmx` - HTMX integration for Django

uv init- `django-browser-reload` - Auto browser reload in development

```

---

### 2️⃣ Create virtual environment

```bash## 🚀 Step 3: Create Django Project

uv venv

.venv\Scripts\activate### 1️⃣ Create Django project and app

``````bash

django-admin startproject config .

---python manage.py startapp core

```

## 📦 Step 2: Install All Packages at Once

### 2️⃣ Create required directories

### Install all required packages with uv```bash

```bashmkdir templates

uv pip install django pillow django-extensions django-cotton django-tailwind-cli honeypot mysqlclient django-htmx django-browser-reloadmkdir static

```mkdir media

mkdir static\css

**Packages installed:**mkdir static\js

- `django` - Web frameworkmkdir static\images

- `pillow` - Image processing```

- `django-extensions` - Useful Django extensions

- `django-cotton` - Component-based templates---

- `django-tailwind-cli` - TailwindCSS without Node.js (with DaisyUI support)

- `honeypot` - Security against spam bots## 🗄️ Step 4: MySQL Database Setup

- `mysqlclient` - MySQL database connector

- `django-htmx` - HTMX integration for Django### 1️⃣ Install MySQL Server

- `django-browser-reload` - Auto browser reload in developmentDownload and install MySQL from [https://dev.mysql.com/downloads/installer/](https://dev.mysql.com/downloads/installer/)



---### 2️⃣ Create database

Open MySQL command line:

## 🚀 Step 3: Create Django Project```sql

CREATE DATABASE myproject_db CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;

### 1️⃣ Create Django project and appCREATE USER 'myproject_user'@'localhost' IDENTIFIED BY 'your_password';

```bashGRANT ALL PRIVILEGES ON myproject_db.* TO 'myproject_user'@'localhost';

django-admin startproject config .FLUSH PRIVILEGES;

python manage.py startapp coreEXIT;

``````



### 2️⃣ Create required directories### 3️⃣ Configure database in `config/settings.py`

```bash```python

mkdir templatesDATABASES = {

mkdir static    'default': {

mkdir media        'ENGINE': 'django.db.backends.mysql',

mkdir static\css        'NAME': 'myproject_db',

mkdir static\js        'USER': 'myproject_user',

mkdir static\images        'PASSWORD': 'your_password',

```        'HOST': 'localhost',

        'PORT': '3306',

---        'OPTIONS': {

            'charset': 'utf8mb4',

## 🗄️ Step 4: MySQL Database Setup            'init_command': "SET sql_mode='STRICT_TRANS_TABLES'",

        }

### 1️⃣ Install MySQL Server    }

Download and install MySQL from [https://dev.mysql.com/downloads/installer/](https://dev.mysql.com/downloads/installer/)}

```

### 2️⃣ Create database

Open MySQL command line:---

```sql

CREATE DATABASE myproject_db CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;## ⚙️ Step 5: Django Settings Configuration

CREATE USER 'myproject_user'@'localhost' IDENTIFIED BY 'your_password';

GRANT ALL PRIVILEGES ON myproject_db.* TO 'myproject_user'@'localhost';### Update `config/settings.py`

FLUSH PRIVILEGES;

EXIT;#### 1️⃣ Add apps to INSTALLED_APPS

``````python

INSTALLED_APPS = [

### 3️⃣ Configure database in `config/settings.py`    'django.contrib.admin',

```python    'django.contrib.auth',

DATABASES = {    'django.contrib.contenttypes',

    'default': {    'django.contrib.sessions',

        'ENGINE': 'django.db.backends.mysql',    'django.contrib.messages',

        'NAME': 'myproject_db',    'django.contrib.staticfiles',

        'USER': 'myproject_user',    

        'PASSWORD': 'your_password',    # Third party apps

        'HOST': 'localhost',    'django_extensions',

        'PORT': '3306',    'django_cotton',

        'OPTIONS': {    'django_tailwind_cli',

            'charset': 'utf8mb4',    'honeypot',

            'init_command': "SET sql_mode='STRICT_TRANS_TABLES'",    'django_htmx',

        }    'django_browser_reload',

    }    

}    # Local apps

```    'core',

]

---```



## ⚙️ Step 5: Django Settings Configuration#### 2️⃣ Add middleware for security

```python

### Update `config/settings.py`MIDDLEWARE = [

    'django.middleware.security.SecurityMiddleware',

#### 1️⃣ Add apps to INSTALLED_APPS    'django.contrib.sessions.middleware.SessionMiddleware',

```python    'django.middleware.common.CommonMiddleware',

INSTALLED_APPS = [    'django.middleware.csrf.CsrfViewMiddleware',

    'django.contrib.admin',    'django.contrib.auth.middleware.AuthenticationMiddleware',

    'django.contrib.auth',    'django.contrib.messages.middleware.MessageMiddleware',

    'django.contrib.contenttypes',    'django.middleware.clickjacking.XFrameOptionsMiddleware',

    'django.contrib.sessions',    'django_htmx.middleware.HtmxMiddleware',  # HTMX support

    'django.contrib.messages',    'django_browser_reload.middleware.BrowserReloadMiddleware',  # Auto-reload in development

    'django.contrib.staticfiles',]

    ```

    # Third party apps

    'django_extensions',#### 3️⃣ Configure templates

    'django_cotton',```python

    'django_tailwind_cli',TEMPLATES = [

    'honeypot',    {

    'django_htmx',        'BACKEND': 'django.template.backends.django.DjangoTemplates',

    'django_browser_reload',        'DIRS': [BASE_DIR / 'templates'],

            'APP_DIRS': True,

    # Local apps        'OPTIONS': {

    'core',            'context_processors': [

]                'django.template.context_processors.debug',

```                'django.template.context_processors.request',

                'django.contrib.auth.context_processors.auth',

#### 2️⃣ Add middleware for security                'django.contrib.messages.context_processors.messages',

```python                'django.template.context_processors.media',

MIDDLEWARE = [            ],

    'django.middleware.security.SecurityMiddleware',            'builtins': [

    'django.contrib.sessions.middleware.SessionMiddleware',                'django_cotton.templatetags.cotton',

    'django.middleware.common.CommonMiddleware',            ],

    'django.middleware.csrf.CsrfViewMiddleware',        },

    'django.contrib.auth.middleware.AuthenticationMiddleware',    },

    'django.contrib.messages.middleware.MessageMiddleware',]

    'django.middleware.clickjacking.XFrameOptionsMiddleware',```

    'django_htmx.middleware.HtmxMiddleware',  # HTMX support

    'django_browser_reload.middleware.BrowserReloadMiddleware',  # Auto-reload in development#### 4️⃣ Configure static and media files

]```python

```# Static files (CSS, JavaScript, Images)

STATIC_URL = '/static/'

#### 3️⃣ Configure templatesSTATIC_ROOT = BASE_DIR / 'staticfiles'

```pythonSTATICFILES_DIRS = [

TEMPLATES = [    BASE_DIR / 'static',

    {]

        'BACKEND': 'django.template.backends.django.DjangoTemplates',

        'DIRS': [BASE_DIR / 'templates'],# Media files (User uploads)

        'APP_DIRS': True,MEDIA_URL = '/media/'

        'OPTIONS': {MEDIA_ROOT = BASE_DIR / 'media'

            'context_processors': [```

                'django.template.context_processors.debug',

                'django.template.context_processors.request',#### 5️⃣ Add security settings

                'django.contrib.auth.context_processors.auth',```python

                'django.contrib.messages.context_processors.messages',# Security Settings

                'django.template.context_processors.media',SECURE_BROWSER_XSS_FILTER = True

            ],SECURE_CONTENT_TYPE_NOSNIFF = True

            'builtins': [X_FRAME_OPTIONS = 'DENY'

                'django_cotton.templatetags.cotton',CSRF_COOKIE_SECURE = False  # Set True in production with HTTPS

            ],SESSION_COOKIE_SECURE = False  # Set True in production with HTTPS

        },SECURE_SSL_REDIRECT = False  # Set True in production with HTTPS

    },

]# Honeypot settings

```HONEYPOT_FIELD_NAME = 'email_confirm'

```

#### 4️⃣ Configure static and media files

```python#### 6️⃣ Configure allowed hosts

# Static files (CSS, JavaScript, Images)```python

STATIC_URL = '/static/'ALLOWED_HOSTS = ['localhost', '127.0.0.1']

STATIC_ROOT = BASE_DIR / 'staticfiles'

STATICFILES_DIRS = [# Browser reload configuration (for development only)

    BASE_DIR / 'static',INTERNAL_IPS = [

]    "127.0.0.1",

]

# Media files (User uploads)```

MEDIA_URL = '/media/'

MEDIA_ROOT = BASE_DIR / 'media'---

```

## 🎨 Step 6: TailwindCSS + DaisyUI Setup

#### 5️⃣ Add security settings

```python### 1️⃣ Add TailwindCSS CLI settings to `config/settings.py`

# Security Settings```python

SECURE_BROWSER_XSS_FILTER = True# TailwindCSS CLI Configuration

SECURE_CONTENT_TYPE_NOSNIFF = TrueTAILWIND_CLI_PATH = "~/.local/bin/"  # Will auto-download

X_FRAME_OPTIONS = 'DENY'TAILWIND_CLI_VERSION = "latest"

CSRF_COOKIE_SECURE = False  # Set True in production with HTTPSTAILWIND_CLI_AUTOMATIC_DOWNLOAD = True

SESSION_COOKIE_SECURE = False  # Set True in production with HTTPS

SECURE_SSL_REDIRECT = False  # Set True in production with HTTPS# Enable DaisyUI

TAILWIND_CLI_USE_DAISY_UI = True

# Honeypot settings

HONEYPOT_FIELD_NAME = 'email_confirm'# TailwindCSS source and destination

```TAILWIND_CLI_SRC_CSS = "static/css/source.css"

TAILWIND_CLI_DIST_CSS = "static/css/output.css"

#### 6️⃣ Configure allowed hosts and browser reload```

```python

ALLOWED_HOSTS = ['localhost', '127.0.0.1']### 2️⃣ Initialize TailwindCSS

```bash

# Browser reload configuration (for development only)uv run manage.py tailwind setup

INTERNAL_IPS = [```

    "127.0.0.1",

]This command will:

```- Download the TailwindCSS standalone CLI

- Set up the necessary configuration

---- Prepare DaisyUI integration



## 🎨 Step 6: TailwindCSS + DaisyUI Setup### 3️⃣ Create `static/css/source.css`

```bash

### 1️⃣ Add TailwindCSS CLI settings to `config/settings.py`New-Item -Path "static/css/source.css" -ItemType File -Force

```python```

# TailwindCSS CLI Configuration

TAILWIND_CLI_PATH = "~/.local/bin/"  # Will auto-downloadAdd this content to `static/css/source.css`:

TAILWIND_CLI_VERSION = "latest"```css

TAILWIND_CLI_AUTOMATIC_DOWNLOAD = True/* Import TailwindCSS */

@import "tailwindcss";

# Enable DaisyUI

TAILWIND_CLI_USE_DAISY_UI = True/* Enable DaisyUI plugin with themes */

@plugin "daisyui" {

# TailwindCSS source and destination    /* Configure DaisyUI themes */

TAILWIND_CLI_SRC_CSS = "static/css/source.css"    themes: ["light", "dark", "cupcake", "synthwave", "retro", "cyberpunk", "valentine", "halloween", "garden", "forest", "aqua", "lofi", "pastel", "fantasy", "wireframe", "black", "luxury", "dracula", "cmyk", "autumn", "business", "acid", "lemonade", "night", "coffee", "winter"];

TAILWIND_CLI_DIST_CSS = "static/css/output.css"};

```

/* Custom CSS Variables for Dark/Light Mode */

### 2️⃣ Initialize TailwindCSS@layer base {

```bash  :root {

uv run manage.py tailwind setup    /* Light Mode Colors */

```    --color-bg-primary: 255 255 255;

    --color-bg-secondary: 249 250 251;

This command will:    --color-bg-tertiary: 243 244 246;

- Download the TailwindCSS standalone CLI    

- Set up the necessary configuration    --color-text-primary: 17 24 39;

- Prepare DaisyUI integration    --color-text-secondary: 75 85 99;

    --color-text-tertiary: 107 114 128;

### 3️⃣ Create `static/css/source.css`    

    --color-title: 31 41 55;

Add this content to `static/css/source.css`:    --color-subtitle: 55 65 81;

```css    --color-description: 107 114 128;

/* Import TailwindCSS */    

@import "tailwindcss";    --color-primary: 59 130 246;

    --color-primary-hover: 37 99 235;

/* Enable DaisyUI plugin with themes */    --color-secondary: 139 92 246;

@plugin "daisyui" {    --color-secondary-hover: 124 58 237;

    /* Configure DaisyUI themes */    

    themes: ["light", "dark", "cupcake", "synthwave", "retro", "cyberpunk", "valentine", "halloween", "garden", "forest", "aqua", "lofi", "pastel", "fantasy", "wireframe", "black", "luxury", "dracula", "cmyk", "autumn", "business", "acid", "lemonade", "night", "coffee", "winter"];    --color-accent: 236 72 153;

};    --color-success: 34 197 94;

    --color-warning: 251 146 60;

/* Custom CSS Variables for Dark/Light Mode */    --color-error: 239 68 68;

@layer base {    

  :root {    --color-logo: 59 130 246;

    /* Light Mode Colors */    --color-border: 229 231 235;

    --color-bg-primary: 255 255 255;  }

    --color-bg-secondary: 249 250 251;

    --color-bg-tertiary: 243 244 246;  .dark {

        /* Dark Mode Colors */

    --color-text-primary: 17 24 39;    --color-bg-primary: 17 24 39;

    --color-text-secondary: 75 85 99;    --color-bg-secondary: 31 41 55;

    --color-text-tertiary: 107 114 128;    --color-bg-tertiary: 55 65 81;

        

    --color-title: 31 41 55;    --color-text-primary: 243 244 246;

    --color-subtitle: 55 65 81;    --color-text-secondary: 209 213 219;

    --color-description: 107 114 128;    --color-text-tertiary: 156 163 175;

        

    --color-primary: 59 130 246;    --color-title: 249 250 251;

    --color-primary-hover: 37 99 235;    --color-subtitle: 229 231 235;

    --color-secondary: 139 92 246;    --color-description: 156 163 175;

    --color-secondary-hover: 124 58 237;    

        --color-primary: 96 165 250;

    --color-accent: 236 72 153;    --color-primary-hover: 59 130 246;

    --color-success: 34 197 94;    --color-secondary: 167 139 250;

    --color-warning: 251 146 60;    --color-secondary-hover: 139 92 246;

    --color-error: 239 68 68;    

        --color-accent: 244 114 182;

    --color-logo: 59 130 246;    --color-success: 74 222 128;

    --color-border: 229 231 235;    --color-warning: 251 191 36;

  }    --color-error: 248 113 113;

    

  .dark {    --color-logo: 96 165 250;

    /* Dark Mode Colors */    --color-border: 75 85 99;

    --color-bg-primary: 17 24 39;  }

    --color-bg-secondary: 31 41 55;}

    --color-bg-tertiary: 55 65 81;

    /* Custom Utility Classes */

    --color-text-primary: 243 244 246;@layer components {

    --color-text-secondary: 209 213 219;  /* Background Colors */

    --color-text-tertiary: 156 163 175;  .bg-primary {

        background-color: rgb(var(--color-bg-primary));

    --color-title: 249 250 251;  }

    --color-subtitle: 229 231 235;  

    --color-description: 156 163 175;  .bg-secondary {

        background-color: rgb(var(--color-bg-secondary));

    --color-primary: 96 165 250;  }

    --color-primary-hover: 59 130 246;  

    --color-secondary: 167 139 250;  .bg-tertiary {

    --color-secondary-hover: 139 92 246;    background-color: rgb(var(--color-bg-tertiary));

      }

    --color-accent: 244 114 182;

    --color-success: 74 222 128;  /* Text Colors */

    --color-warning: 251 191 36;  .text-primary {

    --color-error: 248 113 113;    color: rgb(var(--color-text-primary));

      }

    --color-logo: 96 165 250;  

    --color-border: 75 85 99;  .text-secondary {

  }    color: rgb(var(--color-text-secondary));

}  }

  

/* Custom Utility Classes */  .text-tertiary {

@layer components {    color: rgb(var(--color-text-tertiary));

  /* Background Colors */  }

  .bg-primary {  

    background-color: rgb(var(--color-bg-primary));  .text-title {

  }    color: rgb(var(--color-title));

    }

  .bg-secondary {  

    background-color: rgb(var(--color-bg-secondary));  .text-subtitle {

  }    color: rgb(var(--color-subtitle));

    }

  .bg-tertiary {  

    background-color: rgb(var(--color-bg-tertiary));  .text-description {

  }    color: rgb(var(--color-description));

  }

  /* Text Colors */

  .text-primary {  /* Brand Colors */

    color: rgb(var(--color-text-primary));  .btn-primary {

  }    background-color: rgb(var(--color-primary));

      color: white;

  .text-secondary {  }

    color: rgb(var(--color-text-secondary));  

  }  .btn-primary:hover {

      background-color: rgb(var(--color-primary-hover));

  .text-tertiary {  }

    color: rgb(var(--color-text-tertiary));  

  }  .btn-secondary {

      background-color: rgb(var(--color-secondary));

  .text-title {    color: white;

    color: rgb(var(--color-title));  }

  }  

    .btn-secondary:hover {

  .text-subtitle {    background-color: rgb(var(--color-secondary-hover));

    color: rgb(var(--color-subtitle));  }

  }

    /* Responsive Container */

  .text-description {  .container {

    color: rgb(var(--color-description));    @apply mx-auto px-4 sm:px-6 lg:px-8;

  }    max-width: 1280px;

  }

  /* Brand Colors */  

  .btn-primary {  .container-sm {

    background-color: rgb(var(--color-primary));    @apply mx-auto px-4 sm:px-6 lg:px-8;

    color: white;    max-width: 640px;

  }  }

    

  .btn-primary:hover {  .container-md {

    background-color: rgb(var(--color-primary-hover));    @apply mx-auto px-4 sm:px-6 lg:px-8;

  }    max-width: 768px;

    }

  .btn-secondary {  

    background-color: rgb(var(--color-secondary));  .container-lg {

    color: white;    @apply mx-auto px-4 sm:px-6 lg:px-8;

  }    max-width: 1024px;

    }

  .btn-secondary:hover {  

    background-color: rgb(var(--color-secondary-hover));  .container-xl {

  }    @apply mx-auto px-4 sm:px-6 lg:px-8;

    max-width: 1280px;

  /* Responsive Container */  }

  .container {  

    @apply mx-auto px-4 sm:px-6 lg:px-8;  .container-2xl {

    max-width: 1280px;    @apply mx-auto px-4 sm:px-6 lg:px-8;

  }    max-width: 1536px;

    }

  .container-sm {

    @apply mx-auto px-4 sm:px-6 lg:px-8;  /* Card Component */

    max-width: 640px;  .card {

  }    @apply bg-secondary rounded-lg shadow-md p-6;

    }

  .container-md {  

    @apply mx-auto px-4 sm:px-6 lg:px-8;  .card-title {

    max-width: 768px;    @apply text-title text-2xl font-bold mb-4;

  }  }

    

  .container-lg {  .card-body {

    @apply mx-auto px-4 sm:px-6 lg:px-8;    @apply text-primary;

    max-width: 1024px;  }

  }

    /* Border Utilities */

  .container-xl {  .border-custom {

    @apply mx-auto px-4 sm:px-6 lg:px-8;    border-color: rgb(var(--color-border));

    max-width: 1280px;  }

  }}

  

  .container-2xl {/* Custom Animations */

    @apply mx-auto px-4 sm:px-6 lg:px-8;@layer utilities {

    max-width: 1536px;  .animate-fade-in {

  }    animation: fadeIn 0.5s ease-in;

  }

  /* Card Component */  

  .card {  @keyframes fadeIn {

    @apply bg-secondary rounded-lg shadow-md p-6;    from {

  }      opacity: 0;

      }

  .card-title {    to {

    @apply text-title text-2xl font-bold mb-4;      opacity: 1;

  }    }

    }

  .card-body {  

    @apply text-primary;  .transition-theme {

  }    transition: background-color 0.3s ease, color 0.3s ease;

  }

  /* Border Utilities */}

  .border-custom {```

    border-color: rgb(var(--color-border));

  }### 4️⃣ Build TailwindCSS

}```bash

uv run manage.py tailwind build

/* Custom Animations */```

@layer utilities {

  .animate-fade-in {For development with auto-rebuild:

    animation: fadeIn 0.5s ease-in;```bash

  }uv run manage.py tailwind watch

  ```

  @keyframes fadeIn {

    from {Or run the development server with TailwindCSS auto-compilation:

      opacity: 0;```bash

    }uv run manage.py tailwind runserver

    to {```

      opacity: 1;

    }This command starts both the Django dev server and TailwindCSS watch mode together!

  }

  ---

  .transition-theme {

    transition: background-color 0.3s ease, color 0.3s ease;## 🚀 Step 7: Alpine.js & HTMX Setup

  }

}### 1️⃣ What are Alpine.js & HTMX?

```

**Alpine.js** - Lightweight JavaScript framework for adding interactivity  

### 4️⃣ Build TailwindCSS**HTMX** - Access modern browser features directly from HTML

```bash

uv run manage.py tailwind buildBoth work perfectly without build steps or npm!

```

### 2️⃣ Add Alpine.js & HTMX to your base template

For development with auto-rebuild:

```bashAlpine.js and HTMX are loaded via CDN (no installation needed).

uv run manage.py tailwind watch

```We'll add them to `base.html` in the next step.



Or run the development server with TailwindCSS auto-compilation:### 3️⃣ Using HTMX in Django

```bash

uv run manage.py tailwind runserverHTMX is already configured via `django-htmx` package and middleware.

```

**Example HTMX usage:**

This command starts both the Django dev server and TailwindCSS watch mode together!```html

<!-- Load content without page reload -->

---<button hx-get="/api/data/" hx-target="#result">

    Load Data

## 🚀 Step 7: Alpine.js & HTMX Setup</button>

<div id="result"></div>

### 1️⃣ What are Alpine.js & HTMX?```



**Alpine.js** - Lightweight JavaScript framework for adding interactivity (15KB)  **Django view for HTMX:**

**HTMX** - Access modern browser features directly from HTML (14KB)```python

def htmx_data(request):

Both work perfectly without build steps or npm!    if request.htmx:  # Check if request is from HTMX

        return render(request, 'partials/data.html')

### 2️⃣ Configuration    return render(request, 'full_page.html')

```

Alpine.js and HTMX are loaded via CDN in the base template (no installation needed).

---

The `django-htmx` package and middleware provide server-side support for HTMX requests.

## 📄 Step 8: Create Base Template with SEO

### 3️⃣ Using HTMX in Django

### Create `templates/base.html`

HTMX is already configured via `django-htmx` package and middleware.```bash

New-Item -Path "templates/base.html" -ItemType File -Force

**Example HTMX usage:**```

```html

<!-- Load content without page reload -->Add this content to `templates/base.html`:

<button hx-get="/api/data/" hx-target="#result" class="btn btn-primary">```html

    Load Data{% load static %}

</button>{% load tailwind_cli %}

<div id="result"></div>

```<!DOCTYPE html>

<html lang="en" data-theme="light" class="scroll-smooth">

**Django view for HTMX:**<head>

```python    <!-- Essential Meta Tags -->

def htmx_data(request):    <meta charset="UTF-8">

    if request.htmx:  # Check if request is from HTMX    <meta name="viewport" content="width=device-width, initial-scale=1.0">

        return render(request, 'partials/data.html')    <meta http-equiv="X-UA-Compatible" content="IE=edge">

    return render(request, 'full_page.html')    

```    <!-- SEO Meta Tags -->

    <title>{% block title %}My Django Project{% endblock %} | Your Brand Name</title>

---    <meta name="description" content="{% block description %}Your comprehensive Django application with modern design and functionality.{% endblock %}">

    <meta name="keywords" content="{% block keywords %}django, web development, tailwindcss, daisyui, htmx, alpine.js{% endblock %}">

## 📄 Step 8: Create Base Template with SEO    <meta name="author" content="Your Name or Company">

    <meta name="robots" content="index, follow">

### Create `templates/base.html`    <meta name="language" content="English">

    <meta name="revisit-after" content="7 days">

Add this content to `templates/base.html`:    

```html    <!-- Canonical URL -->

{% load static %}    <link rel="canonical" href="{% block canonical %}{{ request.build_absolute_uri }}{% endblock %}">

{% load tailwind_cli %}    

    <!-- Open Graph Meta Tags (Facebook, LinkedIn) -->

<!DOCTYPE html>    <meta property="og:title" content="{% block og_title %}{% block title %}My Django Project{% endblock %}{% endblock %}">

<html lang="en" data-theme="light" class="scroll-smooth">    <meta property="og:description" content="{% block og_description %}{% block description %}Your comprehensive Django application with modern design and functionality.{% endblock %}{% endblock %}">

<head>    <meta property="og:type" content="{% block og_type %}website{% endblock %}">

    <!-- Essential Meta Tags -->    <meta property="og:url" content="{% block og_url %}{{ request.build_absolute_uri }}{% endblock %}">

    <meta charset="UTF-8">    <meta property="og:image" content="{% block og_image %}{% static 'images/og-image.jpg' %}{% endblock %}">

    <meta name="viewport" content="width=device-width, initial-scale=1.0">    <meta property="og:image:alt" content="{% block og_image_alt %}Your Brand Logo{% endblock %}">

    <meta http-equiv="X-UA-Compatible" content="IE=edge">    <meta property="og:site_name" content="Your Brand Name">

        <meta property="og:locale" content="en_US">

    <!-- SEO Meta Tags -->    

    <title>{% block title %}My Django Project{% endblock %} | Your Brand Name</title>    <!-- Twitter Card Meta Tags -->

    <meta name="description" content="{% block description %}Your comprehensive Django application with modern design and functionality.{% endblock %}">    <meta name="twitter:card" content="summary_large_image">

    <meta name="keywords" content="{% block keywords %}django, web development, tailwindcss, daisyui, htmx, alpine.js{% endblock %}">    <meta name="twitter:site" content="@yourtwitterhandle">

    <meta name="author" content="Your Name or Company">    <meta name="twitter:creator" content="@yourtwitterhandle">

    <meta name="robots" content="index, follow">    <meta name="twitter:title" content="{% block twitter_title %}{% block title %}My Django Project{% endblock %}{% endblock %}">

    <meta name="language" content="English">    <meta name="twitter:description" content="{% block twitter_description %}{% block description %}Your comprehensive Django application with modern design and functionality.{% endblock %}{% endblock %}">

    <meta name="revisit-after" content="7 days">    <meta name="twitter:image" content="{% block twitter_image %}{% static 'images/twitter-card.jpg' %}{% endblock %}">

        

    <!-- Canonical URL -->    <!-- Favicon -->

    <link rel="canonical" href="{% block canonical %}{{ request.build_absolute_uri }}{% endblock %}">    <link rel="icon" type="image/png" sizes="32x32" href="{% static 'images/favicon-32x32.png' %}">

        <link rel="icon" type="image/png" sizes="16x16" href="{% static 'images/favicon-16x16.png' %}">

    <!-- Open Graph Meta Tags (Facebook, LinkedIn) -->    <link rel="apple-touch-icon" sizes="180x180" href="{% static 'images/apple-touch-icon.png' %}">

    <meta property="og:title" content="{% block og_title %}{% block title %}My Django Project{% endblock %}{% endblock %}">    <link rel="manifest" href="{% static 'site.webmanifest' %}">

    <meta property="og:description" content="{% block og_description %}{% block description %}Your comprehensive Django application with modern design and functionality.{% endblock %}{% endblock %}">    

    <meta property="og:type" content="{% block og_type %}website{% endblock %}">    <!-- Theme Color -->

    <meta property="og:url" content="{% block og_url %}{{ request.build_absolute_uri }}{% endblock %}">    <meta name="theme-color" content="#3b82f6">

    <meta property="og:image" content="{% block og_image %}{% static 'images/og-image.jpg' %}{% endblock %}">    <meta name="msapplication-TileColor" content="#3b82f6">

    <meta property="og:image:alt" content="{% block og_image_alt %}Your Brand Logo{% endblock %}">    

    <meta property="og:site_name" content="Your Brand Name">    <!-- TailwindCSS Output (Auto-generated by django-tailwind-cli) -->

    <meta property="og:locale" content="en_US">    {% tailwind_css %}

        

    <!-- Twitter Card Meta Tags -->    <!-- Alpine.js - Lightweight JavaScript Framework -->

    <meta name="twitter:card" content="summary_large_image">    <script defer src="https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js"></script>

    <meta name="twitter:site" content="@yourtwitterhandle">    

    <meta name="twitter:creator" content="@yourtwitterhandle">    <!-- HTMX - Modern Browser Features from HTML -->

    <meta name="twitter:title" content="{% block twitter_title %}{% block title %}My Django Project{% endblock %}{% endblock %}">    <script src="https://unpkg.com/htmx.org@2.0.3"></script>

    <meta name="twitter:description" content="{% block twitter_description %}{% block description %}Your comprehensive Django application with modern design and functionality.{% endblock %}{% endblock %}">    

    <meta name="twitter:image" content="{% block twitter_image %}{% static 'images/twitter-card.jpg' %}{% endblock %}">    <!-- Additional Stylesheets -->

        {% block extra_css %}{% endblock %}

    <!-- Favicon -->    

    <link rel="icon" type="image/png" sizes="32x32" href="{% static 'images/favicon-32x32.png' %}">    <!-- Structured Data (JSON-LD) -->

    <link rel="icon" type="image/png" sizes="16x16" href="{% static 'images/favicon-16x16.png' %}">    <script type="application/ld+json">

    <link rel="apple-touch-icon" sizes="180x180" href="{% static 'images/apple-touch-icon.png' %}">    {

    <link rel="manifest" href="{% static 'site.webmanifest' %}">        "@context": "https://schema.org",

            "@type": "{% block schema_type %}WebSite{% endblock %}",

    <!-- Theme Color -->        "name": "Your Brand Name",

    <meta name="theme-color" content="#3b82f6">        "url": "{{ request.scheme }}://{{ request.get_host }}",

    <meta name="msapplication-TileColor" content="#3b82f6">        "description": "{% block schema_description %}Your comprehensive Django application with modern design and functionality.{% endblock %}",

            "publisher": {

    <!-- TailwindCSS Output (Auto-generated by django-tailwind-cli) -->            "@type": "Organization",

    {% tailwind_css %}            "name": "Your Brand Name",

                "logo": {

    <!-- Alpine.js - Lightweight JavaScript Framework -->                "@type": "ImageObject",

    <script defer src="https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js"></script>                "url": "{% static 'images/logo.png' %}"

                }

    <!-- HTMX - Modern Browser Features from HTML -->        }

    <script src="https://unpkg.com/htmx.org@2.0.3"></script>    }

        </script>

    <!-- Additional Stylesheets -->    

    {% block extra_css %}{% endblock %}    {% block extra_head %}{% endblock %}

    </head>

    <!-- Structured Data (JSON-LD) -->

    <script type="application/ld+json"><body class="bg-primary text-primary transition-theme antialiased" x-data="{ darkMode: false }" :class="{ 'dark': darkMode }">

    {    <!-- Skip to main content for accessibility -->

        "@context": "https://schema.org",    <a href="#main-content" class="sr-only focus:not-sr-only focus:absolute focus:top-4 focus:left-4 bg-primary text-white px-4 py-2 rounded-md z-50">

        "@type": "{% block schema_type %}WebSite{% endblock %}",        Skip to main content

        "name": "Your Brand Name",    </a>

        "url": "{{ request.scheme }}://{{ request.get_host }}",

        "description": "{% block schema_description %}Your comprehensive Django application with modern design and functionality.{% endblock %}",    <!-- Header/Navigation -->

        "publisher": {    <header class="bg-secondary border-b border-custom sticky top-0 z-40 transition-theme">

            "@type": "Organization",        <nav class="container py-4" x-data="{ mobileMenuOpen: false }">

            "name": "Your Brand Name",            <div class="flex items-center justify-between">

            "logo": {                <div class="flex items-center space-x-2">

                "@type": "ImageObject",                    <a href="/" class="text-2xl font-bold" style="color: rgb(var(--color-logo))">

                "url": "{% static 'images/logo.png' %}"                        YourLogo

            }                    </a>

        }                </div>

    }                

    </script>                <div class="hidden md:flex items-center space-x-6">

                        <a href="/" class="text-primary hover:text-subtitle transition">Home</a>

    {% block extra_head %}{% endblock %}                    <a href="#" class="text-primary hover:text-subtitle transition">About</a>

</head>                    <a href="#" class="text-primary hover:text-subtitle transition">Services</a>

                    <a href="#" class="text-primary hover:text-subtitle transition">Contact</a>

<body class="bg-primary text-primary transition-theme antialiased" x-data="{ darkMode: false }" :class="{ 'dark': darkMode }">                </div>

    <!-- Skip to main content for accessibility -->                

    <a href="#main-content" class="sr-only focus:not-sr-only focus:absolute focus:top-4 focus:left-4 bg-primary text-white px-4 py-2 rounded-md z-50">                <!-- Dark Mode Toggle (Alpine.js) -->

        Skip to main content                <button 

    </a>                    @click="darkMode = !darkMode; localStorage.setItem('darkMode', darkMode)"

                    x-init="darkMode = localStorage.getItem('darkMode') === 'true'"

    <!-- Header/Navigation -->                    type="button" 

    <header class="bg-secondary border-b border-custom sticky top-0 z-40 transition-theme">                    class="p-2 rounded-lg hover:bg-tertiary transition" 

        <nav class="container py-4" x-data="{ mobileMenuOpen: false }">                    aria-label="Toggle dark mode"

            <div class="flex items-center justify-between">                >

                <div class="flex items-center space-x-2">                    <svg x-show="!darkMode" class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20">

                    <a href="/" class="text-2xl font-bold" style="color: rgb(var(--color-logo))">                        <path d="M17.293 13.293A8 8 0 016.707 2.707a8.001 8.001 0 1010.586 10.586z"></path>

                        YourLogo                    </svg>

                    </a>                    <svg x-show="darkMode" class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20">

                </div>                        <path d="M10 2a1 1 0 011 1v1a1 1 0 11-2 0V3a1 1 0 011-1zm4 8a4 4 0 11-8 0 4 4 0 018 0zm-.464 4.95l.707.707a1 1 0 001.414-1.414l-.707-.707a1 1 0 00-1.414 1.414zm2.12-10.607a1 1 0 010 1.414l-.706.707a1 1 0 11-1.414-1.414l.707-.707a1 1 0 011.414 0zM17 11a1 1 0 100-2h-1a1 1 0 100 2h1zm-7 4a1 1 0 011 1v1a1 1 0 11-2 0v-1a1 1 0 011-1zM5.05 6.464A1 1 0 106.465 5.05l-.708-.707a1 1 0 00-1.414 1.414l.707.707zm1.414 8.486l-.707.707a1 1 0 01-1.414-1.414l.707-.707a1 1 0 011.414 1.414zM4 11a1 1 0 100-2H3a1 1 0 000 2h1z" fill-rule="evenodd" clip-rule="evenodd"></path>

                                    </svg>

                <div class="hidden md:flex items-center space-x-6">                </button>

                    <a href="/" class="text-primary hover:text-subtitle transition">Home</a>                

                    <a href="#" class="text-primary hover:text-subtitle transition">About</a>                <!-- Mobile Menu Button (Alpine.js) -->

                    <a href="#" class="text-primary hover:text-subtitle transition">Services</a>                <button 

                    <a href="#" class="text-primary hover:text-subtitle transition">Contact</a>                    @click="mobileMenuOpen = !mobileMenuOpen"

                </div>                    class="md:hidden p-2 rounded-lg hover:bg-tertiary transition" 

                                    aria-label="Toggle menu"

                <!-- Dark Mode Toggle (Alpine.js) -->                >

                <button                     <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">

                    @click="darkMode = !darkMode; localStorage.setItem('darkMode', darkMode)"                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>

                    x-init="darkMode = localStorage.getItem('darkMode') === 'true'"                    </svg>

                    type="button"                 </button>

                    class="p-2 rounded-lg hover:bg-tertiary transition"             </div>

                    aria-label="Toggle dark mode"            

                >            <!-- Mobile Menu (Alpine.js) -->

                    <svg x-show="!darkMode" class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20">            <div x-show="mobileMenuOpen" x-transition class="md:hidden mt-4 pb-4 space-y-2">

                        <path d="M17.293 13.293A8 8 0 016.707 2.707a8.001 8.001 0 1010.586 10.586z"></path>                <a href="/" class="block text-primary hover:text-subtitle transition py-2">Home</a>

                    </svg>                <a href="#" class="block text-primary hover:text-subtitle transition py-2">About</a>

                    <svg x-show="darkMode" class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20">                <a href="#" class="block text-primary hover:text-subtitle transition py-2">Services</a>

                        <path d="M10 2a1 1 0 011 1v1a1 1 0 11-2 0V3a1 1 0 011-1zm4 8a4 4 0 11-8 0 4 4 0 018 0zm-.464 4.95l.707.707a1 1 0 001.414-1.414l-.707-.707a1 1 0 00-1.414 1.414zm2.12-10.607a1 1 0 010 1.414l-.706.707a1 1 0 11-1.414-1.414l.707-.707a1 1 0 011.414 0zM17 11a1 1 0 100-2h-1a1 1 0 100 2h1zm-7 4a1 1 0 011 1v1a1 1 0 11-2 0v-1a1 1 0 011-1zM5.05 6.464A1 1 0 106.465 5.05l-.708-.707a1 1 0 00-1.414 1.414l.707.707zm1.414 8.486l-.707.707a1 1 0 01-1.414-1.414l.707-.707a1 1 0 011.414 1.414zM4 11a1 1 0 100-2H3a1 1 0 000 2h1z" fill-rule="evenodd" clip-rule="evenodd"></path>                <a href="#" class="block text-primary hover:text-subtitle transition py-2">Contact</a>

                    </svg>            </div>

                </button>        </nav>

                    </header>

                <!-- Mobile Menu Button (Alpine.js) -->

                <button     <!-- Main Content -->

                    @click="mobileMenuOpen = !mobileMenuOpen"    <main id="main-content" class="min-h-screen">

                    class="md:hidden p-2 rounded-lg hover:bg-tertiary transition"         <!-- Messages -->

                    aria-label="Toggle menu"        {% if messages %}

                >        <div class="container mt-6">

                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">            {% for message in messages %}

                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>            <div class="{% if message.tags == 'error' %}bg-red-100 border-red-400 text-red-700{% elif message.tags == 'success' %}bg-green-100 border-green-400 text-green-700{% elif message.tags == 'warning' %}bg-yellow-100 border-yellow-400 text-yellow-700{% else %}bg-blue-100 border-blue-400 text-blue-700{% endif %} border px-4 py-3 rounded relative mb-4" role="alert">

                    </svg>                <span class="block sm:inline">{{ message }}</span>

                </button>            </div>

            </div>            {% endfor %}

                    </div>

            <!-- Mobile Menu (Alpine.js) -->        {% endif %}

            <div x-show="mobileMenuOpen" x-transition class="md:hidden mt-4 pb-4 space-y-2">        

                <a href="/" class="block text-primary hover:text-subtitle transition py-2">Home</a>        <!-- Page Content -->

                <a href="#" class="block text-primary hover:text-subtitle transition py-2">About</a>        {% block content %}{% endblock %}

                <a href="#" class="block text-primary hover:text-subtitle transition py-2">Services</a>    </main>

                <a href="#" class="block text-primary hover:text-subtitle transition py-2">Contact</a>

            </div>    <!-- Footer -->

        </nav>    <footer class="bg-secondary border-t border-custom mt-16 transition-theme">

    </header>        <div class="container py-8">

            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">

    <!-- Main Content -->                <div>

    <main id="main-content" class="min-h-screen">                    <h3 class="text-title font-bold text-lg mb-4">About Us</h3>

        <!-- Messages -->                    <p class="text-secondary">Your comprehensive Django application with modern design and functionality.</p>

        {% if messages %}                </div>

        <div class="container mt-6">                <div>

            {% for message in messages %}                    <h3 class="text-title font-bold text-lg mb-4">Quick Links</h3>

            <div class="alert {% if message.tags == 'error' %}alert-error{% elif message.tags == 'success' %}alert-success{% elif message.tags == 'warning' %}alert-warning{% else %}alert-info{% endif %}" role="alert">                    <ul class="space-y-2">

                <span>{{ message }}</span>                        <li><a href="#" class="text-secondary hover:text-subtitle transition">Privacy Policy</a></li>

            </div>                        <li><a href="#" class="text-secondary hover:text-subtitle transition">Terms of Service</a></li>

            {% endfor %}                        <li><a href="#" class="text-secondary hover:text-subtitle transition">Contact</a></li>

        </div>                    </ul>

        {% endif %}                </div>

                        <div>

        <!-- Page Content -->                    <h3 class="text-title font-bold text-lg mb-4">Follow Us</h3>

        {% block content %}{% endblock %}                    <div class="flex space-x-4">

    </main>                        <a href="#" class="text-secondary hover:text-subtitle transition" aria-label="Facebook">

                            <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24"><path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/></svg>

    <!-- Footer -->                        </a>

    <footer class="bg-secondary border-t border-custom mt-16 transition-theme">                        <a href="#" class="text-secondary hover:text-subtitle transition" aria-label="Twitter">

        <div class="container py-8">                            <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24"><path d="M23.953 4.57a10 10 0 01-2.825.775 4.958 4.958 0 002.163-2.723c-.951.555-2.005.959-3.127 1.184a4.92 4.92 0 00-8.384 4.482C7.69 8.095 4.067 6.13 1.64 3.162a4.822 4.822 0 00-.666 2.475c0 1.71.87 3.213 2.188 4.096a4.904 4.904 0 01-2.228-.616v.06a4.923 4.923 0 003.946 4.827 4.996 4.996 0 01-2.212.085 4.936 4.936 0 004.604 3.417 9.867 9.867 0 01-6.102 2.105c-.39 0-.779-.023-1.17-.067a13.995 13.995 0 007.557 2.209c9.053 0 13.998-7.496 13.998-13.985 0-.21 0-.42-.015-.63A9.935 9.935 0 0024 4.59z"/></svg>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">                        </a>

                <div>                    </div>

                    <h3 class="text-title font-bold text-lg mb-4">About Us</h3>                </div>

                    <p class="text-secondary">Your comprehensive Django application with modern design and functionality.</p>            </div>

                </div>            <div class="border-t border-custom mt-8 pt-8 text-center text-secondary">

                <div>                <p>&copy; 2025 Your Brand Name. All rights reserved.</p>

                    <h3 class="text-title font-bold text-lg mb-4">Quick Links</h3>            </div>

                    <ul class="space-y-2">        </div>

                        <li><a href="#" class="text-secondary hover:text-subtitle transition">Privacy Policy</a></li>    </footer>

                        <li><a href="#" class="text-secondary hover:text-subtitle transition">Terms of Service</a></li>

                        <li><a href="#" class="text-secondary hover:text-subtitle transition">Contact</a></li>    {% block extra_js %}{% endblock %}

                    </ul></body>

                </div></html>

                <div>```

                    <h3 class="text-title font-bold text-lg mb-4">Follow Us</h3>

                    <div class="flex space-x-4">---

                        <a href="#" class="text-secondary hover:text-subtitle transition" aria-label="Facebook">

                            <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24"><path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/></svg>## 🔧 Step 9: Configure URLs for Static and Media Files

                        </a>

                        <a href="#" class="text-secondary hover:text-subtitle transition" aria-label="Twitter">### Update `config/urls.py`

                            <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24"><path d="M23.953 4.57a10 10 0 01-2.825.775 4.958 4.958 0 002.163-2.723c-.951.555-2.005.959-3.127 1.184a4.92 4.92 0 00-8.384 4.482C7.69 8.095 4.067 6.13 1.64 3.162a4.822 4.822 0 00-.666 2.475c0 1.71.87 3.213 2.188 4.096a4.904 4.904 0 01-2.228-.616v.06a4.923 4.923 0 003.946 4.827 4.996 4.996 0 01-2.212.085 4.936 4.936 0 004.604 3.417 9.867 9.867 0 01-6.102 2.105c-.39 0-.779-.023-1.17-.067a13.995 13.995 0 007.557 2.209c9.053 0 13.998-7.496 13.998-13.985 0-.21 0-.42-.015-.63A9.935 9.935 0 0024 4.59z"/></svg>```python

                        </a>from django.contrib import admin

                    </div>from django.urls import path, include

                </div>from django.conf import settings

            </div>from django.conf.urls.static import static

            <div class="border-t border-custom mt-8 pt-8 text-center text-secondary">

                <p>&copy; 2025 Your Brand Name. All rights reserved.</p>urlpatterns = [

            </div>    path('admin/', admin.site.urls),

        </div>    path('', include('core.urls')),

    </footer>    path("__reload__/", include("django_browser_reload.urls")),  # Browser auto-reload

]

    {% block extra_js %}{% endblock %}

</body># Serve static and media files in development

</html>if settings.DEBUG:

```    urlpatterns += static(settings.STATIC_URL, document_root=settings.STATIC_ROOT)

    urlpatterns += static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)

---```



## 🔧 Step 9: Configure URLs for Static and Media Files### Create `core/urls.py`

```python

### Update `config/urls.py`from django.urls import path

```pythonfrom . import views

from django.contrib import admin

from django.urls import path, includeapp_name = 'core'

from django.conf import settings

from django.conf.urls.static import staticurlpatterns = [

    path('', views.home, name='home'),

urlpatterns = []

    path('admin/', admin.site.urls),```

    path('', include('core.urls')),

    path("__reload__/", include("django_browser_reload.urls")),  # Browser auto-reload### Create `core/views.py`

]```python

from django.shortcuts import render

# Serve static and media files in development

if settings.DEBUG:def home(request):

    urlpatterns += static(settings.STATIC_URL, document_root=settings.STATIC_ROOT)    return render(request, 'core/home.html')

    urlpatterns += static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)```

```

### Create `templates/core/home.html`

### Create `core/urls.py````html

```python{% extends 'base.html' %}

from django.urls import path

from . import views{% block title %}Home{% endblock %}



app_name = 'core'{% block content %}

<div class="container py-16">

urlpatterns = [    <div class="text-center">

    path('', views.home, name='home'),        <h1 class="text-title text-5xl font-bold mb-4">Welcome to Django + TailwindCSS</h1>

]        <p class="text-description text-xl mb-8">Built with django-tailwind-cli and DaisyUI - No Node.js Required!</p>

```        

        <div class="grid grid-cols-1 md:grid-cols-3 gap-8 mt-12">

### Create `core/views.py`            <div class="card">

```python                <h2 class="card-title">Fast Setup</h2>

from django.shortcuts import render                <p class="card-body">Get started quickly with no Node.js or npm dependencies.</p>

            </div>

def home(request):            

    return render(request, 'core/home.html')            <div class="card">

```                <h2 class="card-title">Modern Design</h2>

                <p class="card-body">Beautiful UI with TailwindCSS and DaisyUI components.</p>

### Create `templates/core/home.html`            </div>

```html            

{% extends 'base.html' %}            <div class="card">

                <h2 class="card-title">SEO Ready</h2>

{% block title %}Home{% endblock %}                <p class="card-body">Optimized templates with comprehensive SEO meta tags.</p>

            </div>

{% block content %}        </div>

<div class="container py-16">    </div>

    <div class="text-center"></div>

        <h1 class="text-title text-5xl font-bold mb-4">Welcome to Django + TailwindCSS</h1>{% endblock %}

        <p class="text-description text-xl mb-8">Built with django-tailwind-cli and DaisyUI - No Node.js Required!</p>```

        

        <div class="grid grid-cols-1 md:grid-cols-3 gap-8 mt-12">---

            <div class="card bg-base-100 shadow-xl">

                <div class="card-body">## 🗃️ Step 10: Collect Static Files

                    <h2 class="card-title">Fast Setup</h2>

                    <p>Get started quickly with no Node.js or npm dependencies.</p>### Collect all static files for production

                </div>```bash

            </div>uv run manage.py collectstatic --noinput

            ```

            <div class="card bg-base-100 shadow-xl">

                <div class="card-body">This command will:

                    <h2 class="card-title">Modern Design</h2>- Copy all static files from your apps and `STATICFILES_DIRS` to `STATIC_ROOT`

                    <p>Beautiful UI with TailwindCSS and DaisyUI components.</p>- Make files ready for production deployment

                </div>- Include your compiled CSS from TailwindCSS

            </div>

            **Note:** Run this command every time you update static files before deploying to production.

            <div class="card bg-base-100 shadow-xl">

                <div class="card-body">---

                    <h2 class="card-title">SEO Ready</h2>

                    <p>Optimized templates with comprehensive SEO meta tags.</p>## 🚀 Step 11: Run Migrations and Create Superuser

                </div>

            </div>### Run database migrations

        </div>```bash

    </div>uv run manage.py makemigrations

</div>uv run manage.py migrate

{% endblock %}```

```

### Create admin superuser

---```bash

uv run manage.py createsuperuser

## 🗃️ Step 10: Collect Static Files```



### Collect all static files for productionFollow the prompts to set username, email, and password.

```bash

uv run manage.py collectstatic --noinput---

```

## ▶️ Step 12: Run Development Server

This command will:

- Copy all static files from your apps and `STATICFILES_DIRS` to `STATIC_ROOT`### Option 1: Standard Django server

- Make files ready for production deployment```bash

- Include your compiled CSS from TailwindCSSuv run manage.py runserver

```

**Note:** Run this command every time you update static files before deploying to production.

### Option 2: With TailwindCSS auto-compilation (Recommended)

---```bash

uv run manage.py tailwind runserver

## 🚀 Step 11: Run Migrations and Create Superuser```



### Run database migrationsThis command starts both:

```bash- Django development server on **http://127.0.0.1:8000/**

uv run manage.py makemigrations- TailwindCSS watch mode (auto-rebuilds CSS on changes)

uv run manage.py migrate

```Visit: **http://127.0.0.1:8000/**  

Admin panel: **http://127.0.0.1:8000/admin/**

### Create admin superuser

```bash**Benefits:**

uv run manage.py createsuperuser- ✅ Auto browser reload on file changes

```- ✅ Auto CSS compilation on template/CSS changes

- ✅ Single command for full dev environment

Follow the prompts to set username, email, and password.

---

---

## 🎨 Step 13: Using DaisyUI Components

## ▶️ Step 12: Run Development Server

## 🎨 Step 13: Using DaisyUI Components

### Option 1: Standard Django server

```bash### Available DaisyUI Themes

uv run manage.py runserverYou configured these themes in `source.css`:

```- light, dark, cupcake, synthwave, retro, cyberpunk, valentine, halloween, garden, forest, aqua, lofi, pastel, fantasy, wireframe, black, luxury, dracula, cmyk, autumn, business, acid, lemonade, night, coffee, winter



### Option 2: With TailwindCSS auto-compilation (Recommended)### Switch themes dynamically

```bash```html

uv run manage.py tailwind runserver<!-- Add to your template -->

```<select data-choose-theme class="select select-bordered">

    <option value="light">Light</option>

This command starts both:    <option value="dark">Dark</option>

- Django development server on **http://127.0.0.1:8000/**    <option value="cupcake">Cupcake</option>

- TailwindCSS watch mode (auto-rebuilds CSS on changes)    <option value="synthwave">Synthwave</option>

    <option value="retro">Retro</option>

Visit: **http://127.0.0.1:8000/**  </select>

Admin panel: **http://127.0.0.1:8000/admin/**```



**Benefits:**### Example DaisyUI Components

- ✅ Auto browser reload on file changes

- ✅ Auto CSS compilation on template/CSS changes**Button:**

- ✅ Single command for full dev environment```html

<button class="btn btn-primary">Primary Button</button>

---<button class="btn btn-secondary">Secondary Button</button>

<button class="btn btn-accent">Accent Button</button>

## 🎨 Step 13: Using DaisyUI Components```



### Available DaisyUI Themes**Card:**

You configured these themes in `source.css`:```html

- light, dark, cupcake, synthwave, retro, cyberpunk, valentine, halloween, garden, forest, aqua, lofi, pastel, fantasy, wireframe, black, luxury, dracula, cmyk, autumn, business, acid, lemonade, night, coffee, winter<div class="card bg-base-100 shadow-xl">

    <div class="card-body">

### Switch themes dynamically        <h2 class="card-title">Card Title</h2>

```html        <p>Card content goes here</p>

<!-- Add theme switcher -->        <div class="card-actions justify-end">

<select data-choose-theme class="select select-bordered">            <button class="btn btn-primary">Action</button>

    <option value="light">Light</option>        </div>

    <option value="dark">Dark</option>    </div>

    <option value="cupcake">Cupcake</option></div>

    <option value="synthwave">Synthwave</option>```

    <option value="retro">Retro</option>

</select>**Alert:**

```html

<!-- Add theme change JavaScript --><div class="alert alert-success">

<script src="https://cdn.jsdelivr.net/npm/theme-change@2.0.2/index.js"></script>    <span>Success! Your operation completed.</span>

```</div>

```

### Example DaisyUI Components

**Badge:**

**Buttons:**```html

```html<span class="badge badge-primary">Primary</span>

<button class="btn btn-primary">Primary Button</button><span class="badge badge-secondary">Secondary</span>

<button class="btn btn-secondary">Secondary Button</button>```

<button class="btn btn-accent">Accent Button</button>

<button class="btn btn-ghost">Ghost Button</button>**Modal:**

<button class="btn btn-link">Link Button</button>```html

```<dialog id="my_modal" class="modal">

    <div class="modal-box">

**Cards:**        <h3 class="font-bold text-lg">Hello!</h3>

```html        <p class="py-4">This is a modal dialog</p>

<div class="card bg-base-100 shadow-xl">        <div class="modal-action">

    <figure><img src="https://via.placeholder.com/400x225" alt="Album" /></figure>            <form method="dialog">

    <div class="card-body">                <button class="btn">Close</button>

        <h2 class="card-title">Card Title</h2>            </form>

        <p>Card content goes here</p>        </div>

        <div class="card-actions justify-end">    </div>

            <button class="btn btn-primary">Buy Now</button></dialog>

        </div><button class="btn" onclick="my_modal.showModal()">Open Modal</button>

    </div>```

</div>

```**Navbar:**

```html

**Alerts:**<div class="navbar bg-base-100">

```html    <div class="flex-1">

<div class="alert alert-success">        <a class="btn btn-ghost text-xl">MyApp</a>

    <svg xmlns="http://www.w3.org/2000/svg" class="stroke-current shrink-0 h-6 w-6" fill="none" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" /></svg>    </div>

    <span>Your purchase has been confirmed!</span>    <div class="flex-none">

</div>        <ul class="menu menu-horizontal px-1">

            <li><a>Link</a></li>

<div class="alert alert-warning">            <li><a>Link</a></li>

    <svg xmlns="http://www.w3.org/2000/svg" class="stroke-current shrink-0 h-6 w-6" fill="none" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 9v2m0 4h.01m-6.938 4h13.856c1.54 0 2.502-1.667 1.732-3L13.732 4c-.77-1.333-2.694-1.333-3.464 0L3.34 16c-.77 1.333.192 3 1.732 3z" /></svg>        </ul>

    <span>Warning: Invalid email address!</span>    </div>

</div></div>

``````



**Badges:**See all components: [https://daisyui.com/components/](https://daisyui.com/components/)

```html

<span class="badge badge-primary">Primary</span>---

<span class="badge badge-secondary">Secondary</span>

<span class="badge badge-accent">Accent</span>## 🔥 Step 14: Alpine.js Examples

<span class="badge badge-ghost">Ghost</span>

```### Toggle Example

```html

**Modal:**<div x-data="{ open: false }">

```html    <button @click="open = !open" class="btn btn-primary">Toggle</button>

<button class="btn" onclick="my_modal.showModal()">Open Modal</button>    <div x-show="open" class="alert alert-info mt-4">

        This content can be toggled!

<dialog id="my_modal" class="modal">    </div>

    <div class="modal-box"></div>

        <h3 class="font-bold text-lg">Hello!</h3>```

        <p class="py-4">Press ESC key or click the button below to close</p>

        <div class="modal-action">### Counter Example

            <form method="dialog">```html

                <button class="btn">Close</button><div x-data="{ count: 0 }">

            </form>    <button @click="count++" class="btn btn-success">Increment</button>

        </div>    <button @click="count--" class="btn btn-error">Decrement</button>

    </div>    <p class="text-xl mt-4">Count: <span x-text="count"></span></p>

</dialog></div>

``````



**Navbar:**### Dropdown Example

```html```html

<div class="navbar bg-base-100"><div x-data="{ isOpen: false }" @click.away="isOpen = false">

    <div class="flex-1">    <button @click="isOpen = !isOpen" class="btn btn-primary">

        <a class="btn btn-ghost text-xl">daisyUI</a>        Menu

    </div>    </button>

    <div class="flex-none">    <ul x-show="isOpen" class="menu bg-base-200 w-56 rounded-box mt-2">

        <ul class="menu menu-horizontal px-1">        <li><a>Item 1</a></li>

            <li><a>Link</a></li>        <li><a>Item 2</a></li>

            <li>        <li><a>Item 3</a></li>

                <details>    </ul>

                    <summary>Parent</summary></div>

                    <ul class="p-2 bg-base-100 rounded-t-none">```

                        <li><a>Link 1</a></li>

                        <li><a>Link 2</a></li>---

                    </ul>

                </details>## ⚡ Step 15: HTMX Examples

            </li>

        </ul>### Load Content Without Page Reload

    </div>```html

</div><!-- Button to load content -->

```<button hx-get="{% url 'load_content' %}" 

        hx-target="#content" 

See all components: [https://daisyui.com/components/](https://daisyui.com/components/)        hx-swap="innerHTML"

        class="btn btn-primary">

---    Load Content

</button>

## 🔥 Step 14: Alpine.js Examples

<!-- Content will appear here -->

### Toggle Example<div id="content"></div>

```html```

<div x-data="{ open: false }">

    <button @click="open = !open" class="btn btn-primary">Toggle</button>**Django View:**

    <div x-show="open" x-transition class="alert alert-info mt-4">```python

        This content can be toggled!def load_content(request):

    </div>    return render(request, 'partials/content.html')

</div>```

```

### Form Submission with HTMX

### Counter Example```html

```html<form hx-post="{% url 'submit_form' %}" 

<div x-data="{ count: 0 }" class="text-center">      hx-target="#result"

    <button @click="count++" class="btn btn-success">Increment</button>      hx-swap="innerHTML">

    <button @click="count--" class="btn btn-error">Decrement</button>    {% csrf_token %}

    <p class="text-2xl mt-4">Count: <span x-text="count" class="font-bold"></span></p>    <input type="text" name="name" placeholder="Name" class="input input-bordered">

</div>    <button type="submit" class="btn btn-primary">Submit</button>

```</form>



### Dropdown Example<div id="result"></div>

```html```

<div x-data="{ isOpen: false }" @click.away="isOpen = false" class="relative">

    <button @click="isOpen = !isOpen" class="btn btn-primary">**Django View:**

        Menu```python

    </button>def submit_form(request):

    <ul x-show="isOpen" x-transition class="menu bg-base-200 w-56 rounded-box mt-2 absolute">    if request.method == 'POST' and request.htmx:

        <li><a>Item 1</a></li>        name = request.POST.get('name')

        <li><a>Item 2</a></li>        return HttpResponse(f'<p class="alert alert-success">Hello, {name}!</p>')

        <li><a>Item 3</a></li>    return HttpResponse('Invalid request')

    </ul>```

</div>

```### Infinite Scroll

```html

### Form Validation<div id="posts">

```html    {% for post in posts %}

<div x-data="{ email: '', isValid: false }">    <div class="card bg-base-100 shadow-xl mb-4">

    <input         <div class="card-body">

        x-model="email"             <h2 class="card-title">{{ post.title }}</h2>

        @input="isValid = /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email)"            <p>{{ post.content }}</p>

        type="email"         </div>

        placeholder="Email"     </div>

        class="input input-bordered w-full max-w-xs"    {% endfor %}

    ></div>

    <p x-show="email && !isValid" class="text-error mt-2">Invalid email address</p>

    <p x-show="isValid" class="text-success mt-2">Valid email!</p><!-- Load more trigger -->

</div><div hx-get="{% url 'load_more_posts' %}?page=2" 

```     hx-trigger="revealed" 

     hx-target="#posts" 

---     hx-swap="beforeend">

    <span class="loading loading-spinner loading-lg"></span>

## ⚡ Step 15: HTMX Examples</div>

```

### Load Content Without Page Reload

```html---

<!-- Button to load content -->

<button hx-get="{% url 'load_content' %}" ## 🔐 Step 16: Additional Security Configuration

        hx-target="#content" 

        hx-swap="innerHTML"### Update `config/settings.py` for production

        class="btn btn-primary">

    Load ContentWhen deploying to production, update these settings:

</button>

```python

<!-- Content will appear here --># Production Security Settings

<div id="content" class="mt-4"></div>DEBUG = False

```ALLOWED_HOSTS = ['yourdomain.com', 'www.yourdomain.com']



**Django View:**# HTTPS Settings

```pythonSECURE_SSL_REDIRECT = True

def load_content(request):SESSION_COOKIE_SECURE = True

    return render(request, 'partials/content.html', {'data': 'Hello from HTMX!'})CSRF_COOKIE_SECURE = True

```SECURE_BROWSER_XSS_FILTER = True

SECURE_CONTENT_TYPE_NOSNIFF = True

### Form Submission with HTMXX_FRAME_OPTIONS = 'DENY'

```htmlSECURE_HSTS_SECONDS = 31536000

<form hx-post="{% url 'submit_form' %}" SECURE_HSTS_INCLUDE_SUBDOMAINS = True

      hx-target="#result"SECURE_HSTS_PRELOAD = True

      hx-swap="innerHTML"

      class="space-y-4"># Secret Key - Use environment variable

    {% csrf_token %}import os

    <input type="text" name="name" placeholder="Your Name" class="input input-bordered w-full">SECRET_KEY = os.environ.get('DJANGO_SECRET_KEY', 'your-secret-key-here')

    <button type="submit" class="btn btn-primary">Submit</button>```

</form>

---

<div id="result" class="mt-4"></div>

```## 📚 Step 17: Django Extensions Useful Commands



**Django View:**### Shell Plus (Enhanced Django shell)

```python```bash

from django.http import HttpResponseuv run manage.py shell_plus

```

def submit_form(request):

    if request.method == 'POST' and request.htmx:### Show URLs

        name = request.POST.get('name', '')```bash

        return HttpResponse(f'<div class="alert alert-success">Hello, {name}!</div>')uv run manage.py show_urls

    return HttpResponse('<div class="alert alert-error">Invalid request</div>')```

```

### Generate Secret Key

### Infinite Scroll```bash

```htmluv run manage.py generate_secret_key

<div id="posts">```

    {% for post in posts %}

    <div class="card bg-base-100 shadow-xl mb-4">### Clean PyC files

        <div class="card-body">```bash

            <h2 class="card-title">{{ post.title }}</h2>uv run manage.py clean_pyc

            <p>{{ post.content }}</p>```

        </div>

    </div>---

    {% endfor %}

</div>## 🍯 Step 18: Honeypot Anti-Spam Setup



<!-- Load more trigger -->### Add honeypot to forms

<div hx-get="{% url 'load_more_posts' %}?page=2" 

     hx-trigger="revealed" In your forms, add the honeypot field:

     hx-target="#posts" 

     hx-swap="beforeend"```python

     class="text-center py-4">from django import forms

    <span class="loading loading-spinner loading-lg"></span>from honeypot.decorators import check_honeypot

</div>

```class ContactForm(forms.Form):

    name = forms.CharField(max_length=100)

### Search with Debounce    email = forms.EmailField()

```html    message = forms.CharField(widget=forms.Textarea)

<input type="search" ```

       name="q"

       hx-get="{% url 'search' %}"In your view:

       hx-trigger="keyup changed delay:500ms"```python

       hx-target="#search-results"from honeypot.decorators import check_honeypot

       placeholder="Search..."

       class="input input-bordered w-full">@check_honeypot

def contact_view(request):

<div id="search-results" class="mt-4"></div>    if request.method == 'POST':

```        form = ContactForm(request.POST)

        if form.is_valid():

**Django View:**            # Process form

```python            pass

def search(request):    else:

    query = request.GET.get('q', '')        form = ContactForm()

    results = MyModel.objects.filter(name__icontains=query)[:10]    return render(request, 'contact.html', {'form': form})

    return render(request, 'partials/search_results.html', {'results': results})```

```

In your template:

---```html

{% load honeypot %}

## 🔐 Step 16: Additional Security Configuration

<form method="post">

### Update `config/settings.py` for production    {% csrf_token %}

    {% render_honeypot_field %}

When deploying to production, update these settings:    {{ form.as_p }}

    <button type="submit">Submit</button>

```python</form>

# Production Security Settings```

DEBUG = False

ALLOWED_HOSTS = ['yourdomain.com', 'www.yourdomain.com']---



# HTTPS Settings## 🧩 Step 19: Django Cotton Component Usage

SECURE_SSL_REDIRECT = True

SESSION_COOKIE_SECURE = True### Create a component in `templates/cotton/`

CSRF_COOKIE_SECURE = True

SECURE_BROWSER_XSS_FILTER = TrueExample: `templates/cotton/button.html`

SECURE_CONTENT_TYPE_NOSNIFF = True```html

X_FRAME_OPTIONS = 'DENY'<c-vars primary_color="blue" />

SECURE_HSTS_SECONDS = 31536000

SECURE_HSTS_INCLUDE_SUBDOMAINS = True<button class="px-4 py-2 bg-{{ primary_color }}-500 text-white rounded hover:bg-{{ primary_color }}-600 transition">

SECURE_HSTS_PRELOAD = True    <c-slot />

</button>

# Secret Key - Use environment variable```

import os

SECRET_KEY = os.environ.get('DJANGO_SECRET_KEY', 'your-secret-key-here')### Use in templates

``````html

{% load cotton %}

---

<c-button primary_color="green">

## 📚 Step 17: Django Extensions Useful Commands    Click Me

</c-button>

### Shell Plus (Enhanced Django shell)```

```bash

uv run manage.py shell_plus---

```

## 📦 Step 20: Project Structure

### Show URLs

```bashYour final project structure should look like this:

uv run manage.py show_urls

``````

myproject/

### Generate Secret Key├── .venv/

```bash├── config/

uv run manage.py generate_secret_key│   ├── __init__.py

```│   ├── settings.py

│   ├── urls.py

### Clean PyC files│   ├── asgi.py

```bash│   └── wsgi.py

uv run manage.py clean_pyc├── core/

```│   ├── migrations/

│   ├── __init__.py

---│   ├── admin.py

│   ├── apps.py

## 🍯 Step 18: Honeypot Anti-Spam Setup│   ├── models.py

│   ├── tests.py

### Add honeypot to forms│   ├── urls.py

│   └── views.py

In your forms, add the honeypot field:├── templates/

│   ├── base.html

```python│   ├── core/

from django import forms│   │   └── home.html

from honeypot.decorators import check_honeypot│   └── cotton/

│       └── button.html

class ContactForm(forms.Form):├── static/

    name = forms.CharField(max_length=100)│   ├── css/

    email = forms.EmailField()│   │   ├── source.css

    message = forms.CharField(widget=forms.Textarea)│   │   └── output.css

```│   ├── js/

│   └── images/

In your view:├── media/

```python├── staticfiles/

from honeypot.decorators import check_honeypot├── manage.py

├── requirements.txt

@check_honeypot└── README.md

def contact_view(request):```

    if request.method == 'POST':

        form = ContactForm(request.POST)---

        if form.is_valid():

            # Process form## � Quick Start (TL;DR)

            pass

    else:```bash

        form = ContactForm()# 1. Create and setup project

    return render(request, 'contact.html', {'form': form})mkdir myproject && cd myproject

```uv init

uv venv

In your template:.venv\Scripts\activate

```html

{% load honeypot %}# 2. Install all packages

uv pip install django pillow django-extensions django-cotton django-tailwind-cli honeypot mysqlclient django-htmx django-browser-reload

<form method="post" class="space-y-4">

    {% csrf_token %}# 3. Create Django project

    {% render_honeypot_field %}django-admin startproject config .

    python manage.py startapp core

    <input type="text" name="name" placeholder="Name" class="input input-bordered w-full">mkdir templates static media

    <input type="email" name="email" placeholder="Email" class="input input-bordered w-full">

    <textarea name="message" placeholder="Message" class="textarea textarea-bordered w-full"></textarea># 4. Setup TailwindCSS

    uv run manage.py tailwind setup

    <button type="submit" class="btn btn-primary">Submit</button>uv run manage.py tailwind build

</form>

```# 5. Run migrations

uv run manage.py migrate

---uv run manage.py createsuperuser



## 🧩 Step 19: Django Cotton Component Usage# 6. Start development server

uv run manage.py tailwind runserver

### Create a component in `templates/cotton/````



Example: `templates/cotton/button.html`Visit: **http://127.0.0.1:8000/** 🎉

```html

<c-vars primary_color="blue" />---



<button class="btn btn-{{ primary_color }}">## �🛠️ Troubleshooting

    <c-slot />

</button>### MySQL Connection Issues

```- Make sure MySQL server is running

- Verify database credentials in `settings.py`

### Use in templates- Check if `mysqlclient` is properly installed

```html

<c-button primary_color="primary">### TailwindCSS Not Compiling

    Click Me- Ensure `source.css` exists at `static/css/source.css`

</c-button>- Run `python manage.py tailwind build` manually

- Check for syntax errors in your CSS

<c-button primary_color="secondary">

    Secondary Action### Static Files Not Loading

</c-button>- Run `python manage.py collectstatic`

```- Check `STATIC_URL` and `STATIC_ROOT` in settings

- Ensure `DEBUG = True` for development

---

### Import Errors

## 📦 Step 20: Project Structure- Activate virtual environment: `.venv\Scripts\activate`

- Reinstall packages: `uv pip install -r requirements.txt`

Your final project structure should look like this:

---

```

myproject/## 📝 Additional Resources

├── .venv/

├── config/- **Django Documentation:** https://docs.djangoproject.com/

│   ├── __init__.py- **TailwindCSS Documentation:** https://tailwindcss.com/docs

│   ├── settings.py- **DaisyUI Components:** https://daisyui.com/components/

│   ├── urls.py- **Django TailwindCSS CLI:** https://github.com/oliverandrich/django-tailwind-cli

│   ├── asgi.py

│   └── wsgi.py---

├── core/

│   ├── migrations/## 🎉 You're All Set!

│   ├── __init__.py

│   ├── admin.pyYour Django project with TailwindCSS and DaisyUI is now ready for development. Start building amazing features!

│   ├── apps.py

│   ├── models.py**Happy Coding! 🚀**

│   ├── tests.py
│   ├── urls.py
│   └── views.py
├── templates/
│   ├── base.html
│   ├── core/
│   │   └── home.html
│   └── cotton/
│       └── button.html
├── static/
│   ├── css/
│   │   ├── source.css
│   │   └── output.css
│   ├── js/
│   └── images/
├── media/
├── staticfiles/
├── manage.py
├── requirements.txt
└── README.md
```

---

## 🛠️ Troubleshooting

### ❌ MySQL Connection Issues
**Problem:** Can't connect to MySQL database

**Solutions:**
- Ensure MySQL server is running
- Verify database credentials in `settings.py`
- Check if `mysqlclient` is properly installed
- Try: `uv pip install mysqlclient --force-reinstall`

### ❌ TailwindCSS Not Compiling
**Problem:** CSS changes not appearing

**Solutions:**
- Ensure `source.css` exists at `static/css/source.css`
- Run `uv run manage.py tailwind build` manually
- Check for syntax errors in your CSS
- Delete `static/css/output.css` and rebuild

### ❌ Static Files Not Loading
**Problem:** CSS/JS not loading in browser

**Solutions:**
- Run `uv run manage.py collectstatic`
- Check `STATIC_URL` and `STATIC_ROOT` in settings
- Ensure `DEBUG = True` for development
- Add `{% load static %}` to template
- Clear browser cache

### ❌ Import Errors
**Problem:** Module not found errors

**Solutions:**
- Activate virtual environment: `.venv\Scripts\activate`
- Reinstall packages: `uv pip install -r requirements.txt`
- Check Python version: `python --version` (should be 3.10+)

### ❌ DaisyUI Not Working
**Problem:** DaisyUI classes not applying

**Solutions:**
- Verify `TAILWIND_CLI_USE_DAISY_UI = True` in settings
- Check `@plugin "daisyui"` is in `source.css`
- Rebuild CSS: `uv run manage.py tailwind build`
- Add `data-theme="light"` to `<html>` tag

### ❌ HTMX Not Working
**Problem:** HTMX requests not working

**Solutions:**
- Check HTMX script is loaded in template
- Verify middleware is added: `django_htmx.middleware.HtmxMiddleware`
- Check view returns proper response for HTMX
- Use browser DevTools to check network requests

### ❌ Auto-Reload Not Working
**Problem:** Browser not reloading automatically

**Solutions:**
- Ensure `django_browser_reload` is in `INSTALLED_APPS`
- Add middleware: `django_browser_reload.middleware.BrowserReloadMiddleware`
- Add URL: `path("__reload__/", include("django_browser_reload.urls"))`
- Check `INTERNAL_IPS = ["127.0.0.1"]` in settings

---

## 📝 Development Tips

### 💡 Best Practices

1. **Always use `uv run`** for manage.py commands
2. **Run `tailwind runserver`** during development for auto-compilation
3. **Use Alpine.js** for simple interactivity instead of heavy JavaScript
4. **Use HTMX** for dynamic content loading without full page reloads
5. **Keep `source.css` clean** - use `@layer` directives
6. **Test with different themes** - DaisyUI has 28 built-in themes
7. **Use Django Cotton** for reusable component-based templates

### 🎨 Recommended Workflow

1. Start server with: `uv run manage.py tailwind runserver`
2. Open browser at: `http://127.0.0.1:8000/`
3. Edit templates/CSS - browser auto-reloads
4. Use Alpine.js for UI interactions
5. Use HTMX for server interactions
6. Check browser console for errors

### 📦 Creating requirements.txt

```bash
uv pip freeze > requirements.txt
```

### 🔄 Installing from requirements.txt

```bash
uv pip install -r requirements.txt
```

---

## 📝 Additional Resources

### 📖 Documentation
- **Django Documentation:** https://docs.djangoproject.com/
- **TailwindCSS Documentation:** https://tailwindcss.com/docs
- **DaisyUI Components:** https://daisyui.com/components/
- **Django TailwindCSS CLI:** https://github.com/oliverandrich/django-tailwind-cli
- **Alpine.js Documentation:** https://alpinejs.dev/
- **HTMX Documentation:** https://htmx.org/docs/
- **Django HTMX:** https://django-htmx.readthedocs.io/

### 🎥 Video Tutorials
- Django Official Tutorial: https://docs.djangoproject.com/en/stable/intro/tutorial01/
- TailwindCSS Crash Course: YouTube
- Alpine.js Tutorial: Alpine.js official site

### 🛠️ Tools & Extensions
- **VS Code Extensions:**
  - Python
  - Django
  - Tailwind CSS IntelliSense
  - Alpine.js IntelliSense
  - Better Comments

### 💬 Community Support
- Django Forum: https://forum.djangoproject.com/
- Stack Overflow: https://stackoverflow.com/questions/tagged/django
- Reddit: r/django

---

## 🎉 You're All Set!

Your Django project with TailwindCSS, DaisyUI, Alpine.js, and HTMX is now ready for development!

### 🚀 Next Steps

1. ✅ Customize the color scheme in `source.css`
2. ✅ Create your first model in `core/models.py`
3. ✅ Build beautiful pages with DaisyUI components
4. ✅ Add interactivity with Alpine.js and HTMX
5. ✅ Deploy to production (Heroku, Railway, DigitalOcean)

### 📧 Need Help?

If you encounter issues:
1. Check the Troubleshooting section above
2. Review the documentation links
3. Search on Stack Overflow
4. Ask in Django forums

---

**Happy Coding! 🚀 Built with ❤️ using Django + TailwindCSS + DaisyUI**

---

### ⭐ Star This Guide

If this guide helped you, consider sharing it with others!

**Made with 💙 for the Django community**
