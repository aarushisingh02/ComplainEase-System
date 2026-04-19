# ComplainEase - Complaint Registration System

A full-stack complaint management system with user and admin dashboards, built with Flask and JSON-based storage.

## Features

### User Features
- Registration and login system with session-based authentication
- Submit complaints with title, description, and category
- View all submitted complaints in a dashboard
- Track complaint status (Pending, In Progress, Resolved)
- View admin responses to complaints

### Admin Features
- Secure admin login
- Dashboard with complaint statistics
- View all user complaints
- Update complaint status
- Add responses to complaints
- Search functionality (by username, complaint ID, or title)
- Filter complaints by status

## Technology Stack

- **Backend**: Python Flask
- **Frontend**: HTML, CSS, JavaScript
- **Storage**: JSON files (no database required)
- **Authentication**: Session-based
## Installation

1. **Clone or download the project**

2. **Install Python dependencies**
   ```bash
   cd complaint_system
   pip install -r requirements.txt
   ```

3. **Run the application**
   ```bash
   python app.py
   ```

4. **Access the application**
   Open your browser and navigate to: `http://localhost:5000`

## Default Admin Account

The system automatically creates a default admin account on first run:

- **Username**: `admin`
- **Password**: `admin123`

**Important**: Change these credentials in production by editing `app.py`

## How JSON Storage Works

### Data Persistence
- All data is stored in JSON files in the `data/` directory
- `users.json` stores user accounts and credentials
- `complaints.json` stores all complaint records
- Files are created automatically on first run

### Data Structure

**users.json**
```json
[
  {
    "id": "unique-uuid",
    "username": "user123",
    "email": "user@example.com",
    "password": "password",
    "is_admin": false,
    "created_at": "2026-04-11T10:00:00"
  }
]
```

**complaints.json**
```json
[
  {
    "id": "unique-uuid",
    "user_id": "user-uuid",
    "username": "user123",
    "title": "Complaint title",
    "description": "Detailed description",
    "category": "Service Quality",
    "status": "Pending",
    "response": "",
    "created_at": "2026-04-11T10:00:00",
    "updated_at": "2026-04-11T10:00:00"
  }
]
```

## Usage Guide

### For Users

1. **Register**: Create an account with username, email, and password
2. **Login**: Sign in with your credentials
3. **Submit Complaint**: Use the "Submit Complaint" form
4. **Track Status**: View all your complaints and their current status
5. **View Responses**: Check admin responses in the complaint cards

### For Admins

1. **Login**: Use admin credentials
2. **View Dashboard**: See statistics and all complaints
3. **Search/Filter**: Find specific complaints using search or status filters
4. **Update Status**: Click edit icon to change complaint status
5. **Add Response**: Provide feedback to users via the response field

## Complaint Categories

- Service Quality
- Product Defect
- Billing Issue
- Delivery Problem
- Customer Support
- Technical Issue
- Other

## Status Types

- **Pending**: Newly submitted, awaiting review
- **In Progress**: Being actively worked on
- **Resolved**: Completed and closed

## Error Handling

The system includes comprehensive error handling:
- Form validation on frontend and backend
- User-friendly error messages
- Session management
- Duplicate prevention (usernames, emails)
- Graceful handling of missing data files
