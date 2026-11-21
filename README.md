# 🔐 SecureAuth

A terminal-based user registration and login system in **Python** that follows basic secure-authentication practices: salted password hashing, brute-force lockout, and SQL-injection-safe queries. Built to understand *why* passwords should never be stored in plain text.

---

## 📌 Features

- Registration with username validation and password strength rules
- Passwords hashed with **PBKDF2-HMAC-SHA256** (310,000 iterations) and a unique random **salt** per user
- Constant-time hash comparison (`hmac.compare_digest`)
- **Account lockout** for 30 seconds after 3 failed logins (brute-force protection)
- Same error message for wrong username and wrong password (prevents user enumeration)
- Parameterized SQL queries (prevents SQL injection)
- Hidden password input using `getpass`
- Unit tests covering hashing, lockout, duplicate users and an injection attempt

---

## 🛠️ Tech Stack

| Component | Technology |
|-----------|------------|
| Language | Python 3 (standard library only) |
| Database | SQLite |
| Security | PBKDF2-HMAC-SHA256, salting, account lockout |
| Testing | unittest |

---

## 🧱 Project Structure

```
SecureAuth-Python/
├── main.py        # terminal menu
├── auth.py        # register / login / lockout logic
├── security.py    # hashing and password strength checks
├── db.py          # SQLite setup
├── test_auth.py   # unit tests
└── README.md
```

---

## ▶️ How to Run

```bash
git clone https://github.com/<your-username>/SecureAuth-Python.git
cd SecureAuth-Python
python main.py
```

Run the tests:

```bash
python -m unittest -v
```

No extra packages needed.

---

## 🖼️ Screenshots

> Add a screenshot of the register, login and lockout flow here.

---

## 💡 What I Learned

- Why hashing and salting matter, and how they differ from encryption
- How account lockouts slow down brute-force attacks
- How parameterized queries stop SQL injection

---

## 🚀 Future Improvements

- Two-factor authentication (TOTP)
- Password reset flow
- Login attempt
