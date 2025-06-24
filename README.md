# airbnb-clone-project
AirBnB Clone project.

## Team Roles

- **Backend Developer**  
  Builds and maintains the server-side logic (e.g. Django views, REST/GraphQL APIs), ensures high performance and responsiveness.

- **Frontend Developer**  
  Implements user interfaces (e.g. React components), connects to backend services, and ensures an intuitive UX.

- **Database Administrator**  
  Designs and optimizes the database schema (e.g. PostgreSQL), manages migrations, backups, and performance tuning.

- **DevOps Engineer**  
  Automates deployment pipelines (e.g. Docker, AWS), configures CI/CD, and monitors production health.

- **QA Engineer**  
  Writes and executes test plans (unit, integration, end-to-end), reports bugs, and ensures release quality.

- **Project Manager**  
  Coordinates the team, manages timelines, tracks scope, and liaises with stakeholders to keep the project on track.

## Technology Stack

- **Django**  
  Python web framework for building our backend APIs, authentication, and admin interface.

- **PostgreSQL**  
  Relational database for storing all application data with ACID guarantees.

- **GraphQL**  
  Flexible query language allowing clients to request exactly the data they need from our API.

- **React**  
  Frontend library for building interactive user interfaces and single-page app routing.

- **Docker**  
  Containerization to package our app and dependencies for consistent dev/prod environments.

- **GitHub Actions**  
  Automates testing and deployment workflows on every push or pull request.

- **AWS (EC2, RDS, S3)**  
  Hosts our application servers (EC2), managed database (RDS), and static/media assets (S3).

  ## Database Design

### Entities & Fields

- **Users**  
  - `id` (PK)  
  - `name`  
  - `email` (unique)  
  - `password_hash`  
  - `role` (e.g. guest, host, admin)

- **Properties**  
  - `id` (PK)  
  - `owner_id` (FK → Users.id)  
  - `title`  
  - `description`  
  - `location`  
  - `price_per_night`

- **Bookings**  
  - `id` (PK)  
  - `user_id` (FK → Users.id)  
  - `property_id` (FK → Properties.id)  
  - `start_date`  
  - `end_date`  
  - `status` (e.g. pending, confirmed, cancelled)

- **Reviews**  
  - `id` (PK)  
  - `user_id` (FK → Users.id)  
  - `property_id` (FK → Properties.id)  
  - `rating` (1–5)  
  - `comment`  
  - `created_at`

- **Payments**  
  - `id` (PK)  
  - `booking_id` (FK → Bookings.id)  
  - `amount`  
  - `payment_method`  
  - `status` (e.g. paid, refunded)  
  - `paid_at`

### Relationships

- A **User** can own multiple **Properties**.  
- A **Property** can have many **Bookings**.  
- A **Booking** belongs to one **User** (the guest) and one **Property**.  
- Each **Booking** has one **Payment**.  
- A **User** can leave multiple **Reviews** on **Properties** they’ve booked.

## Feature Breakdown

- **User Management**  
  Allows users to sign up, log in, and manage their profile (guests and hosts). Includes email verification, password reset, and role-based access control to distinguish between guest, host, and admin actions.

- **Property Management**  
  Enables hosts to create, edit, and remove property listings with photos, descriptions, pricing, and availability calendars. Hosts can set house rules, amenities, and manage booking requests directly from their dashboard.

- **Booking System**  
  Lets guests search availability, create booking requests, and view their upcoming and past stays. Includes real-time availability checks, booking status updates (pending, confirmed, cancelled), and calendar integration for hosts and guests.

- **Review & Rating**  
  Permits guests to leave ratings and comments after a stay, and allows hosts to respond. Reviews help build trust within the community and inform future guests’ booking decisions.

- **Payment Processing**  
  Integrates with a payment gateway to handle secure transactions for booking payments, refunds, and payout schedules to hosts. Ensures PCI compliance and provides transaction history for both guests and hosts.

- **Search & Filtering**  
  Provides a robust search interface with filters for location, price range, dates, property type, and amenities. Improves user experience by helping guests quickly find listings that match their criteria.

- **Messaging System**  
  Facilitates in-app communication between guests and hosts for pre-booking inquiries, check-in details, and post-stay follow-ups. Supports notifications and message threading for clear conversation history.

- **Admin Dashboard**  
  Gives administrators an overview of platform metrics (users, listings, bookings, revenue), with tools to manage content, moderate users/reviews, and configure global settings.






