# 🌸 Django + Tailwind CSS + DaisyUI Setup Guide 🌸

![Django](https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![Alpine.js](https://img.shields.io/badge/Alpine.js-8BC0D0?style=for-the-badge&logo=alpine.js&logoColor=black)
![HTMX](https://img.shields.io/badge/HTMX-36C?style=for-the-badge&logo=htmx&logoColor=white)

> A modern, production-ready Django setup with Tailwind CSS, DaisyUI, Alpine.js, HTMX, and Jazzmin admin. **No Node.js or npm required!**

---

## 📋 Table of Contents

- [Features](#-features)
- [Prerequisites](#-prerequisites)
- [Quick Start](#-quick-start)
- [Installation Steps](#-installation-steps)
- [Configuration](#-configuration)
- [Database Setup (Optional)](#-database-setup-optional)
- [Running the Project](#-running-the-project)
- [Project Structure](#-project-structure)
- [Tech Stack](#-tech-stack)
- [Contributing](#-contributing)
- [License](#-license)

---

## ✨ Features

- 🎨 **Tailwind CSS** - Utility-first CSS framework
- 🌼 **DaisyUI** - Beautiful component library with multiple themes
- ⚡ **Alpine.js** - Lightweight JavaScript framework
- 🔄 **HTMX** - High-powered HTML attributes
- 🎭 **Jazzmin** - Modern Django admin interface
- 🔥 **Hot Reload** - Automatic browser refresh on code changes
- 🛡️ **Honeypot** - Built-in spam protection
- 📦 **No npm/Node.js** - Pure Python dependency management
- 🌗 **Dark Mode** - Built-in theme switching

---

## 📦 Prerequisites

- Python 3.10+
- MySQL (optional, SQLite is default)
- [uv](https://github.com/astral-sh/uv) package installer

### Installing uv
#### Windows (PowerShell)
```bash
powershell -c "irm https://astral.sh/uv/install.ps1 | iex"
```
#### macOS/Linux
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

---

## 🚀 Quick Start

```bash
mkdir myproject && cd myproject
```

```bash
uv init && uv venv
```
## Activate virtual environment
#### Windows PowerShell:
```bash
source .venv\Scripts\activate
```
#### macOS/Linux:
```bash
source .venv/bin/activate
```

## Install dependencies
```bash
uv add django pillow django-extensions django-cotton django-tailwind-cli honeypot mysqlclient django-htmx django-browser-reload django-jazzmin
```

## Create Django project
```bash
django-admin startproject config .
```

### Create core app
```bash
python manage.py startapp core
```

### Create required directories
```bash
mkdir templates, templates/core, static, static/css, media
```

---

## 📝 Installation Steps

### Step 1: Project & Virtual Environment

Create your project directory and set up the Python virtual environment:

### Create and navigate to project folder
```bash
mkdir myproject && cd myproject
```

### Initialize uv and create virtual environment
```bash
uv init && uv venv
```

### Activate the virtual environment
```bash
source .venv\Scripts\activate
```

### Step 2: Install Dependencies

*Install all required packages in one command:*

```bash
uv pip install django pillow django-extensions django-cotton django-tailwind-cli honeypot mysqlclient django-htmx django-browser-reload django-jazzmin
```

**Packages Installed:**
- `django` - Web framework
- `pillow` - Image processing
- `django-extensions` - Useful Django extensions
- `django-cotton` - Component-based templating
- `django-tailwind-cli` - Tailwind CSS integration
- `honeypot` - Anti-spam protection
- `mysqlclient` - MySQL database connector
- `django-htmx` - HTMX integration
- `django-browser-reload` - Live reload
- `django-jazzmin` - Modern admin interface

### Step 3: Create Django Project Structure

### Create Django project (. means current directory)
```bash
django-admin startproject config .
```
### Create the core app
```bash
python manage.py startapp core
```

### Create necessary directories
```bash
mkdir templates
mkdir templates\core
mkdir static
mkdir static\css
mkdir media
```

---

## ⚙️ Configuration

### Step 4: Update `config/settings.py`

Make sure `import os` is at the top of the file, then update the following sections:

#### Installed Apps

```python
INSTALLED_APPS = [
    'jazzmin',  # Must be before django.contrib.admin
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',

    # Third-party apps
    'django_extensions',
    'django_cotton',
    'django_tailwind_cli',
    'honeypot',
    'django_htmx',
    'django_browser_reload',

    # Your apps
    'core',
]
```

#### Daisy UI with Tailwind CLI Configuration
```bash
TAILWIND_CLI_USE_DAISY_UI = True
```
#### Middleware

```python
MIDDLEWARE = [
    'django.middleware.security.SecurityMiddleware',
    'django.contrib.sessions.middleware.SessionMiddleware',
    'django.middleware.common.CommonMiddleware',
    'django.middleware.csrf.CsrfViewMiddleware',
    'django.contrib.auth.middleware.AuthenticationMiddleware',
    'django.contrib.messages.middleware.MessageMiddleware',
    'django.middleware.clickjacking.XFrameOptionsMiddleware',
    
    'django_htmx.middleware.HtmxMiddleware',  # HTMX support
    'django_browser_reload.middleware.BrowserReloadMiddleware',  # Live reload
]
```

#### Templates

```python
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [os.path.join(BASE_DIR, 'templates')],
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                'django.template.context_processors.debug',
                'django.template.context_processors.request',
                'django.contrib.auth.context_processors.auth',
                'django.contrib.messages.context_processors.messages',
                'django.template.context_processors.media',
            ],
            'builtins': ['django_cotton.templatetags.cotton'],
        },
    },
]
```

#### Static & Media Files

```python
STATIC_URL = '/static/'
STATIC_ROOT = os.path.join(BASE_DIR, 'staticfiles')
STATICFILES_DIRS = [os.path.join(BASE_DIR, 'static')]

MEDIA_URL = '/media/'
MEDIA_ROOT = os.path.join(BASE_DIR, 'media')
```


#### Additional Settings

```python
# For browser reload
INTERNAL_IPS = ["127.0.0.1"]

# Anti-spam honeypot
HONEYPOT_FIELD_NAME = 'email_confirm'

# Jazzmin admin customization
JAZZMIN_SETTINGS = {
    "site_title": "My Admin",
    "site_header": "My Admin",
}
```

---

## 🗄️ Database Setup (Optional)

### MySQL Configuration

If you prefer MySQL over SQLite, follow these steps:

#### 1. Create MySQL Database

```sql
CREATE DATABASE myproject_db;
CREATE USER 'myproject_user'@'localhost' IDENTIFIED BY 'your_password';
GRANT ALL PRIVILEGES ON myproject_db.* TO 'myproject_user'@'localhost';
FLUSH PRIVILEGES;
```

#### 2. Update Database Settings

Replace the `DATABASES` section in `config/settings.py`:

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'myproject_db',
        'USER': 'myproject_user',
        'PASSWORD': 'your_password',  # Use your actual password
        'HOST': 'localhost',
        'PORT': '3306',
    }
}
```

---

## 🎨 Frontend Setup

### Step 6: Create Tailwind Source File

in `./django_tailwind_cli/source.css`:

```css
@import "tailwindcss";

/* DaisyUI plugin with theme configuration */
@plugin "daisyui" {
  themes: ["light", "dark", "cupcake", "synthwave", "retro", "cyberpunk"];
}

/* Custom component styles */
@layer components {
  .container {
    @apply mx-auto px-4;
  }
}
```

### Step 7: Configure URLs

#### Main URLs - `config/urls.py`

```python
from django.contrib import admin
from django.urls import path, include
from django.conf import settings
from django.conf.urls.static import static

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('core.urls')),
    path("__reload__/", include("django_browser_reload.urls")),
]

# Serve static and media files in development
if settings.DEBUG:
    urlpatterns += static(settings.STATIC_URL, document_root=settings.STATIC_ROOT)
    urlpatterns += static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)
```

#### Core App URLs - `core/urls.py`

Create this file in your `core` directory:

```python
from django.urls import path
from . import views

app_name = 'core'

urlpatterns = [
    path('', views.home, name='home'),
]
```

### Step 8: Create Views and Templates

#### View - `core/views.py`

```python
from django.shortcuts import render

def home(request):
    return render(request, 'core/home.html')
```

#### Base Template - `templates/base.html`

```html
{% load static %}
{% load tailwind_cli %}
<!DOCTYPE html>
<!-- Consider setting the lang attribute dynamically based on request language -->
<html lang="en" data-theme="light">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <!-- Search Engine Optimization (SEO) Tags -->
    <!-- Title Tag: Crucial for SEO. Keep it concise (50-60 chars) and relevant. -->
    <title>{% block page_title %}Default Page Title - My App{% endblock page_title %}</title>
    
    <!-- Meta Description: A brief summary of the page (150-160 chars). -->
    <meta name="description" content="{% block meta_description %}Default description for My App. Describe your page content here.{% endblock meta_description %}">
    
    <!-- Meta Keywords (Less important for Google, but can be used by others) -->
    <meta name="keywords" content="{% block meta_keywords %}default, keywords, my, app{% endblock meta_keywords %}">
    
    <!-- Canonical URL: Helps prevent duplicate content issues. -->
    <!-- This provides a default, but you should override `canonical_url` in child templates for accuracy. -->
    <link rel="canonical" href="{% block canonical_url %}{{ request.build_absolute_uri }}{% endblock canonical_url %}">
    
    <!-- Open Graph (OG) Tags for Social Media (Facebook, LinkedIn, etc.) -->
    <!-- By default, they inherit from page_title and meta_description, but can be overridden -->
    <meta property="og:title" content="{% block og_title %}{% block page_title_og %}{% endblock page_title_og %}{% endblock og_title %}">
    <meta property="og:description" content="{% block og_description %}{% block meta_description_og %}{% endblock meta_description_og %}{% endblock og_description %}">
    <meta property="og:type" content="website">
    <!-- Replace with your default site image -->
    <meta property="og:image" content="{% block og_image %}{% static 'images/default_og_image.png' %}{% endblock og_image %}">
    <meta property="og:url" content="{% block og_url %}{{ request.build_absolute_uri }}{% endblock og_url %}">
    <meta property="og:site_name" content="My App">
    
    <!-- Twitter Card Tags -->
    <meta name="twitter:card" content="summary_large_image">
    <!-- Replace with your Twitter handle if you have one -->
    <meta name="twitter:site" content="@YourTwitterHandle">
    <meta name="twitter:title" content="{% block twitter_title %}{% block page_title_twitter %}{% endblock page_title_twitter %}{% endblock twitter_title %}">
    <meta name="twitter:description" content="{% block twitter_description %}{% block meta_description_twitter %}{% endblock meta_description_twitter %}{% endblock twitter_description %}">
    <!-- Replace with your default site image -->
    <meta name="twitter:image" content="{% block twitter_image %}{% static 'images/default_twitter_image.png' %}{% endblock twitter_image %}">

    <!-- Favicon -->
    <link rel="icon" href="{% static 'favicon.ico' %}" type="image/x-icon">
    <link rel="apple-touch-icon" href="{% static 'apple-touch-icon.png' %}">
    
    <!-- Tailwind CSS -->
    {% tailwind_css %}
    
    <!-- Alpine.js -->
    <script src="https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js"></script>
    
    <!-- HTMX -->
    <script src="https://unpkg.com/htmx.org@2.0.3"></script>

    <!-- Allow extra head content -->
    {% block extra_head %}{% endblock extra_head %}
</head>
<body x-data="{ darkMode: false }" :data-theme="darkMode ? 'dark' : 'light'" class="min-h-screen bg-base-100 text-base-content antialiased flex flex-col">
    
    
    
    <!-- Main content area -->
    <main id="main-content" class="p-4 md:p-8 flex-grow">
        <!-- Replaced the original title block with page_title for consistency -->
        {% block content %}{% endblock %}
    </main>
    
    
    
    <!-- Extra body scripts -->
    {% block extra_scripts %}{% endblock extra_scripts %}
</body>
</html>

```

#### Home Template - `templates/core/home.html`

```html
{% extends 'base.html' %}
{% block title %}Home{% endblock %}

{% block content %}
<div class="hero min-h-screen bg-base-200">
    <div class="hero-content text-center">
        <div class="max-w-md">
            <h1 class="text-5xl font-bold text-primary">Welcome to Django!</h1>
            <p class="py-6">
                <span class="badge badge-primary">Django</span> 
                <span class="badge badge-secondary">Tailwind</span> 
                <span class="badge badge-accent">DaisyUI</span>
            </p>
            <button class="btn btn-primary">Get Started</button>
        </div>
    </div>
</div>
{% endblock %}
```

---

### style.css
```css

:root {
  /* -- Light Mode Colors -- */
  --primary: #E3651D;
  /* Orange */
  --secondary: #750E21;
  /* Dark Red */
  --bg: #ffffff;
  /* Main background */
  --secondary-bg: #f3f4f6;
  /* Gray 100 */
  --card: #f8f8f8;
  /* Card background */
  --title: #e76209;
  /* Text color (Dark Gray) */
  --sub-title: #191919;
  /* Text color */
  --desc: #191919;
  /* Text color */
  --accent: #BED754;
  /* Light Green */
  --neutral: #374151;
  /* Gray 700 */
  --border-color: #e5e7eb;
  /* Borders, dividers (Gray 200) */
  --info: #3b82f6;
  --success: #22c55e;
  --warning: #f59e0b;
  --error: #ef4444;
}

/* Dark mode using data-theme attribute */

[data-theme="dark"] {
  /* -- Dark Mode Colors -- */
  --primary: #E3651D;
  /* Orange */
  --secondary: #750E21;
  /* Dark Red */
  --bg: #181818;
  /* Main background (Dark Gray) */
  --secondary-bg: #750E21;
  /* Secondary background (Dark Red) */
  --card: #131313;
  /* Card background */
  --title: #ff7332;
  /* Text color (Light Green) */
  --sub-title: #BED754;
  /* Text color */
  --desc: #BED754;
  /* Text color */
  --accent: #BED754;
  /* Light Green */
  --neutral: #750E21;
  /* Dark Red */
  --border-color: #E3651D;
  /* Borders (Orange) */
  --info: #58c7f3;
  --success: #00ff00;
  /* Brighter green */
  --warning: #f3cc30;
  --error: #ff0000;
  /* Brighter red */
}

/* Support prefers-color-scheme for automatic detection */

@media (prefers-color-scheme: dark) {
  :root:not([data-theme="light"]) {
    /* -- Dark Mode Colors -- */
    --primary: #E3651D;
    /* Orange */
    --secondary: #750E21;
    /* Dark Red */
    --bg: #181818;
    /* Main background (Dark Gray) */
    --secondary-bg: #750E21;
    /* Secondary background (Dark Red) */
    --card: #131313;
    /* Card background */
    --title: #ff7332;
    /* Text color (Light Green) */
    --sub-title: #ececec;
    /* Text color */
    --desc: #e9e9e9;
    /* Text color */
    --accent: #BED754;
    /* Light Green */
    --neutral: #750E21;
    /* Dark Red */
    --border-color: #E3651D;
    /* Borders (Orange) */
    --info: #58c7f3;
    --success: #00ff00;
    /* Brighter green */
    --warning: #f3cc30;
    --error: #ff0000;
    /* Brighter red */
  }
}

body{
  background-color: var(--bg);
  color: var(--title);
  transition-property: color, background-color, border-color, text-decoration-color, fill, stroke;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 200ms;
  font-family: "Inter", sans-serif;
}

.container{
  width: 100%;
}

@media (min-width: 640px){
  .container{
    max-width: 640px;
  }
}

@media (min-width: 768px){
  .container{
    max-width: 768px;
  }
}

@media (min-width: 1024px){
  .container{
    max-width: 1024px;
  }
}

@media (min-width: 1280px){
  .container{
    max-width: 1280px;
  }
}

@media (min-width: 1536px){
  .container{
    max-width: 1536px;
  }
}

```
---

## 🏃 Running the Project

### Step 9: Initialize and Run

Execute these commands in order:

#### Download Tailwind CLI and build CSS
```bash
uv run manage.py tailwind setup
```

#### build Tailwind CLI and build CSS
```bash
uv run manage.py tailwind build
```

#### Run database migrations
```bash
uv run manage.py migrate
```

#### Create superuser for admin access
```bash
uv run manage.py createsuperuser
```


#### Start development server with Tailwind watch mode
```bash
uv run manage.py tailwind runserver
```

### Access Your Application

- **Frontend**: [http://127.0.0.1:8000/](http://127.0.0.1:8000/)
- **Admin Panel**: [http://127.0.0.1:8000/admin/](http://127.0.0.1:8000/admin/)

---

## 📁 Project Structure

```
myproject/
├── config/                 # Project configuration
│   ├── __init__.py
│   ├── asgi.py
│   ├── settings.py        # Main settings
│   ├── urls.py            # URL routing
│   └── wsgi.py
├── core/                   # Main app
│   ├── migrations/
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── models.py
│   ├── tests.py
│   ├── urls.py            # App URLs
│   └── views.py           # Views
├── static/                 # Static files
│   ├── css/
│   │   ├── source.css     # Tailwind source
│   │   └── output.css     # Compiled CSS
│   ├── img/
│   └── js/
├── templates/              # HTML templates
│   ├── base.html          # Base template
│   └── core/
│       └── home.html      # Homepage
├── media/                  # User uploads
├── .venv/                  # Virtual environment
├── manage.py              # Django management
└── requirements.txt       # Dependencies
```

---

## 🛠️ Tech Stack

| Technology | Purpose | Documentation |
|------------|---------|---------------|
| **Django** | Web Framework | [docs.djangoproject.com](https://docs.djangoproject.com/) |
| **Tailwind CSS** | Utility CSS | [tailwindcss.com](https://tailwindcss.com/) |
| **DaisyUI** | Component Library | [daisyui.com](https://daisyui.com/) |
| **Alpine.js** | JavaScript Framework | [alpinejs.dev](https://alpinejs.dev/) |
| **HTMX** | HTML Attributes | [htmx.org](https://htmx.org/) |
| **Jazzmin** | Admin Theme | [django-jazzmin.readthedocs.io](https://django-jazzmin.readthedocs.io/) |
| **uv** | Package Manager | [github.com/astral-sh/uv](https://github.com/astral-sh/uv) |

---

## 🎯 Available DaisyUI Themes

- `light` - Clean light theme
- `dark` - Dark mode theme
- `cupcake` - Soft pastel colors
- `synthwave` - Retro 80s vibes
- `retro` - Vintage aesthetic
- `cyberpunk` - Neon futuristic

Change themes in `static/css/source.css` or toggle dynamically with Alpine.js.

---

## 🔧 Development Commands


### Run development server with Tailwind watch
```bash
uv run manage.py tailwind runserver
```

#### Build Tailwind CSS for production
```bash
uv run manage.py tailwind build
```

#### Create new Django app
```bash
python manage.py startapp app_name
```

#### Make migrations
```bash
python manage.py makemigrations
```

#### Apply migrations
```bash
python manage.py migrate
```

#### Create superuser
```bash
python manage.py createsuperuser
```

#### Collect static files
```bash
python manage.py collectstatic
```

---

## 📚 Additional Resources

- [Django Documentation](https://docs.djangoproject.com/)
- [Tailwind CSS Docs](https://tailwindcss.com/docs)
- [DaisyUI Components](https://daisyui.com/components/)
- [Alpine.js Documentation](https://alpinejs.dev/start-here)
- [HTMX Documentation](https://htmx.org/docs/)
- [django-tailwind-cli GitHub](https://github.com/oliverandrich/django-tailwind-cli)

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 💖 Acknowledgments

- Django community for the amazing framework
- Tailwind CSS team for the utility-first approach
- DaisyUI for beautiful components
- All open-source contributors

---

<div align="center">
  
**Made with ❤️ and Django**

⭐ Star this repo if you find it helpful!

</div>
