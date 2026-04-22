# 📓 DevLog — Developer Journal API

A backend API that allows developers to **log their learning, track journal entries, and organize notes using tags**.

Built as a **learning project** to understand authentication systems, multi-user platforms, database relationships, and real backend problem solving.

---

## 🌐 Live Demo

- **Frontend**: [https://logyou.lovable.app/](https://logyou.lovable.app/)
- **API**: [https://journal-api-jjmx.onrender.com](https://journal-api-jjmx.onrender.com)
- **API Docs**: [https://journal-api-jjmx.onrender.com/docs](https://journal-api-jjmx.onrender.com/docs)

---

## 📚 What I Learned Building This

Building this project helped me understand important backend concepts:

🔐 **JWT Authentication**
How login systems work, how tokens are generated, and how APIs verify users.

👥 **Multi-User Platforms**
Ensuring each user can only access **their own data**.

🗄️ **Database Relationships**

* **One-to-Many** → `Users → Entries`
* **Many-to-Many** → `Entries ↔ Tags`

🛡️ **Protected Routes**
Using **FastAPI dependency injection** to protect endpoints.

🧠 **Debugging & Problem Solving**
Fixing dependency issues, solving errors, and thinking through backend edge cases.

---

## ✨ Features

🔐 **User authentication with JWT**
- Register new users
- Login and receive authentication token

🔑 **Password hashing**
- Secure password storage using **bcrypt**

📝 **Journal entries**

Users can create entries with:
- Title
- Content
- Mood (good / neutral / bad)
- Date
- Optional tags

🏷️ **Tagging system**

Add tags like `python`, `fastapi`, `debugging`, `backend`

🔎 **Filter entries by tag**

🤖 **AI-powered weekly summary**
- Reads your last 7 entries and generates a progress summary

🔒 **User-specific data**
Each user can **only access their own entries**

---

## 🛠️ Tech Stack

| Technology    | Purpose                        |
| ------------- | ------------------------------ |
| ⚡ FastAPI     | Backend framework              |
| 🗄️ SQLite    | Local database                 |
| 🐘 PostgreSQL | Production database            |
| 🔗 SQLAlchemy | ORM for models & relationships |
| 📦 Pydantic   | Data validation                |
| 🔐 bcrypt     | Password hashing               |
| 🎫 JWT        | Authentication tokens          |

---

## 📂 Project Structure
dev-journal-api/
├── app/
│   ├── main.py
│   ├── database.py
│   ├── auth/
│   │   ├── models.py
│   │   ├── schemas.py
│   │   ├── router.py
│   │   └── utils.py
│   ├── entries/
│   │   ├── models.py
│   │   ├── schemas.py
│   │   └── router.py
│   └── tags/
│       ├── models.py
│       ├── schemas.py
│       └── router.py
├── .env
├── Procfile
└── requirements.txt

---

## ⚙️ Running Locally

**1. Clone the repository**
```bash
git clone https://github.com/ErA-16/Journal-api.git
cd Journal-api
```

**2. Create virtual environment**
```bash
python -m venv venv
source venv/bin/activate  # Mac/Linux
venv\Scripts\activate     # Windows
```

**3. Install dependencies**
```bash
pip install -r requirements.txt
```

**4. Create `.env` file**
SECRET_KEY=your-secret-key-here

**5. Run the server**
```bash
uvicorn app.main:app --reload
```

**6. Open API docs**
http://127.0.0.1:8000/docs

---

## 📡 API Endpoints

### 🔐 Auth

| Method | Endpoint         | Description             |
| ------ | ---------------- | ----------------------- |
| POST   | /auth/register   | Register a user         |
| POST   | /auth/login      | Login and get JWT token |

### 📝 Entries

| Method | Endpoint          | Description           |
| ------ | ----------------- | --------------------- |
| POST   | /entries/         | Create entry          |
| GET    | /entries/entry    | Get all entries       |
| GET    | /entries/summary  | Get AI weekly summary |
| GET    | /entries/{id}     | Get single entry      |
| PUT    | /entries/{id}     | Update entry          |
| DELETE | /entries/{id}     | Delete entry          |

### 🏷️ Tags

| Method | Endpoint                       | Description           |
| ------ | ------------------------------ | --------------------- |
| POST   | /entries/{id}/tags             | Add tag to entry      |
| DELETE | /entries/{id}/tags/{tag_name}  | Remove tag            |
| GET    | /entries/filter?tag=python     | Filter entries by tag |

---

## 🔑 Environment Variables

| Variable      | Description                                |
| ------------- | ------------------------------------------ |
| SECRET_KEY    | Secret key used to sign JWT tokens         |
| DATABASE_URL  | PostgreSQL connection URL (set by Render)  |

---

## 🚀 Deployment

The project is deployed using:

☁️ **Render** — backend hosting
🐘 **PostgreSQL** — production database (provisioned on Render)

Render automatically provides the **DATABASE_URL** environment variable when you add a PostgreSQL database to your service.

---

## 💡 Possible Future Improvements

- 📊 Analytics on journal activity
- 🔍 Full text search through entries
- 📅 Entry reminders
- 📱 Mobile app

---

## 👨‍💻 Author

Built as a learning project while exploring **backend engineering, authentication systems, and database design**.
