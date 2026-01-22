# ComicLoom

[View Live App](comicfront-app-dul8l.ondigitalocean.app) - currently not available due to hosting expences
A full-featured web application for managing and exploring comic collections. Users can browse comics, maintain personal libraries, create wishlists, leave reviews, and admins can manage the comic database.

[View Live App](comicfront-app-dul8l.ondigitalocean.app) - currently not available due to hosting expenses

## Features

### For Users
- **Browse Comics**: Explore a curated collection of comics with details like title, author, genre, and cover images
- **User Authentication**: Register and login securely with JWT-based authentication
- **Personal Library**: Add comics to your reading library with progress tracking
- **Wishlist**: Save comics for future reading
- **Reviews**: Rate and review comics (1-5 stars with comments)
- **Profile Management**: View and manage your account information

### For Admins
- **Comic Management**: Add, edit, and delete comics from the database
- **User Oversight**: Admin privileges for content management
- **Dashboard**: Administrative overview and controls

## Technologies Used

- **Backend**: PHP with FlightPHP micro-framework
- **Database**: MySQL
- **Authentication**: JWT (Firebase JWT)
- **Frontend**: HTML, CSS, JavaScript with jQuery, Bootstrap 5
- **Routing**: Single-page application with SPApp
- **UI Components**: Toastr for notifications, DataTables for listings

## Prerequisites

- **XAMPP** (or similar) with Apache and MySQL
- **PHP** 7.4 or higher
- **MySQL** 5.7 or higher
- **Composer** for PHP dependencies
- **Web Browser** (Chrome, Firefox, etc.)

## Installation & Setup

### 1. Clone or Download the Project
Place the project in your XAMPP htdocs directory:
```
C:\xampp\htdocs\TarikTopic\web-dev-uni\
```

### 2. Install PHP Dependencies
Navigate to the backend directory and install Composer dependencies:
```bash
cd backend
composer install
```

### 3. Database Setup
1. Start XAMPP and ensure Apache and MySQL are running
2. Open phpMyAdmin (http://localhost/phpmyadmin) or MySQL command line
3. Create a database named `comic_collection`
4. Import the SQL dump file:
   - Go to the Import tab in phpMyAdmin
   - Select `dump-comic_collection-202504031821.sql` from the project root
   - Click Go to import

Alternatively, from command line:
```bash
mysql -u root -p comic_collection < dump-comic_collection-202504031821.sql
```

### 4. Configuration
The app uses default database settings (localhost, root/root). If you need to change them, edit `backend/rest/config.php`.

### 5. Access the Application
Open your browser and go to: `http://localhost/TarikTopic/web-dev-uni/frontend/`

## Usage

### First Time Setup
1. **Register**: Create a new account or use existing test accounts:
   - Admin: admin@example.com / password
   - User: collector1@example.com / password

2. **Login**: Use your credentials to access the app

### Navigation
- **Explore**: Browse all available comics
- **Library**: View and manage your reading list
- **Wishlist**: See comics you've saved for later
- **Profile**: Update your account information
- **Admin Settings** (Admin only): Manage comics in the database

### Admin Features
- Click "Add New Comic" to add comics
- Use "Edit" buttons on comic cards to modify details
- Use "Delete" buttons to remove comics
- All changes are reflected immediately in the user interface

## API Endpoints

The backend provides a REST API. Key endpoints include:

### Authentication
- `POST /auth/register` - Register new user
- `POST /auth/login` - User login

### Comics
- `GET /comics` - Get all comics
- `GET /comics/{id}` - Get specific comic
- `POST /comics` - Add new comic (Admin)
- `PUT /comics/{id}` - Update comic (Admin)
- `DELETE /comics/{id}` - Delete comic (Admin)

### User Features
- `GET /user/me` - Get current user profile
- `POST /library/{id}` - Add comic to library
- `POST /wishlist/{id}` - Add comic to wishlist
- `POST /reviews/comic/{id}` - Add review to comic

## Project Structure

```
├── backend/
│   ├── index.php              # Main application entry point
│   ├── rest/
│   │   ├── config.php         # Database configuration
│   │   ├── dao/               # Data Access Objects
│   │   ├── routes/            # API route definitions
│   │   └── services/          # Business logic services
│   └── vendor/                # Composer dependencies
├── frontend/
│   ├── index.html             # Main application page
│   ├── views/                 # SPA view templates
│   ├── services/              # Frontend service classes
│   ├── utils/                 # Utility functions
│   └── assets/                # CSS, JS, images
├── dump-comic_collection-*.sql # Database schema and data
└── README.md                  # This file
```

## Troubleshooting

### Common Issues

1. **Database Connection Error**
   - Ensure MySQL is running in XAMPP
   - Check database credentials in `config.php`
   - Verify database `comic_collection` exists

2. **Page Not Loading**
   - Confirm Apache is running
   - Check browser console for JavaScript errors
   - Ensure all files are in the correct XAMPP directory

3. **Login/Register Not Working**
   - Check PHP error logs in XAMPP
   - Verify JWT secret in `config.php`
   - Ensure database has user table with correct structure

4. **Admin Features Not Available**
   - Login with admin account (admin@example.com)
   - Check user role in database is set to 'admin'

### Logs
- PHP errors: `C:\xampp\apache\logs\error.log`
- MySQL errors: `C:\xampp\mysql\data\mysql_error.log`

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

This project is for educational purposes. Please respect copyright and licensing for any assets used.

---

Built with ❤️ for learning web development fundamentals.
<img width="1661" height="903" alt="image" src="https://github.com/user-attachments/assets/e1536f35-399b-45d5-9993-286f77cea9de" />
