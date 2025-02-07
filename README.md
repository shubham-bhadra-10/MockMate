# MockMate



### **1. Project Overview**
Your website will have the following features:
1. **User Authentication**: Users can sign up, log in, and manage their profiles.
2. **Slot Booking System**: Users can book slots for mock interviews.
3. **Random Pairing**: Users are randomly paired with each other for mock interviews.
4. **Online Coding Platform**: Users can select coding problems for their mock interviews.
5. **Compiler**: An integrated compiler for users to write and test code during the mock interview.
6. **Question Bank**: A repository of coding problems and interview questions.
7. **Interview Feedback**: Users can provide feedback to their peers after the mock interview.

---

### **2. Technology Stack**
- **Frontend**: React (with React Router for navigation, Axios for API calls)
- **Backend**: Spring Boot (REST APIs, Spring Security for authentication)
- **Database**: MySQL (for storing user data, interview slots, questions, etc.)
- **Compiler**: Use an existing compiler API (e.g., JDoodle, Judge0) or build a custom one.
- **Deployment**: AWS, Heroku, or any cloud platform.

---

### **3. Database Design**
Here’s a basic schema for your MySQL database:

#### **Tables**
1. **Users**
   - `user_id` (Primary Key)
   - `name`
   - `email`
   - `password` (hashed)
   - `role` (e.g., user, admin)

2. **Interview Slots**
   - `slot_id` (Primary Key)
   - `user_id` (Foreign Key)
   - `start_time`
   - `end_time`
   - `status` (e.g., booked, completed)

3. **Coding Problems**
   - `problem_id` (Primary Key)
   - `title`
   - `description`
   - `difficulty` (e.g., easy, medium, hard)
   - `tags` (e.g., array, string, dynamic programming)

4. **Mock Interviews**
   - `interview_id` (Primary Key)
   - `user1_id` (Foreign Key)
   - `user2_id` (Foreign Key)
   - `problem_id` (Foreign Key)
   - `start_time`
   - `end_time`
   - `feedback` (optional)

5. **Feedback**
   - `feedback_id` (Primary Key)
   - `interview_id` (Foreign Key)
   - `rating` (e.g., 1-5)
   - `comments`

---

### **4. Backend (Spring Boot)**
#### **APIs**
1. **User Authentication**
   - `POST /api/auth/signup` (User registration)
   - `POST /api/auth/login` (User login)

2. **Slot Booking**
   - `POST /api/slots/book` (Book a slot)
   - `GET /api/slots/available` (Get available slots)

3. **Random Pairing**
   - `POST /api/interviews/pair` (Pair users randomly for mock interviews)

4. **Coding Problems**
   - `GET /api/problems` (Get all problems)
   - `GET /api/problems/{id}` (Get a specific problem)

5. **Compiler**
   - `POST /api/compiler/run` (Execute code using a compiler API)

6. **Feedback**
   - `POST /api/feedback` (Submit feedback for a mock interview)

---

### **5. Frontend (React)**
#### **Pages**
1. **Home Page**
   - Overview of the website and its features.
   - Links to sign up, log in, and book slots.

2. **Sign Up / Log In**
   - Forms for user registration and login.

3. **Dashboard**
   - Display user profile information.
   - Show upcoming mock interviews.

4. **Slot Booking**
   - Calendar view to book available slots.

5. **Mock Interview**
   - Real-time interview interface with:
     - Video call integration (e.g., using WebRTC or a third-party API like Agora).
     - Coding problem selection.
     - Integrated compiler for writing and testing code.

6. **Feedback**
   - Form to submit feedback after the mock interview.

7. **Question Bank**
   - Browse and search coding problems by difficulty, tags, etc.

---

### **6. Compiler Integration**
- Use an existing compiler API like **JDoodle** or **Judge0** to execute code.
- Create a `POST` API in your backend to send code to the compiler API and return the output.

---

### **7. Random Pairing Algorithm**
- When a user books a slot, the backend should:
  1. Find another user who has booked a slot at the same time.
  2. Randomly pair the two users.
  3. Assign a coding problem to the pair.

---

### **8. Deployment**
- **Frontend**: Deploy your React app using Vercel, Netlify, or AWS S3.
- **Backend**: Deploy your Spring Boot app using AWS EC2, Heroku, or any cloud platform.
- **Database**: Use AWS RDS or any MySQL hosting service.

---

### **9. Timeline**
1. **Week 1-2**: Set up the project (React, Spring Boot, MySQL).
2. **Week 3-4**: Implement user authentication and slot booking.
3. **Week 5-6**: Build the random pairing system and integrate the compiler.
4. **Week 7-8**: Create the mock interview interface and feedback system.
5. **Week 9-10**: Test the application and deploy it.

---

### **10. Additional Features (Optional)**
- **Video Call Integration**: Use WebRTC or a third-party API like Agora for video calls during mock interviews.
- **Leaderboard**: Show top users based on feedback ratings.
- **AI-Powered Feedback**: Use AI to analyze mock interviews and provide automated feedback.

---

### **11. Tools and Libraries**
- **Frontend**: React, Axios, React Router, Material-UI or Tailwind CSS.
- **Backend**: Spring Boot, Spring Security, Spring Data JPA.
- **Database**: MySQL, Hibernate.
- **Compiler**: JDoodle API, Judge0 API.
- **Video Call**: WebRTC, Agora.

---

