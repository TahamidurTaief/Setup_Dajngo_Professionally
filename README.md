# 🌸 Django + Tailwind CLI + DaisyUI (No Node/NPM)

This guide sets up **Django + TailwindCSS + DaisyUI** using `django-tailwind-cli`, **without Node.js or npm**.  
It installs everything with **`uv`**, configures MySQL, SEO, and security, and includes ready templates and styling.

---

## ⚙️ Step 1: Project Setup

### 1️⃣ Create project folder and initialize environment
```bash
mkdir myproject
cd myproject
uv init
```

### 2️⃣ Create virtual environment
```bash
uv venv
.venv\Scripts\activate
```

---

## 📦 Step 2: Install All Packages at Once

### Install all required packages with uv
```bash
uv pip install django pillow django-extensions django-cotton django-tailwind-cli honeypot mysqlclient
```

**Packages installed:**
- `django` - Web framework
- `pillow` - Image processing
- `django-extensions` - Useful Django extensions
- `django-cotton` - Component-based templates
- `django-tailwind-cli` - TailwindCSS without Node.js
- `honeypot` - Security against spam bots
- `mysqlclient` - MySQL database connector

---

## 🚀 Step 3: Create Django Project

### 1️⃣ Create Django project and app
```bash
django-admin startproject config .
python manage.py startapp core
```

### 2️⃣ Create required directories
```bash
mkdir templates
mkdir static
mkdir media
mkdir static\css
mkdir static\js
mkdir static\images
```

---

## 🗄️ Step 4: MySQL Database Setup

