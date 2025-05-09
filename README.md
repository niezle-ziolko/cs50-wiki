# CS50 Project 1 - Wiki

This is a simple Wikipedia-style encyclopedia built with Django, HTML, and CSS. The project was created as part of Harvard's CS50’s Web Programming with Python and JavaScript course and includes dynamic page rendering, Markdown support, editing, searching, and content creation features.

## 🗂️ Project Structure

The Django project contains the following key elements:

```
cs50-wiki/
├── encyclopedia/           # Django app for the wiki
│   ├── migrations/
│   │   └── __init__.py
│   ├── static/
│   │   └── encyclopedia/
│   │       ├── favicon.ico
│   │       ├── logo-dark.webp
│   │       ├── logo-light.webp
│   │       ├── script.js
│   │       └── styles.css
│   ├── templates/
│   │   └── encyclopedia/
│   │       ├── edit.html
│   │       ├── index.html
│   │       ├── layout.html
│   │       ├── new.html
│   │       ├── page.html
│   │       ├── result.html
│   │       └── results.html
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── models.py
│   ├── tests.py
│   ├── urls.py
│   ├── util.py             # Helper functions for Markdown & file handling
│   └── views.py
├── entries/                # Folder with app content
│   ├── CSS.md
│   ├── Django.md
│   ├── Git.md
│   ├── HTML.md
│   ├── Pepe-the-Frog.md
│   ├── Python.md
│   └── Test.md
├── wiki/                   # Main project configuration
│   ├── __init__.py
│   ├── asgi.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── .gitignore
├── LICENSE
├── manage.py
├── README.md
└── requirements.txt
```

The core logic for rendering, searching, editing, and navigating entries is implemented in the `encyclopedia` app.

## ✅ Features Overview

This section summarizes each feature implemented in the application.

### 📖 Entry Page
  - Visiting `/wiki/TITLE` displays the entry's content.
  - If the entry exists:
    - The page displays the corresponding Markdown-converted content.
    - The HTML title reflects the entry title.
  - If the entry does not exist:
    - An error page is displayed indicating the entry was not found.

### 🏠 Index Page
  - The homepage lists all encyclopedia entries alphabetically as clickable links.
  - Clicking a link redirects to the corresponding entry page.

### 🔎 Search Functionality
  - A search box is always available in the sidebar.
  - Behavior:
    - If the query **exactly matches** an entry title:
      - Redirects directly to that entry.
    - If the query is a **substring match**:
      - Displays a search results page with all partial matches.
      - Clicking a result leads to the respective entry page.

### ➕ New Page Creation
  - The sidebar includes a “Create New Page” link.
  - Users are taken to a form where they can:
    - Provide a title and Markdown content.
    - Submit the form to create the entry.
  - Validation:
    - If an entry with that title already exists:
      - An error is shown.
    - Otherwise:
      - The entry is saved and the user is redirected to the new page.

### ✏️ Edit Page
  - Each entry page includes an “Edit” link.
  - The edit interface:
    - Displays a `textarea` pre-filled with the entry’s current Markdown.
    - Users can make changes and save them.
    - After saving, the user is redirected to the updated entry.

### 🎲 Random Page
  - A “Random Page” link in the sidebar redirects to a randomly chosen entry.

### 🔁 Markdown Conversion
  - Entry content is stored as Markdown files.
  - Before rendering, content is converted to HTML using the `markdown2` package:
    ```bash
    pip3 install markdown2
    ```

### 💡 Additional Notes
  - **Consistency**: The site follows a clean and uniform design for easy navigation.
  - **Error Handling**: Invalid actions (e.g., duplicate entries, missing pages) trigger clear, informative messages.
  - **Extensibility**: The modular code structure supports future feature additions or design changes.

## 🚀 Running the Application

To run the app locally:

### Install dependencies

```bash
pip install -r requirements.txt
```

### Database setup

```bash
python manage.py makemigrations
python manage.py migrate
```

### Start development server

```bash
python manage.py runserver
```

## 🧱 Static Assets

To collect and build static assets:

```bash
python manage.py collectstatic
```

## 🎥 Demo

Video walkthrough of the project and specifications:
👉 https://youtu.be/VMSHx8HTh2w

## 📜 Certification
This project was submitted as part of the CS50’s Web Programming with Python and JavaScript course offered by Harvard University.
Upon successful completion, I was awarded a certificate, which is available here:

🎓 [View Certificate](https://certificates.cs50.io/6f5116d0-882d-4fc1-9dc6-0c96c5d4c7b1.pdf)
