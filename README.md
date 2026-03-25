🚗 AutoBrain AI Management System

AutoBrain AI is a modern, full-stack management system designed for auto parts businesses. It integrates inventory, POS, CRM, suppliers, service management, analytics, and AI assistance into one unified platform.

Built with Spring Boot + React, AutoBrain runs locally, giving you full control over your data — fast, secure, and scalable.

🏗️ Architecture Design
🔷 High-Level Architecture
🔷 Layered Architecture (Backend)

AutoBrain follows a clean layered architecture to ensure maintainability and scalability:

1. Controller Layer
Handles HTTP requests & responses
Exposes REST APIs
Validates input data
2. Service Layer
Contains business logic
Coordinates workflows (orders, stock updates, etc.)
Communicates with AI layer
3. Repository Layer
Data access abstraction using Spring Data JPA
Handles CRUD operations
Optimized queries
🔷 Modular System Design

The backend is organized into feature-based modules:

/modules
 ├── auth
 ├── inventory
 ├── orders
 ├── crm
 ├── suppliers
 ├── service
 ├── analytics
 └── ai

Each module follows:

Controller
Service
Repository
Entity
DTO

➡️ This ensures low coupling and high cohesion

🔷 Data Flow
🔷 Key Architecture Principles
Separation of Concerns → Clear boundaries between layers
Scalability → Modular backend & independent services
Security → JWT-based authentication & stateless APIs
Extensibility → Easy to plug in new modules or AI features
Performance → Optimized DB queries & lightweight frontend
🌟 Core Features
📦 Inventory Management
Full CRUD for auto parts
Stock tracking & adjustments
Barcode & QR code generation
Product image upload
Advanced filtering & search
💳 Point of Sale (POS)
Fast checkout system
Barcode scanner integration
Cart & real-time pricing
Invoice generation
Automatic stock updates
🚗 Car Part Finder
Manual vehicle selection
VIN-based lookup
Compatible parts filtering
👥 CRM & Suppliers
Customer profiles & purchase history
Supplier management
Purchase orders
🔧 Service & Repair
Work orders
Appointment scheduling
Repair status tracking
🤖 AI Assistant
Chat powered by Groq API
Real-time database insights
Business analytics support
📊 Analytics Dashboard
Revenue tracking
KPIs & charts
Actionable business insights
📱 Mobile Scanner App

AutoBrain includes a dedicated Flutter mobile application for warehouse and shop workers.

🔍 Features
📷 Barcode & QR code scanning
📦 Instant product lookup via SKU
🛒 Create orders directly from scans
📉 Real-time stock adjustments
📊 Mobile KPI dashboard
🔐 JWT-based authentication
⚙️ Tech Stack (Mobile)
Flutter (Dart)
mobile_scanner
http (API calls)
intl
🛠️ Tech Stack
Frontend
React 18 + TypeScript
Vite
Tailwind CSS + Radix UI
Axios
Recharts
Backend
Spring Boot 3
Java 17
Spring Security (JWT)
Spring Data JPA
Database
MySQL
AI
Groq API
📡 API Overview
Authentication
POST /api/auth/login
POST /api/auth/register
GET /api/auth/me
Inventory
GET /api/car-parts
PATCH /api/car-parts/{id}/stock
Orders
GET /api/orders
POST /api/orders
AI
POST /api/ai/chat
🚀 Getting Started
Prerequisites
Node.js 18+
Java 17+
MySQL or Docker
Flutter (for mobile app)
Run Backend
cd backend
./mvnw spring-boot:run
Run Frontend
npm install
npm run dev
Run Mobile App
flutter pub get
flutter run
🔐 Security
JWT-based authentication
Stateless API design
Secure token storage:
Web → localStorage
Mobile → memory
🗺️ Roadmap
Role-based access control (RBAC)
Advanced AI automation
Mobile UX improvements
Export reports (PDF/Excel)
Multi-tenant / multi-shop support
📌 Project Highlights
Full-stack + mobile ecosystem
Real-world business use case
AI-powered insights
Clean & modular architecture
Highly scalable design
📄 License

MIT License © 2026 Yassine Kalai Ezzar

If you want, I can take this even further and:

Add a microservices version (future scaling)
Add a DevOps / deployment architecture (Docker + CI/CD)
Or make it look like a top-tier GitHub project (badges, screenshots, etc.)
