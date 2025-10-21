# 🎓 College Management System

A full-stack **College Management System** for managing students, doctors, departments, subjects, quizzes, assignments, grades, and announcements.  
Supports **web, mobile, and desktop** platforms with a RESTful API backend.

---

## 📌 Project Overview

This system allows:  

- **Admins** to manage users, departments, subjects, and student registration codes.  
- **Doctors** to manage their subjects, quizzes, assignments, grades, and announcements.  
- **Students** to register using codes, view dashboards, track deadlines, and see grades & announcements.  

The project is designed to **enable parallel work**, so Backend, Frontend, and UI/UX teams can work simultaneously on different phases.

---

## 🛠 Tech Stack

### **Backend**
| Layer | Technology | Why |
|-------|------------|-----|
| Runtime | Node.js | Fast, scalable, event-driven |
| Framework | Express.js | Minimal, modular, REST API support |
| Database | MySQL | Structured relational data, supports relationships |
| ORM / Query Builder | Prisma | Simplifies queries, migrations, type-safe |
| Authentication | JWT | Stateless, secure, works across web & mobile |
| Password Hashing | bcrypt | Industry-standard secure password storage |
| Validation | Joi / Zod | Input validation |
| Environment | dotenv | Secure management of secrets |
| Testing | Postman / Thunder Client | API testing |
| Dev Tools | nodemon | Auto-restart server on code changes |

### **Frontend**
| Platform | Framework | Why |
|----------|-----------|-----|
| Web | React | Component-based, reusable UI, fast development |
| Mobile | Flutter | Cross-platform, single codebase, fast UI building |
| Desktop (optional) | Electron.js | Reuse React components, create desktop admin panel |
  

---

## 👥 Detailed User Stories

### **Admin**
1. **Generate Student Registration Codes**  
   - Create single/multiple codes  
   - Track code status: used / unused  
   - Delete codes if needed  

2. **Manage Departments**  
   - Create, edit, delete departments  
   - View all departments  

3. **Manage Subjects**  
   - Create, edit, delete subjects  
   - Assign doctor & department  
   - View all subjects  

4. **Manage Users**  
   - View all users (students/doctors)  
   - Edit users: name, email, role, department, password  
   - Suspend/reactivate accounts  
   - Delete users  

---

### **Doctor**
1. View assigned subjects & enrolled students  
2. Create, edit, delete quizzes and assignments  
3. Enter and update grades  
4. Post, edit, delete announcements  
5. Optional: real-time notifications  

---

### **Student**
1. Register using code  
2. Login (JWT authentication, role-based access)  
3. View dashboard: subjects, deadlines, quizzes, grades, announcements  
4. View quizzes and deadlines per subject  
5. View announcements and mark read/unread  

---

## 🗂 Project Phases & Roles

Each phase is **small, actionable, and aligned across Backend, Frontend, and UI/UX teams**.

---

### **Phase 1: Project Setup & Environment**
**Goal:** Establish basic structure for backend and frontend projects and initial UI wireframes.

**Backend Dev**
- Initialize Node.js + Express project  
- Setup Prisma + MySQL connection  
- Setup folder structure: `controllers/`, `routes/`, `models/`, `services/`, `middlewares/`  
- Create test route `/health`  
- Install dev packages: nodemon, bcrypt, jsonwebtoken, joi, dotenv  

**Frontend Dev**
- Initialize React & Flutter projects  
- Setup basic routing and navigation  
- Create placeholder dashboard pages (Admin, Doctor, Student)  

**UI/UX Designer**
- Create wireframes for login, registration, and dashboard pages  
- Define color palette, fonts, spacing, and button styles  

**End Goal:**  
- Backend server running & connected to DB  
- Frontend skeleton ready  
- UI/UX wireframes finalized  

---

### **Phase 2: Database Design & Modeling**
**Goal:** Design database schema and integrate with backend ORM.

**Backend Dev**
- Design tables: `User`, `Department`, `Subject`, `RegistrationCode`, `Quiz`, `Assignment`, `Deadline`, `Grade`, `Announcement`  
- Define relationships (foreign keys, many-to-many)  
- Seed admin user  
- Run Prisma migrations  

