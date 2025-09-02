OS-based Booking System

An Operating Systems-inspired Room Booking System built with Django REST Framework, using process scheduling (FCFS) and synchronization (mutexes & semaphores) concepts.

This project demonstrates how OS-level scheduling and concurrency principles can be applied to a real-world booking system, ensuring fairness and preventing overbooking.

Features

Room Management – View available rooms and slots

Booking System – Users can request bookings for rooms

Process Scheduling (FCFS) – Bookings are scheduled using First Come First Serve algorithm

Concurrency Control – Uses mutex locks, semaphores, and transactions to handle simultaneous bookings

Queue Monitoring – See all queued and running processes

Error Handling – Handles cases like room full, room not found, and concurrent booking conflicts

Tech Stack

Python 3

Django + Django REST Framework (DRF)

Threading & Synchronization (mutex, semaphores)

SQLite / PostgreSQL (Django ORM)

Project Structure
OS-based-Booking-system/
│── booking/                # Django app
│   ├── models.py           # Room & Booking models
│   ├── serializers.py      # DRF serializers
│   ├── views.py            # API endpoints + scheduling logic
│   └── urls.py             # API routes
│── manage.py
│── README.md

Getting Started
1. Clone the repo
git clone https://github.com/ipsita-23/OS-based-Booking-system.git
cd OS-based-Booking-system

2. Create a virtual environment
python -m venv venv
source venv/bin/activate   # On Linux/Mac
venv\Scripts\activate      # On Windows

3. Install dependencies
pip install -r requirements.txt

4. Run migrations
python manage.py makemigrations
python manage.py migrate

5. Start the server
python manage.py runserver


Server runs at: http://127.0.0.1:8000/

API Endpoints
Method	Endpoint	Description
GET	/rooms/	List all rooms
GET	/rooms/<room_id>/bookings/	List bookings for a room
POST	/processes/create/	Create a dummy process
GET	/processes/	List all processes
POST	/booking/create/	Queue a booking request
GET	/process/schedule/	Run FCFS scheduling
GET	/queue/	Show queued & running processes
Example Booking Flow

User requests booking → Added to process queue

Worker thread (FCFS) picks next request

Semaphore lock checks available slots

If slot available → booking success

If full → booking fails

Concepts Demonstrated

First Come First Serve (FCFS) Scheduling

Mutex Locks for thread-safe PID generation

Semaphores to control room availability

Database Transactions (select_for_update) to prevent race conditions

Contributing

Feel free to fork this repo, raise issues, and submit PRs.

Author

Ipsita Umang
CSE Student | AI & OS Enthusiast
