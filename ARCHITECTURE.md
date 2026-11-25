# Dashboard Architecture

## System Overview

The dashboard uses a Python-based backend to serve a web interface, store information locally, and connect to external services.

## Architecture Diagram

```text
             USER
               |
               v
       DASHBOARD INTERFACE
        HTML / CSS / JS
               |
               v
        PYTHON BACKEND
               |
       +-------+-------+
       |       |       |
       v       v       v
    LOCAL   GMAIL   BACKGROUND
    JSON    IMAP    PROCESSES
    STORAGE         & ALERTS
       |
       v
  PERSONAL DATA

               |
               v
       REMOTE ACCESS
          TAILSCALE
               |
        +------+------+
        |             |
        v             v
      LAPTOP        MOBILE
```

## Main Components

### 1. Frontend
The dashboard interface uses HTML, CSS, and JavaScript to display information and provide interactive functionality.

### 2. Backend
Python handles application logic, authentication, data management, and communication between components.

### 3. Local Storage
JSON files store dashboard information locally on the computer.

### 4. Email Integration
Gmail IMAP provides access to email information for dashboard notifications.

### 5. Remote Access
Tailscale provides private network connectivity, allowing authorized devices to access the dashboard remotely.

### 6. Background Services
Linux systemd manages the dashboard process, allowing it to run in the background and start automatically.

## Security Approach

- Dashboard data remains stored locally.
- Credentials are stored outside the public project repository.
- Remote access is provided through a private network.
- Authentication protects dashboard access.
- Sensitive personal configuration is excluded from public documentation.
