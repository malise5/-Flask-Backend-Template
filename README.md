# 🐍 Flask Backend Template

A scalable, production-ready Flask backend template built with best practices for APIs, database integration, modular design, and environment configuration.

---

## 📁 Project Structure

```
flask_app/
├── app/                  # Main application package
│   ├── config.py         # App configuration (env-based)
│   ├── models/           # SQLAlchemy models
│   ├── routes/           # Route blueprints
│   ├── schemas/          # Marshmallow schemas
│   ├── services/         # Business logic / service layer
│   ├── utils/            # Utility/helper functions
│   └── extensions.py     # Extensions initialization
├── migrations/           # Alembic migrations
├── manage.py             # CLI entry point
├── requirements.txt      # Python dependencies
├── wsgi.py               # WSGI entry point (gunicorn, etc.)
├── .env                  # Environment variables
└── .flaskenv             # Flask-specific environment config
```

---

## 🚀 Features

* ✅ Flask application factory pattern
* ✅ Modular Blueprints
* ✅ SQLAlchemy + Alembic (Flask-Migrate)
* ✅ Marshmallow schema validation
* ✅ RESTful API structure
* ✅ Environment-based config (dev, prod)
* ✅ Gunicorn-ready WSGI
* ✅ CORS and basic security setup
* ✅ CLI support for running and migrating

---

## 📦 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/flask-backend-template.git
cd flask-backend-template
```

### 2. Create a Virtual Environment

```bash
python3 -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

## ⚙️ Configuration

Create a `.env` file in the root:

```env
FLASK_ENV=development
SECRET_KEY=your_secret_key
DATABASE_URL=sqlite:///db.sqlite3
```

---

## 🧪 Running the App (Development)

```bash
flask run
```

The server runs by default at: `http://127.0.0.1:5000`

---

## 🔨 Database Migration

```bash
flask db init       # Only once
flask db migrate -m "Initial migration"
flask db upgrade
```

---

## 🐘 Deployment (Production with Gunicorn)

```bash
gunicorn wsgi:app
```

Or for multi-worker production:

```bash
gunicorn -w 4 -b 0.0.0.0:8000 wsgi:app
```

---

## 🧰 API Example (Register Endpoint)

**POST** `/api/auth/register`

```json
{
  "email": "test@example.com",
  "name": "Test User"
}
```

Response:

```json
{
  "id": 1,
  "email": "test@example.com",
  "name": "Test User"
}
```

---

## ✅ TODO (Optional Enhancements)

* [ ] Add JWT authentication
* [ ] Add role-based access
* [ ] Add rate limiting
* [ ] Add OpenAPI/Swagger docs

---

## 📝 License

This project is licensed under the MIT License.
