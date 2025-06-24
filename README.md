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




