
# URL Shortening Service

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Project Structure](#project-structure)
- [Setup and Installation](#setup-and-installation)
- [Security and Environment Variables](#security-and-environment-variables)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Introduction

The **URL Shortening Service** is a web application built using Django that allows users to generate shortened URLs from longer ones for efficient and secure web interactions. This service is ideal for individuals or businesses looking to manage long URLs in a concise manner and provides an easy way to share short, user-friendly URLs. The system ensures efficient performance through MongoDB for data storage and incorporates strong security measures to handle sensitive user data.

## Features

- **URL Shortening**: Users can input long URLs and receive shortened versions that can be easily shared or embedded in applications.
- **MongoDB Integration**: Utilizes MongoDB as the backend database for storing URLs, ensuring flexible and fast data retrieval.
- **User Session Security**: Secured user sessions through cookies, preventing unauthorized access and providing a safe user experience.
- **URL Validation**: All URLs submitted by users are validated for correctness and security.
- **Email Notifications**: Django’s email functionality is incorporated to send personalized emails containing the shortened URLs, ensuring a professional user experience.
- **Environment Variable Management**: Sensitive information like database credentials, email settings, and secret keys are securely managed via environment variables.

## Technologies Used

### Backend
- **Django**: The backend framework used to create the core logic and APIs for URL shortening and user session management.
- **MongoDB**: A NoSQL database used for storing URLs, ensuring flexibility and performance.

### Frontend
- **HTML, CSS, JavaScript**: Used for designing the user interface, making it responsive and user-friendly.

### Security
- **Cookies**: Used to manage user sessions securely.
- **Environment Variables**: Managed sensitive information, such as API keys and database credentials, using environment variables to enhance security.

## Project Structure

```bash
url-shortening-service/
│
├── app/
│   ├── models.py          # MongoDB integration for URL storage
│   ├── views.py           # Logic for URL shortening, validation, and email dispatch
│   ├── forms.py           # Form for URL input and validation
│   ├── templates/         # HTML files for the frontend interface
│   ├── static/            # CSS, JavaScript, and images for the frontend
│   └── urls.py            # URL routing for the application
│
├── manage.py              # Django project management
├── requirements.txt       # Dependencies for the project
└── .env                   # Environment variables file (excluded from Git)
```

### Key Folders:

- `app/`: Contains all the Django application logic, including models, views, forms, and templates for the frontend.
- `templates/`: Houses the HTML files for rendering the URL shortening interface.
- `static/`: Contains CSS and JavaScript files to enhance the frontend appearance and interactivity.

## Setup and Installation

To get the URL Shortening Service up and running, follow the steps below:

### Prerequisites

- **Python 3.x** and **pip**
- **MongoDB** (Make sure MongoDB is installed and running locally or remotely)
- **Git**

### Backend Setup (Django)

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/url-shortening-service.git
   cd url-shortening-service
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Set up the `.env` file for environment variables:
   - Create a `.env` file in the root directory:
     ```bash
     touch .env
     ```
   - Add your MongoDB connection string, secret key, and email configuration (see [Security and Environment Variables](#security-and-environment-variables)).

4. Run migrations (if needed):
   ```bash
   python manage.py migrate
   ```

5. Start the development server:
   ```bash
   python manage.py runserver
   ```

The application will now be accessible at `http://127.0.0.1:8000/`.

## Security and Environment Variables

To ensure security, sensitive information such as the database connection string, secret keys, and email configuration are stored in environment variables.

### Example `.env` file:

```bash
SECRET_KEY='your-django-secret-key'
MONGO_DB_CONNECTION_STRING='mongodb://localhost:27017/yourdbname'
EMAIL_HOST_USER='youremail@example.com'
EMAIL_HOST_PASSWORD='your-email-password'
EMAIL_HOST='smtp.example.com'
EMAIL_PORT=587
```

**Note**: Never commit the `.env` file to version control (e.g., Git). Add it to your `.gitignore` file.

### Setting Up Email Functionality

To enable the application to send personalized emails containing shortened URLs:

1. Configure your email settings in the `.env` file as shown above.
2. Make sure you have a valid SMTP email service to send emails.

## Usage

Once the application is set up:

1. Go to the homepage.
2. Input a long URL in the form and submit it.
3. The application will return a shortened URL, which can be shared or embedded.
4. An email with the shortened URL will also be sent to the user’s registered email (if configured).

## Contributing

We welcome contributions to improve this URL Shortening Service. To contribute:

1. Fork the repository.
2. Create a new branch.
3. Make your changes and test thoroughly.
4. Submit a pull request.

