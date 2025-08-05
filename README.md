# Stock Market Dashboard - Flask Application

A comprehensive Flask web application that provides real-time stock market data, user authentication, and a modern dashboard interface for tracking Indian market indices and stocks.

## 🚀 Features

### Core Functionality
- **Real-time Stock Data**: Live tracking of major Indian market indices (Nifty 50, Bank Nifty, Sensex)
- **Individual Stock Tracking**: Monitor specific stocks like Reliance Industries
- **User Authentication**: Secure registration and login system with email verification
- **Password Recovery**: Forgot password functionality with OTP verification
- **Responsive Dashboard**: Modern, mobile-friendly interface

### Security Features
- **Password Hashing**: Bcrypt encryption for secure password storage
- **Rate Limiting**: Protection against brute force attacks (5 login attempts per minute)
- **Session Management**: Secure user sessions with Flask-Login
- **Email Verification**: Welcome emails sent upon successful registration

### Technical Features
- **SQLite Database**: Lightweight database for user management
- **Flask Extensions**: Comprehensive use of Flask ecosystem
- **Real-time Data**: Integration with Yahoo Finance API via yfinance
- **Email Integration**: SMTP email functionality for notifications

## 📋 Prerequisites

Before running this application, make sure you have the following installed:
- Python 3.7 or higher
- pip (Python package installer)

## 🛠️ Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd app
   ```

2. **Navigate to the App directory**
   ```bash
   cd App
   ```

3. **Create a virtual environment (recommended)**
   ```bash
   python -m venv venv
   
   # On Windows
   venv\Scripts\activate
   
   # On macOS/Linux
   source venv/bin/activate
   ```

4. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

5. **Set up environment variables**
   Create a `.env` file in the App directory with the following variables:
   ```env
   MAIL_SERVER=smtp.gmail.com
   MAIL_PORT=587
   MAIL_USE_TLS=True
   MAIL_USERNAME=your_email@gmail.com
   MAIL_PASSWORD=your_app_password
   MAIL_DEFAULT_SENDER=your_email@gmail.com
   ```

   **Note**: For Gmail, you'll need to use an App Password instead of your regular password. Enable 2-factor authentication and generate an App Password.

6. **Initialize the database**
   The database will be automatically created when you run the application for the first time.

## 🚀 Running the Application

1. **Start the Flask application**
   ```bash
   python app.py
   ```

2. **Access the application**
   Open your web browser and navigate to:
   ```
   http://localhost:5000
   ```

## 📱 Usage

### Registration
1. Click on "Register" to create a new account
2. Fill in your username, email, and password
3. Upon successful registration, you'll receive a welcome email
4. Login with your credentials

### Dashboard
- View real-time data for major Indian market indices
- Monitor Nifty 50, Bank Nifty, and Sensex values
- Access individual stock information

### Stock Tracking
- Navigate to the Stock page to view specific stock data
- Currently tracks Reliance Industries and Nifty 50

### Password Recovery
1. Click "Forgot Password" on the login page
2. Enter your registered email address
3. Check your email for the OTP code
4. Enter the OTP and set a new password

## 🏗️ Project Structure

```
App/
├── app.py                 # Main Flask application
├── models.py             # Database models
├── forms.py              # Flask-WTF forms
├── extensions.py         # Flask extensions configuration
├── requirements.txt      # Python dependencies
├── static/
│   └── styles.css        # CSS styles
├── templates/
│   ├── base.html         # Base template
│   ├── home.html         # Home page
│   ├── login.html        # Login page
│   ├── register.html     # Registration page
│   ├── dashboard.html    # Dashboard page
│   ├── stock.html        # Stock tracking page
│   ├── forgot.html       # Password recovery page
│   ├── verify_otp.html   # OTP verification page
│   ├── change_password.html # Password change page
│   └── welcome_email.html # Email template
```

## 🔧 Configuration

### Database
- **Type**: SQLite
- **File**: `site.db` (created automatically)
- **Location**: App directory

### Email Configuration
- **SMTP Server**: Configurable via environment variables
- **TLS**: Enabled by default
- **Port**: 587 (configurable)

### Rate Limiting
- **Login Attempts**: 5 per minute
- **General Requests**: 200 per day, 50 per hour

## 📊 Dependencies

### Core Dependencies
- **Flask**: Web framework
- **Flask-SQLAlchemy**: Database ORM
- **Flask-Login**: User session management
- **Flask-Bcrypt**: Password hashing
- **Flask-Mail**: Email functionality
- **Flask-Limiter**: Rate limiting
- **Flask-WTF**: Form handling

### Data Dependencies
- **yfinance**: Yahoo Finance API integration
- **pandas**: Data manipulation
- **numpy**: Numerical operations

### Utility Dependencies
- **python-dotenv**: Environment variable management
- **email-validator**: Email validation
- **Werkzeug**: WSGI utilities

## 🔒 Security Considerations

- Passwords are hashed using bcrypt
- Rate limiting prevents brute force attacks
- Session management with Flask-Login
- CSRF protection with Flask-WTF
- Environment variables for sensitive data

## 🐛 Troubleshooting

### Common Issues

1. **Email not sending**
   - Check your `.env` file configuration
   - Ensure you're using an App Password for Gmail
   - Verify SMTP settings

2. **Database errors**
   - Delete `site.db` and restart the application
   - Check file permissions

3. **Import errors**
   - Ensure all dependencies are installed: `pip install -r requirements.txt`
   - Activate your virtual environment

4. **Rate limiting errors**
   - Wait for the rate limit to reset
   - Check your request frequency

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 📞 Support

For support and questions:
- Create an issue in the repository
- Check the troubleshooting section above

## 🔄 Updates

Stay updated with the latest changes by:
- Watching the repository
- Checking the releases page
- Following the commit history

---

**Note**: This application is for educational and personal use. Always verify stock data from official sources before making investment decisions. 