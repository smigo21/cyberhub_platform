# CyberHub Platform

A Django-based cybersecurity community platform for Bahir Dar University.

## Features

- User registration and member management
- CTF competitions and challenges
- Forum discussions
- Blog posts and community content
- Event management
- Admin dashboard
- REST API

## Quick Start

### Prerequisites

- Python 3.8+
- pip

### Installation

1. **Clone or download the project**

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the setup script**
   ```bash
   python run_server.py
   ```

   This will:
   - Run database migrations
   - Create a superuser (admin/admin123)
   - Populate sample data
   - Start the development server

4. **Access the application**
   - Main site: http://localhost:8000
   - Admin panel: http://localhost:8000/admin
   - API docs: http://localhost:8000/api

### Manual Setup (Alternative)

If the setup script doesn't work, run these commands manually:

```bash
# Set environment variable
export DJANGO_SECRET_KEY="your-secret-key-here"

# Run migrations
python manage.py makemigrations
python manage.py migrate

# Create superuser
python manage.py createsuperuser

# Populate sample data (optional)
python manage.py populate_sample_data

# Run server
python manage.py runserver
```

## Default Credentials

- **Admin User**: admin / admin123
- **Test Member**: testuser / testpass123

## Project Structure

```
cyburhub_platform/
├── main/                   # Main Django app
├── templates/              # HTML templates
├── static/                 # CSS, JS, images
├── cyburhub/              # Django project settings
├── requirements.txt        # Python dependencies
├── run_server.py          # Setup script
└── README.md              # This file
```

## Key Fixed Issues

1. **Template Rendering**: Fixed admin dashboard context data
2. **Security**: Removed hardcoded secrets, added proper validation
3. **Authorization**: Fixed admin access controls
4. **Forms**: Added proper CSS classes and error handling
5. **Media Files**: Configured proper file upload handling
6. **Database**: Fixed migration and model issues

## Development

- The project uses SQLite for development
- Debug mode is enabled by default
- Static files are served automatically in development
- Media files (uploads) are stored in the `media/` directory

## Production Deployment

For production:

1. Set `DEBUG = False` in settings
2. Configure proper database (PostgreSQL recommended)
3. Set up proper static file serving (nginx/Apache)
4. Use environment variables for sensitive settings
5. Enable HTTPS and security headers

## Troubleshooting

1. **Migration errors**: Delete `db.sqlite3` and run migrations again
2. **Static files not loading**: Check `STATIC_URL` and `STATICFILES_DIRS` settings
3. **Permission errors**: Ensure proper admin user setup
4. **Template errors**: Check template syntax and context variables

## Support

For issues and questions, check the code review findings in your IDE or create an issue in the project repository.