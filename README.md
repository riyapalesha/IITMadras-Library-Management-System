# BookVista: Library Management System

BookVista is a full-stack web application designed to facilitate the management and distribution of e-books across various sections of an online library. The system offers a seamless experience for both users and administrators to issue, return, and manage digital resources.


## Features

* **User Authentication:** Secure user login, registration, and role-based access control.
* **E-Book Management:** Browse, issue, and return e-books, alongside leaving user feedback.
* **Admin Dashboard:** Librarians can add, delete, and update e-books and sections, as well as grant or revoke user requests.
* **Visual Analytics:** Real-time statistics tracking active users, book distributions across sections, and request metrics.
* **Advanced Search:** Find books instantly by title, author, or section.
* **Automated Notifications & Reports:** Email alerts reminding users of upcoming returns and monthly summary reports sent to administrators.
* **Background Task Scheduling:** Periodic jobs handled via Celery and Redis.
* **Data Export:** Export user and book datasets delivered directly via email.
* **Dummy Payment Portal:** Integrated simulation for purchasing e-books.



## Project Structure

Since this repository combines both the backend and frontend into a single project workspace, follow the setup instructions below to get everything running locally.



## Project Setup

### 1. Backend Setup

Open a terminal window and navigate to the `backend/` directory:

```bash
cd Library-Management-System-backend

```

Create a Python virtual environment:

```bash
python3 -m venv env

```

Activate the environment:

* **macOS / Linux:**
```bash
source env/bin/activate

```


* **Windows (Git Bash / PowerShell):**
```bash
source env/Scripts/activate

```



Install Python requirements:

```bash
pip install -r requirements.txt

```

#### Running Background Services & Application

Make sure you have **Redis** installed and start the Redis server:

```bash
redis-server

```

In separate terminal tabs (with your virtual environment activated), start your Celery worker and beat scheduler:

* **Start Celery Worker:**
```bash
celery -A main:celery_app worker -P solo --loglevel INFO

```


* **Start Celery Beat Scheduler:**
```bash
celery -A main:celery_app beat --loglevel INFO

```



Finally, start the main web application:

```bash
python3 main.py

```

---

### 2. Frontend Setup

Open a separate terminal window and navigate to the `frontend/` directory:

```bash
cd Library-Management-System-frontend

```

Install project dependencies:

```bash
npm install

```

Compile and hot-reload for local development:

```bash
npm run serve

```

Compile and minify for production:

```bash
npm run build

```

#### Lints and Fixes Files

```bash
npm run lint

```
