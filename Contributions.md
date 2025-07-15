# Contributions

This document outlines my **technical** and **non-technical** contributions to the **PlanTopia graduation project**. From backend development and cloud integration to payment gateway setup and team collaboration, I played a key role in ensuring a robust and scalable solution.

---

## 📚 Table of Contents

- [Technical Contributions](#-technical-contributions)
  - [Deployment & Hosting](#-deployment--hosting)
  - [Backend System (ASP.NET Core)](#-backend-system-aspnet-core)
    - [Plant Controller](#-plant-controller)
    - [Task Controller](#-task-controller)
    - [User Operations](#user-operations)
    - [Favorites Feature](#-favorites-feature)
    - [Ordering System](#-ordering-system)
    - [AWS Integration](#-aws-integration)
    - [Stripe Payment Integration](#-stripe-payment-integration)
  - [Project Structure & Design Patterns](#-project-structure--design-patterns)
- [Non-Technical Contributions](#-non-technical-contributions)

---

## 💻 Technical Contributions

### 🌐 Deployment & Hosting

- Me and Mohmed Reyad were Responsible for **deploying and hosting** the entire web application using **Monster ASP.NET**.
  - Chose Monster ASP.NET as a reliable and free hosting option suitable for students.
  - Configured remote SQL database for cloud accessibility.

---

### ⚙ Backend System (ASP.NET Core)

#### 🌱 Plant Controller  
- Developed the **Plant Controller** to handle all plant-related operations.  
- Implemented endpoints for:  
  - **Adding new plants** with their details (name, description, price, etc.)  
  - **Updating existing plant data** such as stock, pricing, and status.  
  - **Retrieving plant lists** with filtering and searching options for better usability.  
  - **Deleting plants** while ensuring data consistency.  
- Integrated **AWS S3** for image upload, allowing plants to have associated images stored securely.  
- Ensured **clean DTOs** for request/response to avoid over-fetching unnecessary data.  

---

#### 👤 User Operations
- Developed APIs for:
  - **User registration & profile management**
  - Profile image upload (linked with AWS S3)
  - Proper role resolution for Customers/Admins/Workers.

---

#### ✅ Task Controller  
- Contributed to the **Task Controller** that manages nursery worker tasks.  
- Helped in implementing:  
  - **Creating and assigning tasks** (watering, pruning, maintenance) to workers.  
  - **Retrieving daily/weekly tasks** for individual workers.  
  - **Updating task status** (Pending → In Progress → Completed).  
  - **Deleting or reassigning tasks** when needed.  
- Ensured **role-based access** so only Admins can assign or modify worker tasks.  
- Assisted in connecting **Task Controller** with the **Worker module**, ensuring seamless linking of tasks to specific workers.  

---

#### ⭐ Favorites Feature
- Designed the **Favorite Items service**:
  - Customers can add/remove plants from their favorites list.
  - Exposed lightweight endpoints requiring only plant ID for quick actions.

---

#### 🛒 Ordering System
- Created **Cart & Order services**:
  - Add/view/update cart items
  - Place orders, move cart items to orders
  - Allow cancellation only for pending orders
  - Updated order status workflow for better tracking (e.g., ORDERED → PROCESSING → DELIVERED)

---

#### ☁ AWS Integration
- Integrated **AWS S3** for storing:
  - **Plant images**  
  - **User profile images**  
- Wrote reusable upload logic with robust error handling and S3 path management.

---

#### 💳 Stripe Payment Integration
- Configured **Stripe payment gateway** to handle secure payments.
  - Created payment sessions with dynamic order data.
  - Used **Stripe webhooks** to confirm successful payments.
  - Implemented failed-card handling and proper rollback logic.

---

## 🏗 Project Structure & Design Patterns

To ensure **scalability**, **maintainability**, and **testability**, our backend was designed using a **clean layered architecture**.  

We adopted a **Service-Repository pattern with Unit of Work**, enforcing a clear **separation of concerns** and keeping the codebase modular and robust.

---

### 🔄 **Design Patterns Used**
- **Layered Architecture** → Clear division between API, Service, and Data layers.
- **Repository Pattern** → Encapsulates database access, making it reusable.
- **Unit of Work Pattern** → Groups multiple repository actions into a single transaction.
- **DTO Pattern** → Ensures API requests/responses are clean and structured.

---

### 📂 **Solution Structure**

PlanTopia Solution
│
├── Api                                # Entry point of the application
│   ├── Controllers                    # HTTP endpoints to handle requests
│   ├── Dtos                           # Data Transfer Objects for request/response shaping
│   ├── Migrations                     # EF Core migrations history
│   ├── Services                       # Business logic, separated by domain
│   │   ├── AdminServices
│   │   ├── AuthService
│   │   ├── AwsS3Service
│   │   ├── CartService
│   │   ├── CustomerServices
│   │   ├── FavoriteItemService
│   │   ├── InvoiceService
│   │   ├── MLModelService
│   │   ├── OrderService
│   │   ├── PaymentService
│   │   ├── PlantService
│   │   ├── TaskService
│   │   └── WorkerServices
│   ├── appsettings.json              # App configuration (connection strings, tokens, etc.)
│   ├── Plantopia.http                # HTTP request collections (for testing APIs)
│   └── Program.cs                    # Main startup class
│
├── DAL                                # Data Access Layer
│   ├── Configuration                  # Entity configurations (Fluent API)
│   ├── Data                           # DbContext and seed logic
│   └── Repository                     # Repository pattern implementation
│       ├── Interfaces                 # Repository contracts
│       └── Implementations           # Repository logic + UnitOfWork
│
├── Entities                           # Domain layer for models and shared types
│   ├── Enums                          # Enum types (e.g., Roles, Statuses)
│   ├── Interfaces                     # Shared logic or marker interfaces
│   └── Models                         # Core data models (User, Order, Plant, etc.)




---

### 🔄 **Repository & Unit of Work Structure**

DAL
│
└── Repository
├── Interfaces
│ ├── IGenericRepository.cs
│ ├── IOrderRepository.cs
│ └── IUnitOfWork.cs
└── Implementations
├── GenericRepository.cs
├── OrderRepository.cs
└── UnitOfWork.cs


✅ **Why this matters:**
- Makes the system **easy to maintain** and extend.
- Reduces code duplication through reusable components.
- Improves **testability** by abstracting database dependencies.
- Allows **atomic commits** across multiple repositories.

---

## 🙌 Non-Technical Contributions

### 1. From Real-World Needs to a Viable Project Idea
The journey began with a simple but insightful conversation. One of our team members, Abdelrahman Amer, had real-world experience working in a nursery. We quickly realized this space was full of inefficiencies and unaddressed needs — from poor task assignment to the absence of disease monitoring tools. After several discussions, we concluded that building a nursery management system with intelligent features would be both practical and meaningful. That was the seed of what became **PlanTopia**.

---

### 2. Leading the Backend Team
I helped the leader"Mohamed Reyad" in the **backend development team**, ensuring our work was well-organized and aligned with the overall system architecture. My responsibility wasn’t limited to dividing tasks — it included:
- Assigning roles based on each team member’s strengths and interests.
- Monitoring progress to ensure deadlines and technical quality were met.
- Explaining tasks in detail so everyone understood *why* and *how* a component fits into the larger system.

---

### 3. Supporting Team Members When It Mattered
When teammates struggled with tasks or time constraints, I stepped in to:
- Help debug issues and guide them step by step.
- Or take ownership of the task myself, ensuring we didn’t fall behind.

---

### 4. Maintaining Team Energy & Momentum
I often reminded the team of our goals and progress, keeping morale high and momentum strong through regular check-ins.

---

### 5. Coordinating Across Technical Tracks
Bridged the gap between **backend, frontend, and AWS services** to ensure seamless integration.

---

### 6. Learning & Growing Together
Encouraged **knowledge sharing**, shared tutorials, code snippets, and collaborative problem-solving.

---

This document reflects both the **code-level impact** I had on the project as well as my role in enabling a smooth, collaborative team journey.
