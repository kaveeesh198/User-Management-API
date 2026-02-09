
User Management API

A User Management API built with Fastify, TypeScript, Prisma ORM, and PostgreSQL (Dockerized), providing full CRUD operations for users with a clean, scalable plugin-based architecture and Prisma-powered database migrations.

⸻

🚀 Tech Stack
	•	Fastify – High-performance Node.js framework
	•	TypeScript – Type-safe backend development
	•	PostgreSQL – Relational database
	•	Prisma ORM – Database modeling, migrations, and queries
	•	Docker & Docker Compose – Containerized PostgreSQL setup

⸻

✨ Features
	•	Create a user
	•	Get all users
	•	Get a single user by ID
	•	Update user details
	•	Delete a user
	•	PostgreSQL database with Prisma migrations
	•	Clean Fastify plugin-based structure
	•	Scalable and production-friendly architecture

⸻

📂 Project Structure

├── prisma/
│   ├── schema.prisma
│   └── migrations/
│
├── src/
│   ├── plugins/
│   │   └── prisma.ts
│   │
│   ├── modules/
│   │   └── user/
│   │       ├── user.routes.ts
│   │       ├── user.controller.ts
│   │       └── user.service.ts
│   │
│   ├── app.ts
│   └── server.ts
│
├── docker-compose.yml
├── .env
├── package.json
├── tsconfig.json
└── README.md


⸻

🐳 Database Setup (PostgreSQL with Docker)

Start the PostgreSQL database using Docker Compose:

docker-compose up -d

Make sure your .env file contains the database URL:

DATABASE_URL="postgresql://postgres:password@localhost:5432/user_management"


⸻

🧬 Prisma Setup

Generate Prisma client:

npx prisma generate

Run database migrations:

npx prisma migrate dev --name init

(Optional) Open Prisma Studio:

npx prisma studio


⸻

▶️ Running the Server

Install dependencies:

npm install

Start the development server:

npm run dev

The API will be available at:

http://localhost:3000


⸻

📡 API Endpoints

User Routes

Method	Endpoint	Description
POST	/users	Create a user
GET	/users	Get all users
GET	/users/:id	Get user by ID
PUT	/users/:id	Update user
DELETE	/users/:id	Delete user


⸻

🧪 Example User Model

User {
  id        Int      @id @default(autoincrement())
  email     String   @unique
  name      String
  createdAt DateTime @default(now())
}


⸻

🧱 Architecture Notes
	•	Modular structure for easy feature expansion
	•	Fastify plugins for shared services (Prisma, config, etc.)
	•	Separation of routes, controllers, and services
	•	Ready for authentication and authorization integration

⸻

📌 Future Improvements
	•	Authentication (JWT / Firebase Auth)
	•	Input validation (Zod / Yup)
	•	Role-based access control
	•	Pagination and filtering
	•	API documentation (Swagger / OpenAPI)

⸻

📝 License

This project is open-source and available for learning and portfolio use.

⸻
