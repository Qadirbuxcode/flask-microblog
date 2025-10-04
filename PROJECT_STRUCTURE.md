# Flask Microblog Project Structure

## 📁 Project Overview
A modern Flask web application with user authentication, posts, following system, and profile management.

## 🗂️ Directory Structure

`
FIRST PROJECT SIMPLE WEB/
├── 📁 app/                          # Main application package
│   ├── 📄 __init__.py              # Flask app factory & configuration
│   ├── 📄 config.py                # Application configuration
│   ├── 📄 models.py                # Database models (User, Post)
│   ├── 📄 routes.py                # Application routes & views
│   ├── 📄 forms.py                 # WTForms for form handling
│   ├── 📄 email.py                 # Email functionality
│   ├── 📄 errors.py                # Error handlers
│   ├── 📄 tests.py                 # Unit tests
│   ├── 📄 app.db                   # SQLite database
│   ├── 📁 templates/               # Jinja2 templates
│   │   ├── 📄 base.html            # Base template with Bootstrap
│   │   ├── 📄 bootstrap_wtf.html   # Bootstrap form macros
│   │   ├── 📄 index.html           # Homepage with posts
│   │   ├── 📄 login.html           # User login form
│   │   ├── 📄 register.html        # User registration form
│   │   ├── 📄 user.html            # User profile page
│   │   ├── 📄 edit_profile.html    # Edit user profile
│   │   ├── 📄 upload_profile_image.html # Profile image upload
│   │   ├── 📄 _post.html           # Post display macro
│   │   ├── 📄 reset_password.html  # Password reset form
│   │   ├── 📄 404.html             # 404 error page
│   │   ├── 📄 500.html             # 500 error page
│   │   └── 📁 email/               # Email templates
│   │       ├── 📄 reset_password.html
│   │       └── 📄 reset_password.txt
│   └── 📁 static/                  # Static files
│       └── 📁 profile_pics/        # User profile images
│           ├── 📄 default.jpg      # Default profile image
│           └── 📄 [user_images]    # User uploaded images
├── 📁 migrations/                  # Database migrations
│   ├── 📄 alembic.ini
│   ├── 📄 env.py
│   ├── 📄 README
│   ├── 📄 script.py.mako
│   └── 📁 versions/                # Migration files
├── 📁 logs/                        # Application logs
│   └── 📄 microblog.log
├── 📁 env/                         # Virtual environment
├── 📄 microblog.py                 # Application entry point
├── 📄 databasequery.text           # Database queries reference
└── 📄 PROJECT_STRUCTURE.md         # This file
`

## 🔧 Key Files Description

### Core Application Files
- **microblog.py** - Main entry point, runs the Flask development server
- **app/__init__.py** - Flask app factory, initializes extensions
- **app/config.py** - Configuration settings (database, email, security)
- **app/models.py** - SQLAlchemy models (User, Post, followers table)
- **app/routes.py** - All application routes and view functions
- **app/forms.py** - WTForms form classes for validation
- **app/email.py** - Email sending functionality
- **app/errors.py** - Error handlers for 404/500 pages

### Templates
- **base.html** - Base template with Bootstrap navigation and layout
- **bootstrap_wtf.html** - Bootstrap form macros for consistent styling
- **index.html** - Homepage with post creation and feed
- **login.html** - User authentication form
- **register.html** - User registration form
- **user.html** - User profile display
- **_post.html** - Individual post display component

### Database
- **app.db** - SQLite database file
- **migrations/** - Alembic database migration files

### Static Files
- **static/profile_pics/** - User uploaded profile images
- **default.jpg** - Default profile image for new users

## 🚀 Features Implemented

### Authentication & User Management
- User registration and login
- Password hashing with Werkzeug
- Remember me functionality
- Password reset via email
- Profile image uploads
- User profile editing

### Social Features
- Create and view posts
- Follow/unfollow users
- User feed (posts from followed users)
- Explore all posts
- User profile pages

### Security Features
- CSRF protection
- Secure file uploads
- Input validation
- SQL injection prevention
- XSS protection

### UI/UX Features
- Responsive Bootstrap design
- Modern navigation with dropdowns
- Form validation with error styling
- Flash messages
- Mobile-friendly interface

## 🛠️ Technologies Used

- **Backend**: Flask, SQLAlchemy, Flask-Login, Flask-Mail
- **Frontend**: Bootstrap 5, Bootstrap Icons
- **Database**: SQLite (development)
- **Forms**: WTForms with custom Bootstrap macros
- **Templates**: Jinja2
- **Migrations**: Alembic
- **Security**: Werkzeug security, CSRF protection

## 📋 Setup Instructions

1. **Activate virtual environment**:
   `ash
   .\env\Scripts\Activate.ps1
   `

2. **Install dependencies**:
   `ash
   pip install flask flask-sqlalchemy flask-migrate flask-login flask-mail wtforms
   `

3. **Run database migrations**:
   `ash
   flask db upgrade
   `

4. **Start the application**:
   `ash
   python microblog.py
   `

5. **Access the application**:
   Open http://127.0.0.1:5000 in your browser

## 🔒 Security Notes

- Set SECRET_KEY environment variable in production
- Use PostgreSQL or MySQL for production database
- Configure proper email settings for password reset
- Enable HTTPS in production
- Set up proper logging and monitoring
