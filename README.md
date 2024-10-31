## Greetings!
This is Dentalism, a booking web application that I developed in about five days. The tech stack I used includes React.js, TypeScript, TailwindCSS, Tanstack, Webpack, and FullCalendar on the frontend, and Node.js with TypeScript on the backend.
For the database, I used the free MongoDB Atlas service.

## Application Flow
### 🟪 Landing Page
Users are greeted with a landing page where they can create an appointment by providing their email address, selecting a dentist, and choosing a date and time from the available slots. The availability of slots is determined by the dentist’s schedule. Users can book multiple appointments in a day, but not for the same time slot (e.g., 8:00–9:00, 10:00–11:00, 11:00–12:00, 13:00–14:00, etc.).

### 🟪 Booking Confirmation
Once the user clicks the "Make Reservation" button, they will receive an email from the Dentalism admin. I used Nodemailer with Gmail's SMTP to implement a passwordless login system. The email contains a link with a hash that validates with the server upon clicking. This action generates a JWT token for the user, which is tied to their email and unique ID. This token can be used for future appointments. One improvement I had in mind is to implement a cron job that invalidates old hashes to prevent reuse, but due to time constraints, I couldn’t add this feature.

### 🟪 Dashboard
Once logged in, users are directed to a dashboard that displays their upcoming appointments. Here, they can view, create, update, and cancel appointments. I used the FullCalendar package to display dates in a user-friendly way. The application also has route guards to protect certain routes. If users do not have a valid token stored in their cookies, they cannot access protected areas.

### 🔗 Video Demo
https://drive.google.com/file/d/1fcLPgwAlHTKWVepDM8pgE7sGhM6-Zqqi/view?usp=sharing
