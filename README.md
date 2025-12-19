# Student Wellness Management System (SWMS)

**University:** East West University
**Department:** Department of CSE
**Submitted to:** K. M. Safin Kamal (KMSK), Lecturer

## Project Overview

A C-based management system designed to monitor and support student mental health. It enables daily mood tracking, automated and manual consultation recommendations, and appointment scheduling between students and mental health professionals.

## Project Structure

The code has been organized into separate files based on functionality:

### Files Overview

- **`common.h`** - Header file containing all shared structures, constants, and function prototypes
- **`student.c`** - All student-related functions (registration, login, mood entry, reports, appointments)
- **`faculty.c`** - All faculty/teacher-related functions (login, view mood data, recommend students)
- **`consultant.c`** - All consultant-related functions (login, view recommendations, manage appointments)
- **`admin.c`** - All administrator functions (login, add faculty/consultants, view registrations)
- **`main.c`** - Main function with the primary menu system

### Features

#### Student Features
- **Registration and Login**: Secure access for students.
- **Daily Mood Tracking**: Input mood scores (1-10) and detailed notes. Scores below 5 trigger automatic consultation recommendations.
- **Reports**: View mood history (Today, Weekly, Monthly, 3-Month trends).
- **Appointments**: Book appointments with consultants and view status.
- **Recommendations**: View and respond to faculty or system recommendations.

#### Faculty Features
- **Login**: Secure access for faculty.
- **Mood Monitoring**: View average mood levels for students in assigned courses/sections.
- **Vulnerable Student Identification**: Identify students with average mood < 5.
- **Manual Recommendations**: Recommend students for consultation based on mood trends.
- **Tracking**: Track the status of recommendations.

#### Consultant Features
- **Login**: Secure access for consultants.
- **Recommendation Management**: View pending recommendations from faculty and the system.
- **Appointment Scheduling**: Schedule dates and times for recommended students.
- **Management**: View scheduled appointments and accept/reject requests.

#### Administrator Features
- **Secure Login**: Centralized management.
- **User Management**: View and manage all registered students, faculty, and consultants.
- **Add Users**: Register new faculty members and consultants.

### Data Files
- `students.txt` - Student registration data
- `teachers.txt` - Faculty registration data
- `consultants.txt` - Consultant registration data
- `mood_entries.txt` - Student mood entries (Daily logs)
- `recommendations.txt` - Faculty and system recommendations
- `appointments.txt` - Appointment data

## Technical Implementation

- **Language:** C
- **Libraries Used:** `stdio.h`, `stdlib.h`, `string.h`, `time.h` (for real-time date/time handling).

### Key Data Structures
- **`Student` / `Teacher` / `Consultant`**: Stores ID, Name, Password, and academic metadata.
- **`MoodEntry`**: Stores student ID, mood score, notes, and date.
- **`Recommendation`**: Tracks referral ID, student ID, faculty ID, and status.
- **`Appointment`**: Tracks student-consultant pairings with date, time, and status.

## Compilation

To compile the project, you can either:

1. **Compile all files together:**
   ```bash
   gcc -o swms main.c student.c faculty.c consultant.c admin.c
   ```

2. **Compile separately and link:**
   ```bash
   gcc -c main.c student.c faculty.c consultant.c admin.c
   gcc -o swms main.o student.o faculty.o consultant.o admin.o
   ```

## Usage

Run the compiled executable:
```bash
./swms
```

### Default Admin Credentials
- Username: `admin_swms`
- Password: `swmsewu2025`

## Code Organization Benefits

- **Modularity**: Each file handles specific functionality
- **Maintainability**: Easier to locate and modify specific features
- **Readability**: Cleaner code structure with logical separation
- **Collaboration**: Multiple developers can work on different modules
- **Debugging**: Issues can be isolated to specific modules
