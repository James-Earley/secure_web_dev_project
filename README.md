# secure_web_dev_project: WebDevWonders: A Showcase of Secure Web Features
 Flask-based web application designed to showcase various secure web features. 

## Introduction

WebDevWonders is a Flask-based web application designed to showcase various secure web features. This application aligns with the final project requirements of CT5173 - Secure Web Programming, offered at the University of Galway. It demonstrates practical implementations of web security measures, including authentication, input sanitization, and CSRF protection.

## Getting Started

### Requirements

- Python 3.8 or higher
- Flask
- SQLite
- Werkzeug for security utilities
- Flask-WTF for form handling and CSRF protection
- Bleach for input sanitization

### Installation

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/yourrepository/webdevwonders.git
   cd webdevwonders
   ```

2. **Set up a Virtual Environment (Optional but recommended):**

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. **Install Dependencies:**

   ```bash
   pip install Flask sqlite3 bleach Flask-WTF
   ```

4. **Environment Variables:**

   Set the `FLASK_SECRET_KEY` environment variable for session management:

   ```bash
   export FLASK_SECRET_KEY='your_secret_key_here'  # On Windows use `set FLASK_SECRET_KEY=your_secret_key_here`
   ```

### Database Setup

Run the following SQLite commands to create the necessary database schema:

```sql
CREATE TABLE users(id INTEGER PRIMARY KEY, username TEXT, password TEXT, email TEXT, fname TEXT, lname TEXT, gender TEXT, bio TEXT, is_admin INTEGER);
CREATE TABLE echo(content TEXT, user_id INTEGER);
CREATE TABLE facts(fact TEXT, user_id INTEGER);
CREATE TABLE polls(question_id INTEGER, option_text TEXT, votes_count INTEGER);
CREATE TABLE questions(id INTEGER PRIMARY KEY, text TEXT);
CREATE TABLE votes(id INTEGER PRIMARY KEY, question_id INTEGER, user_id INTEGER, option_id INTEGER);
```

### Running the Application

1. **Start the Flask Application:**

   ```bash
   flask run
   ```

   The application will be accessible at `http://127.0.0.1:5000/`.

## Features

- **User Authentication:** Signup, login, and logout functionalities.
- **Admin Interface:** Special admin privileges for user and poll management.
- **Secure Forms:** Utilization of Flask-WTF and CSRF tokens for form submissions.
- **Data Sanitization:** Input sanitization with Bleach to prevent XSS attacks.
- **Echo Feature:** Demonstrates secure user input echoing.
- **Polls and Facts:** Interactive polls and facts submission to engage users.

## Security Measures

The application implements various security measures addressed in the practical sessions, including but not limited to:

- **Password Hashing:** Uses Werkzeug to hash and verify passwords securely.
- **CSRF Protection:** Integrates CSRFProtect from Flask-WTF to safeguard against Cross-Site Request Forgery.
- **Input Sanitization:** Employs Bleach for sanitizing user inputs before rendering them or storing in the database.

## Contributions

This project is part of the coursework for CT5173 - Secure Web Programming. Contributions are welcome to extend its functionalities and improve security features.

## License

This project is licensed under the MIT License - see the LICENSE.md file for details.