**Frontend Dev**
- Build UI pages with placeholder data  
- Setup forms for login/registration  
- Setup tables for users, subjects, registration codes  

**UI/UX Designer**
- Finalize design for forms and tables  
- Define responsive layout rules for web & mobile  

**End Goal:**  
- Database ready  
- Mock frontend UI functional  
- UI/UX designs approved  

---

### **Phase 3: Authentication**
**Goal:** Enable registration and login for all roles.

**Backend Dev**
- `/auth/register` endpoint with registration code validation  
- `/auth/login` endpoint (JWT-based)  
- Middleware for auth & role-based route access  
- Password hashing with bcrypt  
- Input validation using Joi  

**Frontend Dev**
- Student registration form connected to backend  
- Login form for all roles  
- Store JWT token (web: localStorage, mobile: secure storage)  
- Redirect users to correct dashboard  

**UI/UX Designer**
- Style login & registration forms  
- Add error messages, validation feedback  

**End Goal:**  
- Users can register & login  
- Role-based access implemented  

---

### **Phase 4: Admin Module**
**Goal:** Allow admin to manage codes, departments, subjects, and users.

**Backend Dev**
- CRUD endpoints for registration codes  
- CRUD endpoints for departments and subjects  
- CRUD endpoints for users (view, edit, suspend/reactivate, delete)  

**Frontend Dev**
- Build admin dashboard tables & forms  
- Connect forms to backend endpoints  
- Enable dynamic updates after operations  

**UI/UX Designer**
- Design tables, forms, modals, and buttons for dashboard  
- Ensure responsive design and usability  

**End Goal:**  
- Admin can fully manage all system entities  
- Frontend displays dynamic, interactive data  

---

### **Phase 5: Doctor Module**
**Goal:** Allow doctors to manage quizzes, assignments, grades, and announcements.

**Backend Dev**
- CRUD endpoints for quizzes and assignments  
- Enter/update grades  
- CRUD endpoints for announcements  
- Fetch students per subject  

**Frontend Dev**
- Build doctor dashboard with forms & tables  
- Connect API for quizzes, assignments, grades, and announcements  

**UI/UX Designer**
- Design doctor dashboard layout and forms  
- Highlight priority actions (grade input, deadline updates)  

**End Goal:**  
- Doctor can manage all academic content for subjects  
- Frontend dashboard functional  

---

### **Phase 6: Student Module**
**Goal:** Students can see dashboard with subjects, deadlines, quizzes, grades, and announcements.

**Backend Dev**
- Endpoints for dashboard data: subjects, deadlines, quizzes, grades, announcements  

**Frontend Dev**
- Build student dashboard (web + mobile)  
- Connect API endpoints for live data  
- Show deadlines, grades, quizzes per subject  

**UI/UX Designer**
- Design student dashboard for clarity  
- Highlight deadlines and grades visually  

**End Goal:**  
- Students see live academic info on web & mobile  

---

### **Phase 7: Real-Time Features (Optional)**
**Goal:** Implement live updates for announcements & chat.

**Backend Dev**
- Socket.io server for announcements & chat  
- Store messages in DB  

**Frontend Dev**
- Implement real-time updates in React & Flutter  
- Update UI dynamically when new announcements/messages arrive  

**UI/UX Designer**
- Design real-time notification alerts and chat UI  
- Visual cues for unread/read items  

**End Goal:**  
- Real-time announcements and chat working on web & mobile  

---

### **Phase 8: Deployment**
**Goal:** Deploy full system online for demo or production.

**Backend Dev**
- Prepare production-ready server  
- Deploy backend (Render/Railway/AWS)  

**Frontend Dev**
- Deploy React app (Vercel/Netlify)  
- Build Flutter mobile app (Play Store / App Store)  

**UI/UX Designer**
- Review final UI/UX across platforms  
- Ensure consistent branding & usability  

**End Goal:**  
- Full system deployed, fully functional, ready for demo  

---

