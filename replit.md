# StudentSmart - Hiring Platform

## Overview
StudentSmart is a professional hiring platform inspired by Toptal, designed to connect top student talent with exciting internship opportunities. Built with Python Flask and modern web technologies, it provides a comprehensive solution for student recruitment and talent management.

## Recent Changes
- **November 8, 2025**: Synchronized Hero/Carousel Animations ✅
  - **Toptal-Style Fluid Transitions** - Complete animation overhaul:
    - Removed duplicate carousel cards for clean one-to-one student mapping
    - Unified JavaScript controller with shared `activeIndex` state
    - Smooth 0.5s ease-out fade transitions (fade out → swap → fade in)
    - Auto-advance every 6 seconds with manual control pause (3 seconds)
  - **Visual Synchronization** - Hero and carousel stay in perfect sync:
    - Active carousel card highlights with blue border, scale, and opacity
    - Inactive cards fade to 60% opacity for clear visual hierarchy
    - Auto-scroll centers active card using `scrollIntoView`
    - Arrow navigation and card clicks update both hero and carousel
  - **Reduced Spacing** - Tighter, continuous layout flow:
    - Hero section: 36px/12px padding (reduced from 60px/20px)
    - Carousel section: 12px/40px padding (reduced from 60px/80px)
    - Hero layout gap: 32px (reduced from 40px)
    - Creates seamless visual connection between sections
  - **Responsive Design** - Maintained across all breakpoints:
    - Mobile: Hero stacks above carousel with smooth transitions
    - Desktop: Two-column layout with synchronized animations
    - All fade effects and highlighting work consistently

- **November 4, 2025**: Homepage Carousel Redesign ✅
  - **Toptal-Inspired Layout** - Complete homepage overhaul:
    - Hero section with large featured student profile card on the right
    - Professional gradient card with large profile photo (320x320px)
    - Verified expert badge and previous company information
  - **Horizontal Carousel** - Featured talent showcase:
    - Horizontal profile cards (340px wide) with photo on left, details on right
    - Each card shows: verified badge, name, role, and previous company
  - **Sample Data Added** - Created 10 featured student profiles for demo:
    - Students from top institutions (MIT, Stanford, Harvard, etc.)
    - Roles: Full Stack Developer, ML Engineer, Product Manager, etc.
    - Previous companies: Google, Meta, Apple, Amazon, etc.
    - Admin can feature real students, and carousel will dynamically update

- **November 2, 2025**: Company/Employer Portal ✅
  - **Complete Company Portal** - Full-featured employer access:
    - Dual authentication (Email/Password + Google OAuth) for companies
    - Company registration with business details and logo upload
    - Company dashboard showing posted jobs, view counts, and applicant metrics
    - Job/internship posting interface with optional admin-managed applications
    - Application tracking and management for company-posted positions
    - View tracking system to measure job post engagement
  - **Admin Company Management** - Comprehensive oversight:
    - Companies dashboard listing all registered employers
    - Individual company detail pages with job posts and metrics
    - Ability to view and manage company-posted internships
    - Access to applications for admin-managed company posts
  - **Enhanced Navigation** - "For Companies" link added to navbar
  - **Multi-User Architecture** - Platform now serves three user types:
    - Students (existing features maintained)
    - Companies (new employer portal)
    - Admins (expanded with company management)
  - **Critical Bug Fixes** - Added comprehensive guards for role attribute access preventing crashes when Company users access shared routes

- **November 2, 2025**: UI/UX Improvements ✅
  - **Unified Login Interface** - Single login page for both students and admins (automatic role detection)
  - **Indian States Dropdown** - Added comprehensive dropdown with all 28 states and 8 union territories in onboarding
  - **Professional Profile Page** - Complete redesign with Toptal-inspired layout:
    - Gradient header with large profile photo
    - Timeline-style experience display
    - Hover-animated skill badges
    - Professional typography and spacing
  - **Enhanced Navigation Bar** - Modern user dropdown menu:
    - Round profile photo icon with animation on hover
    - Dropdown contains: My Dashboard, My Profile, My Applications, Logout
    - Mobile-responsive with hamburger menu
    - Smooth animations and transitions

- **November 1, 2025**: Production-ready platform completed ✅
  - Implemented **dual authentication** for students (Email/Password + Google OAuth)
  - Built comprehensive admin dashboard with full management controls
  - Created Toptal-inspired professional UI/UX
  - Added **CSRF protection** to all forms across the application
  - Implemented secure password hashing with Werkzeug
  - Built multi-step onboarding system (5 steps total)
  - Added student profile pages with Toptal-style resume display
  - Created complete admin management for students, internships, and applications
  - Implemented audit logging system tracking all admin actions
  - Added state-wise and college-wise analytics with charts
  - Enabled file uploads (profile photos and resumes) with security

## Project Architecture

### Technology Stack
- **Backend**: Python Flask 3.x
- **Database**: SQLite (SQLAlchemy ORM) - Will be migrated to MySQL in production
- **Authentication**: 
  - **Dual authentication for students and companies**: Email/Password OR Google OAuth 2.0 (via Authlib)
  - Username/password for admin users
  - Secure password hashing with Werkzeug
  - Session-based user type tracking (student/company/admin)
- **Frontend**: HTML5, CSS3, JavaScript, Bootstrap 5
- **Image Processing**: Pillow (PIL)
- **Forms**: Flask-WTF with CSRF protection
- **Migrations**: Flask-Migrate

### Key Features

#### For Students:
1. **Dual Authentication** - Sign up/login with Email & Password OR Google OAuth
2. **Multi-step Onboarding** - Comprehensive 5-step profile creation:
   - Personal information (phone, college, location, bio)
   - Education history (degrees, institutions, grades)
   - Work experience (companies, positions, descriptions)
   - Skills & certifications (proficiency levels, credentials)
   - Profile photo and resume upload
