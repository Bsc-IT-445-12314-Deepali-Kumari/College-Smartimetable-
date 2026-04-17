SmartTimetable ERP is a role-based college timetable management system with:

Admin approval workflows.
Teacher preference submission
Optimization-based timetable generation
Student/Teacher personalized timetable views
Academic calendar and event management

Tech Stack:
Python 3.11+
Flask
PuLP (ILP optimization)
HTML/CSS/JavaScript (Jinja templates)
File-based storage (text/JSON lines) 

Roles and Key Features
Admin
Approve/reject teacher and student signup requests
Approve/reject/edit teacher preference requests
See Generation Stack of approved course preferences
Generate timetable semester-wise
Edit/delete timetable rows before generation
View semester-wise timetable generation history
Manage events and vacations
Teacher
Signup/login after admin approval
Submit subject preferences (day/slot/target department)
View pending/approved preference status
View personal timetable
Manage own calendar events
Student
Signup/login after admin approval
View department-based personal timetable
View institute timetable with filters
View academic calendar and event details
Mathematical Timetable Generation (Brief)

Objective:
Minimize preference violations
Minimize late-slot usage
Apply teacher-priority cost
Implementation file: timetable.py

Project Structure
SmartTimetable/
├── app.py                         # Main Flask app (routes + workflows)
├── timetable.py                   # ILP model and timetable generation
├── templates/                     # All UI templates
│   ├── login.html
│   ├── admin.html
│   ├── admin_edit_preference.html
│   ├── admin_edit_event.html
│   ├── admin_edit_timetable.html
│   ├── teacher_dashboard.html
│   ├── student_dashboard.html
│   ├── student_timetable.html
│   └── profile.html
├── static/
│   └── profile_pics/              # Uploaded profile pictures
├── users.txt                      # Approved users
├── users_pending.txt              # Pending signup requests
├── approval_history.txt           # Signup approve/reject history
├── preference_requests.txt        # Pending teacher preferences
├── preference_history.txt         # Preference decision history
├── data.txt                       # Approved course preferences (generation source)
├── timetable_output.txt           # Current generated timetable
├── timetable_history.txt          # Semester-wise generation history
├── events.txt                     # Calendar events
└── README.md

How to Start the Project
1. Open terminal in project folder
cd /d c:\Users\LENOVO\Desktop\MiniProject2\Code\SmartTimetable
2. Install dependencies (first time only)
pip install flask pulp
3. Run the server
python app.py
4. Open browser
http://127.0.0.1:5000/login
If port 5000 is busy:

set PORT=5050
python app.py
Then open:

http://127.0.0.1:5050/login
Recommended Demo Flow
Login as admin
Approve pending teacher/student accounts
Approve teacher preference requests
Open Generate Timetable section
Review Generation Stack
Generate timetable
Verify timetable in admin, teacher, and student dashboards
