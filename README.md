# 📊 Flask Finance Dashboard

A comprehensive Flask web application that provides real-time stock market data, user authentication, and a modern dashboard interface for tracking Indian market indices and stocks.

[![Python](https://img.shields.io/badge/Python-3.7+-blue.svg)](https://www.python.org/downloads/)
[![Flask](https://img.shields.io/badge/Flask-3.0.3-green.svg)](https://flask.palletsprojects.com/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## 🌟 Features

### 📈 Core Functionality

- **Real-time Stock Data**: Live tracking of major Indian market indices (Nifty 50, Bank Nifty, Sensex)
- **Individual Stock Tracking**: Monitor specific stocks like Reliance Industries
- **User Authentication**: Secure registration and login system with email verification
- **Password Recovery**: Forgot password functionality with OTP verification
- **Responsive Dashboard**: Modern, mobile-friendly interface

### 🔒 Security Features

- **Password Hashing**: Bcrypt encryption for secure password storage
- **Rate Limiting**: Protection against brute force attacks (5 login attempts per minute)
- **Session Management**: Secure user sessions with Flask-Login
- **Email Verification**: Welcome emails sent upon successful registration
- **CSRF Protection**: Built-in CSRF protection with Flask-WTF

### 🛠️ Technical Features

- **SQLite Database**: Lightweight database for user management
- **Flask Extensions**: Comprehensive use of Flask ecosystem
- **Real-time Data**: Integration with Yahoo Finance API via yfinance
- **Email Integration**: SMTP email functionality for notifications
- **Environment Configuration**: Secure configuration management with dotenv

## 📋 Prerequisites

Before running this application, make sure you have the following installed:

- **Python 3.7** or higher
- **pip** (Python package installer)
- **Git** (for cloning the repository)

## 🚀 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/DeepanshuTIET/Flask_Finance_Dashboard.git
cd Flask_Finance_Dashboard/App
```

### 2. Create Virtual Environment (Recommended)

```bash
# Create virtual environment
python -m venv venv

# Activate virtual environment
# On Windows
venv\Scripts\activate
# On macOS/Linux
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Environment Configuration

Create a `.env` file in the App directory with the following variables:

```env
# Email Configuration (Gmail Example)
MAIL_SERVER=smtp.gmail.com
MAIL_PORT=587
MAIL_USE_TLS=True
MAIL_USERNAME=your_email@gmail.com
MAIL_PASSWORD=your_app_password
MAIL_DEFAULT_SENDER=your_email@gmail.com
```

**⚠️ Important Notes:**

- For Gmail, you'll need to use an **App Password** instead of your regular password
- Enable 2-factor authentication and generate an App Password from Google Account settings
- You can also use AWS SES or other SMTP providers

### 5. Initialize Database

The database will be automatically created when you run the application for the first time.

## 🏃‍♂️ Running the Application

### Start the Flask Application

```bash
python app.py
```

### Access the Application

Open your web browser and navigate to:

```
http://localhost:5000
```

## 📱 Usage Guide

### 🔐 Registration Process

1. Click on "Register" to create a new account
2. Fill in your username, email, and password
3. Upon successful registration, you'll receive a welcome email
4. Login with your credentials

### 📊 Dashboard Features

- **Real-time Market Data**: View live data for major Indian market indices
- **Nifty 50 Tracking**: Monitor Nifty 50 index values
- **Bank Nifty Monitoring**: Track Bank Nifty performance
- **Sensex Updates**: Real-time Sensex data

### 📈 Stock Tracking

- Navigate to the Stock page to view specific stock data
- Currently tracks:
  - **Reliance Industries** (RELIANCE.NS)
  - **Nifty 50** (^NSEI)

### 🔑 Password Recovery

1. Click "Forgot Password" on the login page
2. Enter your registered email address
3. Check your email for the OTP code
4. Enter the OTP and set a new password

## 🏗️ Project Structure

```
App/
├── app.py                 # Main Flask application
├── models.py             # Database models (User)
├── forms.py              # Flask-WTF forms (Registration, Login)
├── extensions.py         # Flask extensions configuration
├── requirements.txt      # Python dependencies
├── .sample.env           # Environment variables template
├── .gitignore           # Git ignore file
├── static/
│   └── styles.css        # CSS styles
└── templates/
    ├── base.html         # Base template with navigation
    ├── home.html         # Home page
    ├── login.html        # Login page
    ├── register.html     # Registration page
    ├── dashboard.html    # Dashboard page with market data
    ├── stock.html        # Stock tracking page
    ├── forgot.html       # Password recovery page
    ├── verify_otp.html   # OTP verification page
    ├── change_password.html # Password change page
    └── welcome_email.html # Email template
```

## 🔧 Configuration

### Database Configuration

- **Type**: SQLite
- **File**: `site.db` (created automatically)
- **Location**: App directory
- **ORM**: SQLAlchemy with Flask-SQLAlchemy

### Email Configuration

- **SMTP Server**: Configurable via environment variables
- **TLS**: Enabled by default
- **Port**: 587 (configurable)
- **Providers**: Gmail, AWS SES, or any SMTP provider

### Rate Limiting

- **Login Attempts**: 5 per minute
- **General Requests**: 200 per day, 50 per hour
- **Protection**: Prevents brute force attacks

## 📦 Dependencies

### Core Dependencies

- **Flask 3.0.3**: Web framework
- **Flask-SQLAlchemy 3.1.1**: Database ORM
- **Flask-Login 0.6.3**: User session management
- **Flask-Bcrypt 1.0.1**: Password hashing
- **Flask-Mail 0.10.0**: Email functionality
- **Flask-Limiter 3.7.0**: Rate limiting
- **Flask-WTF 1.2.1**: Form handling and CSRF protection

### Data Dependencies

- **yfinance 0.2.40**: Yahoo Finance API integration
- **pandas 2.2.2**: Data manipulation
- **numpy 1.26.4**: Numerical operations

### Utility Dependencies

- **python-dotenv 1.0.1**: Environment variable management
- **email-validator 2.1.1**: Email validation
- **Werkzeug 3.0.3**: WSGI utilities

## 🔒 Security Considerations

- **Password Security**: Passwords are hashed using bcrypt
- **Rate Limiting**: Prevents brute force attacks
- **Session Management**: Secure user sessions with Flask-Login
- **CSRF Protection**: Built-in protection with Flask-WTF
- **Environment Variables**: Sensitive data stored in .env file
- **Input Validation**: Form validation and sanitization

## 🐛 Troubleshooting

### Common Issues and Solutions

#### 1. Email Not Sending

**Problem**: Registration emails or password recovery emails not being sent
**Solutions**:

- Check your `.env` file configuration
- Ensure you're using an App Password for Gmail
- Verify SMTP settings and port configuration
- Check firewall settings

#### 2. Database Errors

**Problem**: Database-related errors or missing tables
**Solutions**:

- Delete `site.db` and restart the application
- Check file permissions in the App directory
- Ensure SQLAlchemy is properly installed

#### 3. Import Errors

**Problem**: ModuleNotFoundError or import issues
**Solutions**:

- Ensure all dependencies are installed: `pip install -r requirements.txt`
- Activate your virtual environment
- Check Python version compatibility

#### 4. Rate Limiting Errors

**Problem**: "Rate limit exceeded" errors
**Solutions**:

- Wait for the rate limit to reset
- Check your request frequency
- Consider increasing limits in development

#### 5. Yahoo Finance API Issues

**Problem**: Stock data not loading
**Solutions**:

- Check internet connectivity
- Verify yfinance package is installed
- Some stock symbols might be temporarily unavailable

## 🚀 Deployment

### Local Development

```bash
python app.py
```

### Production Deployment

For production deployment, consider:

- Using a production WSGI server (Gunicorn, uWSGI)
- Setting up a reverse proxy (Nginx)
- Using a production database (PostgreSQL, MySQL)
- Configuring proper logging
- Setting up SSL/TLS certificates

## 🤝 Contributing

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/AmazingFeature`)
3. **Commit** your changes (`git commit -m 'Add some AmazingFeature'`)
4. **Push** to the branch (`git push origin feature/AmazingFeature`)
5. **Open** a Pull Request

### Development Guidelines

- Follow PEP 8 style guidelines
- Add proper documentation
- Include tests for new features
- Update requirements.txt if adding new dependencies

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 📞 Support

For support and questions:

- **Create an issue** in the repository
- **Check the troubleshooting section** above
- **Review the documentation** in this README

## 🔄 Updates and Maintenance

Stay updated with the latest changes by:

- **Watching** the repository
- **Checking** the releases page
- **Following** the commit history
- **Reviewing** the changelog

## ⚠️ Disclaimer

**Important**: This application is for educational and personal use. Always verify stock data from official sources before making investment decisions. The application uses Yahoo Finance API which may have delays or inaccuracies.

## 🙏 Acknowledgments

- **Yahoo Finance API** for providing stock market data
- **Flask Community** for the excellent web framework
- **Open Source Contributors** for various packages used in this project

---

**Made with ❤️ by [DeepanshuTIET](https://github.com/DeepanshuTIET)**

**Repository**: [https://github.com/DeepanshuTIET/Flask_Finance_Dashboard.git](https://github.com/DeepanshuTIET/Flask_Finance_Dashboard.git)
