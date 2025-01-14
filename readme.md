# EDM System

EDM System is an electronic document, task, and project management server application for teams and companies.  
It is extremely easy to install and configure.  
See **[EDM Project website](https://edmproject.github.io)** to get the complete documentation, screenshots, downloads, etc.

The application has the following functions:
* Documents: create, upload files, edit, delete, approve
* Approval list for documents
* User profiles, companies, departments: create, edit, delete
* Tasks: create, edit, upload files, assign, forward, delete, change status (mark as done, cancel, etc.), add comments with files attached
* Projects: create, edit, add and detach tasks, view tasks by their progress (kanban board), take or assign tasks
* Notifications by e-mail: about user creation to that user, about approvals, about changes and comments in a task to related users
* Themes and localization support
* UX/UI features: bb-code, search results highlighting, etc.
* Some basic bruteforce protection
* Redis support to store sessions and other shared data
* Other functions, not mentioned in this list

Supported themes: dark, light, monochrome-dark, monochrome-light.  
Supported languages: English, Spanish, French, Russian.

## How to build and run
To build use Go (Golang) programming language, run `go build` in the `cmd/edm` directory, then move `cmd/edm/edm` (`cmd\edm\edm.exe` for windows) executable two directories up, and then run it from the root project directory. If you build the application and run locally, by default it immediately opens the browser, so you can start using it.  
Default login: **admin**, for default password use empty string (no password).  
To build with docker and run with docker-compose use: `docker build -t edm .` and then `docker-compose up`. If you run it with docker-compose it does not open the browser by itself. You can open the system at: http://127.0.0.1:8090

## Technical details
The application supports the following RDBMS:
* SQLite
* Microsoft SQL Server
* MySQL(MariaDB)
* Oracle
* PostgreSQL

The application runs on modern browsers: Chrome, Firefox, Safari, and does not support Internet Explorer.  
Config file, logs, uploads, sqlite database are stored in `.edm` directory of a user home directory. See the config file to modify the server configuration.  
Themes are located in the `static/themes` directory.  
Language files are located in `i18nserver` (backend) and `static/i18n` (frontend) directories.