3. **Professional Profile Pages** - Toptal-style resume display
4. **Internship Portal** - Browse and apply to opportunities
5. **Application Tracking** - Monitor application status
6. **Dashboard** - Profile completion percentage and activity overview

#### For Companies:
1. **Dual Authentication** - Sign up/login with Email & Password OR Google OAuth
2. **Company Registration** - Complete profile with:
   - Company name, website, and description
   - Industry and company size
   - Logo upload
3. **Job/Internship Posting** - Create and manage postings:
   - Full job details (title, description, requirements)
   - Salary range and location
   - Optional admin-managed applications
   - View count tracking
4. **Dashboard** - Overview of:
   - Total job posts and applications received
   - View counts per posting
   - Recent applications
5. **Application Management**:
   - View all applications for company-posted jobs
   - Access student profiles and resumes
   - Track application status

#### For Admins:
1. **Comprehensive Dashboard** - Analytics and statistics:
   - Total students, companies, applications, pending reviews
   - State-wise distribution charts
   - College-wise statistics
   - Recent activity feed
2. **Student Management**:
   - View all registered students
   - Filter by college name and state
   - Search by name, email, or skills
   - Approve/reject student profiles
   - Feature top students on homepage
3. **Company Management**:
   - View all registered companies
   - Individual company detail pages
   - Monitor company-posted jobs
   - Manage admin-delegated applications
4. **Internship Management**:
   - Create new internship postings
   - Edit existing opportunities
   - Activate/deactivate listings
   - Track applications per posting
5. **Application Management**:
   - View all applications (admin and company posts)
   - Update application status (pending/reviewed/shortlisted/rejected)
   - Add notes to applications
6. **User Management**:
   - Create new admin accounts
   - Manage admin roles (admin/super_admin)
   - Activate/deactivate users
7. **Audit Logs**:
   - Complete tracking of all admin actions
   - Timestamp, IP address, and action details
   - Pagination for historical review

### Database Models
- **User**: Students and admin users (with password_hash field for email/password auth)
- **Company**: Employer accounts with company details and logo
- **Profile**: Extended student information
- **Education**: Academic qualifications
- **WorkExperience**: Employment history
- **Skill**: Technical and professional skills
- **Certification**: Credentials and certifications
- **Internship**: Job postings (can be posted by admin or company with admin_managed flag)
- **Application**: Student applications to internships
- **AuditLog**: Admin action tracking (timestamp, IP, action, admin)

### File Structure
```
.
├── app.py                  # Main Flask application
├── static/
│   ├── css/
│   │   └── style.css      # Custom Toptal-inspired styling
│   ├── js/
│   ├── images/
│   └── uploads/           # User-uploaded files
│       ├── profile_photos/
│       └── resumes/
├── templates/
│   ├── base.html          # Base template with navigation
│   ├── index.html         # Homepage
│   ├── auth/
│   │   ├── student_register.html   # Student email/password registration
│   │   ├── student_login.html      # Student dual auth login page
│   │   ├── company_register.html   # Company email/password registration
│   │   ├── company_login.html      # Company dual auth login page
│   │   └── admin_login.html        # Admin login page
│   ├── student/           # Student-facing pages
│   │   ├── onboarding_step[1-4].html
│   │   ├── onboarding_complete.html
│   │   ├── dashboard.html
│   │   ├── profile.html
│   │   ├── edit_profile.html
│   │   ├── internships.html
│   │   └── internship_detail.html
│   ├── company/           # Company portal pages
│   │   ├── dashboard.html
│   │   ├── post_job.html
│   │   ├── applications.html
│   │   └── edit_profile.html
│   └── admin/             # Admin panel pages
│       ├── dashboard.html
│       ├── students.html
│       ├── student_detail.html
│       ├── companies.html
│       ├── company_detail.html
│       ├── internships.html
│       ├── create_internship.html
│       ├── edit_internship.html
│       ├── applications.html
│       ├── users.html
│       ├── create_user.html
│       └── audit_logs.html
└── studentsmart.db        # SQLite database (auto-created)
```

## User Preferences
- Stack: Python Flask + HTML/CSS/JS
- Database: SQLite (current) → MySQL (future migration)
- Design: Professional, Toptal-inspired aesthetic
- Focus: Clean code, comprehensive admin controls, scalability

## Default Admin Access
**Email**: admin@studentsmart.co.in  
**Password**: admin123

**Important**: Change this password in production!

## Environment Variables Required
- `SESSION_SECRET`: Flask session secret key (set automatically)
- `GOOGLE_OAUTH_CLIENT_ID`: Google OAuth client ID (required for student and company login)
- `GOOGLE_OAUTH_CLIENT_SECRET`: Google OAuth client secret (required for student and company login)

## Next Phase Features (Planned)
1. Migrate to MySQL database
2. Email notification system
3. Advanced analytics with CSV/PDF export
4. Bulk email functionality for admins
5. Enhanced search with AI-powered matching
6. Company interview scheduling system

## Running the Project
The project runs automatically on Replit. Access points:
- **Homepage**: Main domain (student-facing)
- **Student Login**: /student/login
- **Company Portal**: /company/login
- **Admin Panel**: /admin/login

## Development Notes
- All admin actions are logged in the audit_logs table
- Student profiles require admin approval before being featured
- File uploads are optimized (images thumbnailed to 500x500px)
- CSRF protection enabled on all forms
- Session-based authentication with Flask-Login
- Multi-user architecture with separate models for User (students/admins) and Company
- Role attribute guards implemented to prevent AttributeError across user types
- session['user_type'] tracks authentication type (student/company/admin)