### 1️⃣ Install MySQL Server
Download and install MySQL from [https://dev.mysql.com/downloads/installer/](https://dev.mysql.com/downloads/installer/)

### 2️⃣ Create database
Open MySQL command line:
```sql
CREATE DATABASE myproject_db CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
CREATE USER 'myproject_user'@'localhost' IDENTIFIED BY 'your_password';
GRANT ALL PRIVILEGES ON myproject_db.* TO 'myproject_user'@'localhost';
FLUSH PRIVILEGES;
EXIT;
```

### 3️⃣ Configure database in `config/settings.py`
```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'myproject_db',
        'USER': 'myproject_user',
        'PASSWORD': 'your_password',
        'HOST': 'localhost',
        'PORT': '3306',
        'OPTIONS': {
            'charset': 'utf8mb4',
            'init_command': "SET sql_mode='STRICT_TRANS_TABLES'",
        }
    }
}
```

---

## ⚙️ Step 5: Django Settings Configuration

### Update `config/settings.py`

#### 1️⃣ Add apps to INSTALLED_APPS
```python
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    
    # Third party apps
    'django_extensions',
    'django_cotton',
    'django_tailwind_cli',
    'honeypot',
    
    # Local apps
    'core',
]
```

#### 2️⃣ Add middleware for security
```python
MIDDLEWARE = [
    'django.middleware.security.SecurityMiddleware',
    'django.contrib.sessions.middleware.SessionMiddleware',
    'django.middleware.common.CommonMiddleware',
    'django.middleware.csrf.CsrfViewMiddleware',
    'django.contrib.auth.middleware.AuthenticationMiddleware',
    'django.contrib.messages.middleware.MessageMiddleware',
    'django.middleware.clickjacking.XFrameOptionsMiddleware',
]
```

#### 3️⃣ Configure templates
```python
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [BASE_DIR / 'templates'],
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                'django.template.context_processors.debug',
                'django.template.context_processors.request',
                'django.contrib.auth.context_processors.auth',
                'django.contrib.messages.context_processors.messages',
                'django.template.context_processors.media',
            ],
            'builtins': [
                'django_cotton.templatetags.cotton',
            ],
        },
    },
]
```

#### 4️⃣ Configure static and media files
```python
# Static files (CSS, JavaScript, Images)
STATIC_URL = '/static/'
STATIC_ROOT = BASE_DIR / 'staticfiles'
STATICFILES_DIRS = [
    BASE_DIR / 'static',
]

# Media files (User uploads)
MEDIA_URL = '/media/'
MEDIA_ROOT = BASE_DIR / 'media'
```

#### 5️⃣ Add security settings
```python
# Security Settings
SECURE_BROWSER_XSS_FILTER = True
SECURE_CONTENT_TYPE_NOSNIFF = True
X_FRAME_OPTIONS = 'DENY'
CSRF_COOKIE_SECURE = False  # Set True in production with HTTPS
SESSION_COOKIE_SECURE = False  # Set True in production with HTTPS
SECURE_SSL_REDIRECT = False  # Set True in production with HTTPS

# Honeypot settings
HONEYPOT_FIELD_NAME = 'email_confirm'
```

#### 6️⃣ Configure allowed hosts
```python
ALLOWED_HOSTS = ['localhost', '127.0.0.1']
```

---

## 🎨 Step 6: TailwindCSS + DaisyUI Setup

### 1️⃣ Add TailwindCSS CLI settings to `config/settings.py`
```python
# TailwindCSS CLI Configuration
TAILWIND_CLI_PATH = "~/.local/bin/"  # Will auto-download
TAILWIND_CLI_VERSION = "latest"
TAILWIND_CLI_AUTOMATIC_DOWNLOAD = True

# TailwindCSS source and destination
TAILWIND_CLI_SRC_CSS = "static/css/source.css"
TAILWIND_CLI_DIST_CSS = "static/css/output.css"

# Enable DaisyUI and extra plugins
TAILWIND_CLI_CONFIG_FILE = None  # We use source.css instead
```

### 2️⃣ Create `static/css/source.css`
```bash
New-Item -Path "static/css/source.css" -ItemType File -Force
```

Add this content to `static/css/source.css`:
```css
@tailwind base;
@tailwind components;
@tailwind utilities;

/* Custom CSS Variables for Dark/Light Mode */
@layer base {
  :root {
    /* Light Mode Colors */
    --color-bg-primary: 255 255 255;
    --color-bg-secondary: 249 250 251;
    --color-bg-tertiary: 243 244 246;
    
    --color-text-primary: 17 24 39;
    --color-text-secondary: 75 85 99;
    --color-text-tertiary: 107 114 128;
    
    --color-title: 31 41 55;
    --color-subtitle: 55 65 81;
    --color-description: 107 114 128;
    
    --color-primary: 59 130 246;
    --color-primary-hover: 37 99 235;
    --color-secondary: 139 92 246;
    --color-secondary-hover: 124 58 237;
    
    --color-accent: 236 72 153;
    --color-success: 34 197 94;
    --color-warning: 251 146 60;
    --color-error: 239 68 68;
    
    --color-logo: 59 130 246;
    --color-border: 229 231 235;
  }

  .dark {
    /* Dark Mode Colors */
    --color-bg-primary: 17 24 39;
    --color-bg-secondary: 31 41 55;
    --color-bg-tertiary: 55 65 81;
    
    --color-text-primary: 243 244 246;
    --color-text-secondary: 209 213 219;
    --color-text-tertiary: 156 163 175;
    
    --color-title: 249 250 251;
    --color-subtitle: 229 231 235;
    --color-description: 156 163 175;
    
    --color-primary: 96 165 250;
    --color-primary-hover: 59 130 246;
    --color-secondary: 167 139 250;
    --color-secondary-hover: 139 92 246;
    
    --color-accent: 244 114 182;
    --color-success: 74 222 128;
    --color-warning: 251 191 36;
    --color-error: 248 113 113;
    
    --color-logo: 96 165 250;
    --color-border: 75 85 99;
  }
}

/* Custom Utility Classes */
@layer components {
  /* Background Colors */
  .bg-primary {
    background-color: rgb(var(--color-bg-primary));
  }
  
  .bg-secondary {
    background-color: rgb(var(--color-bg-secondary));
  }
  
  .bg-tertiary {
    background-color: rgb(var(--color-bg-tertiary));
  }

  /* Text Colors */
  .text-primary {
    color: rgb(var(--color-text-primary));
  }
  
  .text-secondary {
    color: rgb(var(--color-text-secondary));
  }
  
  .text-tertiary {
    color: rgb(var(--color-text-tertiary));
  }
  
  .text-title {
    color: rgb(var(--color-title));
  }
  
  .text-subtitle {
    color: rgb(var(--color-subtitle));
  }
  
  .text-description {
    color: rgb(var(--color-description));
  }

  /* Brand Colors */
  .btn-primary {
    background-color: rgb(var(--color-primary));
    color: white;
  }
  
  .btn-primary:hover {
    background-color: rgb(var(--color-primary-hover));
  }
  
  .btn-secondary {
    background-color: rgb(var(--color-secondary));
    color: white;
  }
  
  .btn-secondary:hover {
    background-color: rgb(var(--color-secondary-hover));
  }

  /* Responsive Container */
  .container {
    @apply mx-auto px-4 sm:px-6 lg:px-8;
    max-width: 1280px;
  }
  
  .container-sm {
    @apply mx-auto px-4 sm:px-6 lg:px-8;
    max-width: 640px;
  }
  
  .container-md {
    @apply mx-auto px-4 sm:px-6 lg:px-8;
    max-width: 768px;
  }
  
  .container-lg {
    @apply mx-auto px-4 sm:px-6 lg:px-8;
    max-width: 1024px;
  }
  
  .container-xl {
    @apply mx-auto px-4 sm:px-6 lg:px-8;
    max-width: 1280px;
  }
  
  .container-2xl {
    @apply mx-auto px-4 sm:px-6 lg:px-8;
    max-width: 1536px;
  }

  /* Card Component */
  .card {
    @apply bg-secondary rounded-lg shadow-md p-6;
  }
  
  .card-title {
    @apply text-title text-2xl font-bold mb-4;
  }
  
  .card-body {
    @apply text-primary;
  }

  /* Border Utilities */
  .border-custom {
    border-color: rgb(var(--color-border));
  }
}

/* Custom Animations */
@layer utilities {
  .animate-fade-in {
    animation: fadeIn 0.5s ease-in;
  }
  
  @keyframes fadeIn {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }
  
  .transition-theme {
    transition: background-color 0.3s ease, color 0.3s ease;
  }
}
```

### 3️⃣ Build TailwindCSS
```bash
python manage.py tailwind build
```

For development with auto-rebuild:
```bash
python manage.py tailwind watch
```

---

## 📄 Step 7: Create Base Template with SEO

### Create `templates/base.html`
```bash
New-Item -Path "templates/base.html" -ItemType File -Force
```

Add this content to `templates/base.html`:
```html
{% load static %}
<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <!-- Essential Meta Tags -->
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    
    <!-- SEO Meta Tags -->
    <title>{% block title %}My Django Project{% endblock %} | Your Brand Name</title>
    <meta name="description" content="{% block description %}Your comprehensive Django application with modern design and functionality.{% endblock %}">
    <meta name="keywords" content="{% block keywords %}django, web development, tailwindcss, daisyui{% endblock %}">
    <meta name="author" content="Your Name or Company">
    <meta name="robots" content="index, follow">
    <meta name="language" content="English">
    <meta name="revisit-after" content="7 days">
    
    <!-- Canonical URL -->
    <link rel="canonical" href="{% block canonical %}{{ request.build_absolute_uri }}{% endblock %}">
    
    <!-- Open Graph Meta Tags (Facebook, LinkedIn) -->
    <meta property="og:title" content="{% block og_title %}{% block title %}My Django Project{% endblock %}{% endblock %}">
    <meta property="og:description" content="{% block og_description %}{% block description %}Your comprehensive Django application with modern design and functionality.{% endblock %}{% endblock %}">
    <meta property="og:type" content="{% block og_type %}website{% endblock %}">
    <meta property="og:url" content="{% block og_url %}{{ request.build_absolute_uri }}{% endblock %}">
    <meta property="og:image" content="{% block og_image %}{% static 'images/og-image.jpg' %}{% endblock %}">
    <meta property="og:image:alt" content="{% block og_image_alt %}Your Brand Logo{% endblock %}">
    <meta property="og:site_name" content="Your Brand Name">
    <meta property="og:locale" content="en_US">
    
    <!-- Twitter Card Meta Tags -->
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:site" content="@yourtwitterhandle">
    <meta name="twitter:creator" content="@yourtwitterhandle">
    <meta name="twitter:title" content="{% block twitter_title %}{% block title %}My Django Project{% endblock %}{% endblock %}">
    <meta name="twitter:description" content="{% block twitter_description %}{% block description %}Your comprehensive Django application with modern design and functionality.{% endblock %}{% endblock %}">
    <meta name="twitter:image" content="{% block twitter_image %}{% static 'images/twitter-card.jpg' %}{% endblock %}">
    
    <!-- Favicon -->
    <link rel="icon" type="image/png" sizes="32x32" href="{% static 'images/favicon-32x32.png' %}">
    <link rel="icon" type="image/png" sizes="16x16" href="{% static 'images/favicon-16x16.png' %}">
    <link rel="apple-touch-icon" sizes="180x180" href="{% static 'images/apple-touch-icon.png' %}">
    <link rel="manifest" href="{% static 'site.webmanifest' %}">
    
    <!-- Theme Color -->
    <meta name="theme-color" content="#3b82f6">
    <meta name="msapplication-TileColor" content="#3b82f6">
    
    <!-- DNS Prefetch for Performance -->
    <link rel="dns-prefetch" href="//fonts.googleapis.com">
    
    <!-- TailwindCSS Output -->
    <link rel="stylesheet" href="{% static 'css/output.css' %}">
    
    <!-- Additional Stylesheets -->
    {% block extra_css %}{% endblock %}
    
    <!-- Structured Data (JSON-LD) -->
    <script type="application/ld+json">
    {
        "@context": "https://schema.org",
        "@type": "{% block schema_type %}WebSite{% endblock %}",
        "name": "Your Brand Name",
        "url": "{{ request.scheme }}://{{ request.get_host }}",
        "description": "{% block schema_description %}Your comprehensive Django application with modern design and functionality.{% endblock %}",
        "publisher": {
            "@type": "Organization",
            "name": "Your Brand Name",
            "logo": {
                "@type": "ImageObject",
                "url": "{% static 'images/logo.png' %}"
            }
        }
    }
    </script>
    
    {% block extra_head %}{% endblock %}
</head>

<body class="bg-primary text-primary transition-theme antialiased">
    <!-- Skip to main content for accessibility -->
    <a href="#main-content" class="sr-only focus:not-sr-only focus:absolute focus:top-4 focus:left-4 bg-primary text-white px-4 py-2 rounded-md z-50">
        Skip to main content
    </a>

    <!-- Header/Navigation -->
    <header class="bg-secondary border-b border-custom sticky top-0 z-40 transition-theme">
        <nav class="container py-4">
            <div class="flex items-center justify-between">
                <div class="flex items-center space-x-2">
                    <a href="/" class="text-2xl font-bold" style="color: rgb(var(--color-logo))">
                        YourLogo
                    </a>
                </div>
                
                <div class="hidden md:flex items-center space-x-6">
                    <a href="/" class="text-primary hover:text-subtitle transition">Home</a>
                    <a href="#" class="text-primary hover:text-subtitle transition">About</a>
                    <a href="#" class="text-primary hover:text-subtitle transition">Services</a>
                    <a href="#" class="text-primary hover:text-subtitle transition">Contact</a>
                </div>
                
                <!-- Dark Mode Toggle -->
                <button id="theme-toggle" type="button" class="p-2 rounded-lg hover:bg-tertiary transition" aria-label="Toggle dark mode">
                    <svg id="theme-toggle-dark-icon" class="hidden w-5 h-5" fill="currentColor" viewBox="0 0 20 20">
                        <path d="M17.293 13.293A8 8 0 016.707 2.707a8.001 8.001 0 1010.586 10.586z"></path>
                    </svg>
                    <svg id="theme-toggle-light-icon" class="hidden w-5 h-5" fill="currentColor" viewBox="0 0 20 20">
                        <path d="M10 2a1 1 0 011 1v1a1 1 0 11-2 0V3a1 1 0 011-1zm4 8a4 4 0 11-8 0 4 4 0 018 0zm-.464 4.95l.707.707a1 1 0 001.414-1.414l-.707-.707a1 1 0 00-1.414 1.414zm2.12-10.607a1 1 0 010 1.414l-.706.707a1 1 0 11-1.414-1.414l.707-.707a1 1 0 011.414 0zM17 11a1 1 0 100-2h-1a1 1 0 100 2h1zm-7 4a1 1 0 011 1v1a1 1 0 11-2 0v-1a1 1 0 011-1zM5.05 6.464A1 1 0 106.465 5.05l-.708-.707a1 1 0 00-1.414 1.414l.707.707zm1.414 8.486l-.707.707a1 1 0 01-1.414-1.414l.707-.707a1 1 0 011.414 1.414zM4 11a1 1 0 100-2H3a1 1 0 000 2h1z" fill-rule="evenodd" clip-rule="evenodd"></path>
                    </svg>
                </button>
                
                <!-- Mobile Menu Button -->
                <button id="mobile-menu-toggle" class="md:hidden p-2 rounded-lg hover:bg-tertiary transition" aria-label="Toggle menu">
                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>
                    </svg>
                </button>
            </div>
            
            <!-- Mobile Menu -->
            <div id="mobile-menu" class="hidden md:hidden mt-4 pb-4 space-y-2">
                <a href="/" class="block text-primary hover:text-subtitle transition py-2">Home</a>
                <a href="#" class="block text-primary hover:text-subtitle transition py-2">About</a>
                <a href="#" class="block text-primary hover:text-subtitle transition py-2">Services</a>
                <a href="#" class="block text-primary hover:text-subtitle transition py-2">Contact</a>
            </div>
        </nav>
    </header>

    <!-- Main Content -->
    <main id="main-content" class="min-h-screen">
        <!-- Messages -->
        {% if messages %}
        <div class="container mt-6">
            {% for message in messages %}
            <div class="{% if message.tags == 'error' %}bg-red-100 border-red-400 text-red-700{% elif message.tags == 'success' %}bg-green-100 border-green-400 text-green-700{% elif message.tags == 'warning' %}bg-yellow-100 border-yellow-400 text-yellow-700{% else %}bg-blue-100 border-blue-400 text-blue-700{% endif %} border px-4 py-3 rounded relative mb-4" role="alert">
                <span class="block sm:inline">{{ message }}</span>
            </div>
            {% endfor %}
        </div>
        {% endif %}
        
        <!-- Page Content -->
        {% block content %}{% endblock %}
    </main>

    <!-- Footer -->
    <footer class="bg-secondary border-t border-custom mt-16 transition-theme">
        <div class="container py-8">
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div>
                    <h3 class="text-title font-bold text-lg mb-4">About Us</h3>
                    <p class="text-secondary">Your comprehensive Django application with modern design and functionality.</p>
                </div>
                <div>
                    <h3 class="text-title font-bold text-lg mb-4">Quick Links</h3>
                    <ul class="space-y-2">
                        <li><a href="#" class="text-secondary hover:text-subtitle transition">Privacy Policy</a></li>
                        <li><a href="#" class="text-secondary hover:text-subtitle transition">Terms of Service</a></li>
                        <li><a href="#" class="text-secondary hover:text-subtitle transition">Contact</a></li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-title font-bold text-lg mb-4">Follow Us</h3>
                    <div class="flex space-x-4">
                        <a href="#" class="text-secondary hover:text-subtitle transition" aria-label="Facebook">
                            <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24"><path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/></svg>
                        </a>
                        <a href="#" class="text-secondary hover:text-subtitle transition" aria-label="Twitter">
                            <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24"><path d="M23.953 4.57a10 10 0 01-2.825.775 4.958 4.958 0 002.163-2.723c-.951.555-2.005.959-3.127 1.184a4.92 4.92 0 00-8.384 4.482C7.69 8.095 4.067 6.13 1.64 3.162a4.822 4.822 0 00-.666 2.475c0 1.71.87 3.213 2.188 4.096a4.904 4.904 0 01-2.228-.616v.06a4.923 4.923 0 003.946 4.827 4.996 4.996 0 01-2.212.085 4.936 4.936 0 004.604 3.417 9.867 9.867 0 01-6.102 2.105c-.39 0-.779-.023-1.17-.067a13.995 13.995 0 007.557 2.209c9.053 0 13.998-7.496 13.998-13.985 0-.21 0-.42-.015-.63A9.935 9.935 0 0024 4.59z"/></svg>
                        </a>
                    </div>
                </div>
            </div>
            <div class="border-t border-custom mt-8 pt-8 text-center text-secondary">
                <p>&copy; 2025 Your Brand Name. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <!-- JavaScript -->
    <script>
        // Dark Mode Toggle
        const themeToggleBtn = document.getElementById('theme-toggle');
        const themeToggleDarkIcon = document.getElementById('theme-toggle-dark-icon');
        const themeToggleLightIcon = document.getElementById('theme-toggle-light-icon');

        // Check for saved theme preference or default to light mode
        if (localStorage.getItem('color-theme') === 'dark' || (!('color-theme' in localStorage) && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
            document.documentElement.classList.add('dark');
            themeToggleLightIcon.classList.remove('hidden');
        } else {
            themeToggleDarkIcon.classList.remove('hidden');
        }

        themeToggleBtn.addEventListener('click', function() {
            // Toggle icons
            themeToggleDarkIcon.classList.toggle('hidden');
            themeToggleLightIcon.classList.toggle('hidden');

            // Toggle dark mode
            if (document.documentElement.classList.contains('dark')) {
                document.documentElement.classList.remove('dark');
                localStorage.setItem('color-theme', 'light');
            } else {
                document.documentElement.classList.add('dark');
                localStorage.setItem('color-theme', 'dark');
            }
        });

        // Mobile Menu Toggle
        const mobileMenuToggle = document.getElementById('mobile-menu-toggle');
        const mobileMenu = document.getElementById('mobile-menu');

        mobileMenuToggle.addEventListener('click', function() {
            mobileMenu.classList.toggle('hidden');
        });
    </script>
    
    {% block extra_js %}{% endblock %}
</body>
</html>
```

---

## 🔧 Step 8: Configure URLs for Static and Media Files

### Update `config/urls.py`
```python
from django.contrib import admin
from django.urls import path, include
from django.conf import settings
from django.conf.urls.static import static

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('core.urls')),
]

# Serve static and media files in development
if settings.DEBUG:
    urlpatterns += static(settings.STATIC_URL, document_root=settings.STATIC_ROOT)
    urlpatterns += static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)
```

### Create `core/urls.py`
```python
from django.urls import path
from . import views

app_name = 'core'

urlpatterns = [
    path('', views.home, name='home'),
]
```

### Create `core/views.py`
```python
from django.shortcuts import render

def home(request):
    return render(request, 'core/home.html')
```

### Create `templates/core/home.html`
```html
{% extends 'base.html' %}

{% block title %}Home{% endblock %}

{% block content %}
<div class="container py-16">
    <div class="text-center">
        <h1 class="text-title text-5xl font-bold mb-4">Welcome to Django + TailwindCSS</h1>
        <p class="text-description text-xl mb-8">Built with django-tailwind-cli and DaisyUI - No Node.js Required!</p>
        
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8 mt-12">
            <div class="card">
                <h2 class="card-title">Fast Setup</h2>
                <p class="card-body">Get started quickly with no Node.js or npm dependencies.</p>
            </div>
            
            <div class="card">
                <h2 class="card-title">Modern Design</h2>
                <p class="card-body">Beautiful UI with TailwindCSS and DaisyUI components.</p>
            </div>
            
            <div class="card">
                <h2 class="card-title">SEO Ready</h2>
                <p class="card-body">Optimized templates with comprehensive SEO meta tags.</p>
            </div>
        </div>
    </div>
</div>
{% endblock %}
```

---

## 🗃️ Step 9: Collect Static Files

### Collect all static files for production
```bash
python manage.py collectstatic --noinput
```

This command will:
- Copy all static files from your apps and `STATICFILES_DIRS` to `STATIC_ROOT`
- Make files ready for production deployment
- Include your compiled CSS from TailwindCSS

**Note:** Run this command every time you update static files before deploying to production.

---

## 🚀 Step 10: Run Migrations and Create Superuser

### Run database migrations
```bash
python manage.py makemigrations
python manage.py migrate
```

### Create admin superuser
```bash
python manage.py createsuperuser
```

Follow the prompts to set username, email, and password.

---

## ▶️ Step 11: Run Development Server

### Start the Django development server
```bash
python manage.py runserver
```

Visit: **http://127.0.0.1:8000/**

Admin panel: **http://127.0.0.1:8000/admin/**

---

## 🎨 Step 12: Using TailwindCSS in Development

### Watch mode for automatic CSS compilation
Open a new terminal and run:
```bash
python manage.py tailwind watch
```

This will automatically rebuild your CSS when you make changes to your templates or `source.css` file.

---

## 🔐 Step 13: Additional Security Configuration

### Update `config/settings.py` for production

When deploying to production, update these settings:

```python
# Production Security Settings
DEBUG = False
ALLOWED_HOSTS = ['yourdomain.com', 'www.yourdomain.com']

# HTTPS Settings
SECURE_SSL_REDIRECT = True
SESSION_COOKIE_SECURE = True
CSRF_COOKIE_SECURE = True
SECURE_BROWSER_XSS_FILTER = True
SECURE_CONTENT_TYPE_NOSNIFF = True
X_FRAME_OPTIONS = 'DENY'
SECURE_HSTS_SECONDS = 31536000
SECURE_HSTS_INCLUDE_SUBDOMAINS = True
SECURE_HSTS_PRELOAD = True

# Secret Key - Use environment variable
import os
SECRET_KEY = os.environ.get('DJANGO_SECRET_KEY', 'your-secret-key-here')
```

---

## 📚 Step 14: Django Extensions Useful Commands

### Shell Plus (Enhanced Django shell)
```bash
python manage.py shell_plus
```

### Show URLs
```bash
python manage.py show_urls
```

### Generate Secret Key
```bash
python manage.py generate_secret_key
```

### Clean PyC files
```bash
python manage.py clean_pyc
```

---

## 🍯 Step 15: Honeypot Anti-Spam Setup

### Add honeypot to forms

In your forms, add the honeypot field:

```python
from django import forms
from honeypot.decorators import check_honeypot

class ContactForm(forms.Form):
    name = forms.CharField(max_length=100)
    email = forms.EmailField()
    message = forms.CharField(widget=forms.Textarea)
```

In your view:
```python
from honeypot.decorators import check_honeypot

@check_honeypot
def contact_view(request):
    if request.method == 'POST':
        form = ContactForm(request.POST)
        if form.is_valid():
            # Process form
            pass
    else:
        form = ContactForm()
    return render(request, 'contact.html', {'form': form})
```

In your template:
```html
{% load honeypot %}

<form method="post">
    {% csrf_token %}
    {% render_honeypot_field %}
    {{ form.as_p }}
    <button type="submit">Submit</button>
</form>
```

---

## 🧩 Step 16: Django Cotton Component Usage

### Create a component in `templates/cotton/`

Example: `templates/cotton/button.html`
```html
<c-vars primary_color="blue" />

<button class="px-4 py-2 bg-{{ primary_color }}-500 text-white rounded hover:bg-{{ primary_color }}-600 transition">
    <c-slot />
</button>
```

### Use in templates
```html
{% load cotton %}

<c-button primary_color="green">
    Click Me
</c-button>
```

---

## 📦 Step 17: Project Structure

Your final project structure should look like this:

```
myproject/
├── .venv/
├── config/
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   ├── asgi.py
│   └── wsgi.py
├── core/
│   ├── migrations/
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── models.py
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

### MySQL Connection Issues
- Make sure MySQL server is running
- Verify database credentials in `settings.py`
- Check if `mysqlclient` is properly installed

### TailwindCSS Not Compiling
- Ensure `source.css` exists at `static/css/source.css`
- Run `python manage.py tailwind build` manually
- Check for syntax errors in your CSS

### Static Files Not Loading
- Run `python manage.py collectstatic`
- Check `STATIC_URL` and `STATIC_ROOT` in settings
- Ensure `DEBUG = True` for development

### Import Errors
- Activate virtual environment: `.venv\Scripts\activate`
- Reinstall packages: `uv pip install -r requirements.txt`

---

## 📝 Additional Resources

- **Django Documentation:** https://docs.djangoproject.com/
- **TailwindCSS Documentation:** https://tailwindcss.com/docs
- **DaisyUI Components:** https://daisyui.com/components/
- **Django TailwindCSS CLI:** https://github.com/oliverandrich/django-tailwind-cli

---

## 🎉 You're All Set!

Your Django project with TailwindCSS and DaisyUI is now ready for development. Start building amazing features!

**Happy Coding! 🚀**
