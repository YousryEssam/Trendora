# 🛍️ Trendora - Modern E-Commerce Web Application

**Trendora** is a fully-featured modern e-commerce web application built using **ASP.NET Core (.NET 8)** and **Entity Framework Core**. It follows clean architecture principles, promoting scalability, maintainability, and modular design. [Main Repo Link](https://github.com/SantyOsama/Trendora) 

---

## 📑 Table of Contents

- [🎯 Purpose](#-purpose)
- [🏗️ High-Level Architecture](#-high-level-architecture)
- [🛠️ Core Technology Stack](#-core-technology-stack)
- [🔐 Authentication & Authorization](#-authentication--authorization)
- [📦 Main Features](#-main-features)
- [🧩 Data Model Overview](#-data-model-overview)
- [⚙️ Application Configuration](#️-application-configuration)
- [📁 Project Structure](#-project-structure)



---

## 🎯 Purpose

Trendora aims to deliver a complete and scalable e-commerce platform with essential features such as:

- User authentication and role-based authorization
- Product catalog management
- Shopping cart system
- Order lifecycle management
- Wishlist and product reviews

It is built with a layered architecture and utilizes well-known design patterns to ensure clean code and extensibility.

---

## 🏗️ High-Level Architecture

Trendora is structured into several layers:

- **Client Applications** – (e.g., Web front-end or Postman)
- **API Layer** – Handles HTTP requests and routes them to appropriate services
- **Business Logic Layer** – Contains application logic and use cases
- **Data Access Layer** – Implements repositories and Unit of Work
- **Database Layer** – SQL Server with EF Core and Identity integration

📊 **Architecture Diagram**  
Client App
↓
API Controllers
↓
Services / Managers (Business Logic)
↓
Repositories / Unit of Work (Data Access)
↓
EF Core / DbContext
↓
SQL Server

---

## 🛠️ Core Technology Stack

| Component            | Technology                  |
|---------------------|-----------------------------|
| Framework           | ASP.NET Core (.NET 8.0)     |
| Database            | SQL Server                  |
| ORM                 | Entity Framework Core       |
| Authentication      | JWT                         |
| Identity Management | ASP.NET Core Identity       |
| API Docs            | Swagger / OpenAPI           |
| Object Mapping      | DTOs                        |
| Data Patterns       | Repository + Unit of Work   |

---

## 🔐 Authentication & Authorization

Trendora uses **JWT-based authentication** with **ASP.NET Core Identity**. It supports role-based access for:

- **Admin**
- **User**
- **Trader**

### 🔁 Authentication Flow:

1. User registers or logs in with credentials.
2. Credentials are validated using Identity.
3. JWT token is generated and returned.
4. Token is used for authenticated API access.

🔐 DTOs:  
- `RegisterDTO.cs`  
- `LoginDTO.cs`

---

## 📦 Main Features

- 🛍️ **Product Catalog** – Browse, search, and manage products and categories.
- 🛒 **Shopping Cart** – Add/update/remove items and manage session cart.
- 📦 **Order Management** – Checkout flow, order items, and order history.
- 💖 **Wishlist System** – Save products for later.
- 🌟 **Product Reviews** – Users can review and rate products.

---

## 🧩 Data Model Overview

Key entities include:

- `ApplicationUser`
- `Product`, `Category`
- `Cart`, `CartItem`
- `Order`, `OrderItem`
- `Wishlist`, `WishlistItem`
- `Address`, `ProductReview`

📘 Defined in:  
- `Models/`  
- `Data/TrendOraDbContext.cs`

---

## ⚙️ Application Configuration

Trendora's configuration is managed through standard ASP.NET Core mechanisms:

Connection Strings: Database connection is configured in appsettings.json
JWT Settings: JWT token issuer, audience, and security key are defined in configuration
Dependency Injection: Services are registered in the Program.cs startup code
Middleware Pipeline: HTTP request processing pipeline is configured with standard middleware

## 📁 Project Structure

```bash
Trendora/
│
├── Controllers/          # API Controllers
├── DTOs/                 # Data Transfer Objects
├── Models/               # Entity Models
├── Data/                 # DbContext & EF Configuration
├── GenericRepositories/  # IRepository, UnitOfWork, GenericRepo
├── Services/             # Business Logic
├── Program.cs            # App Startup
├── appsettings.json      # Configuration
└── Trendora.csproj       # Project File

---

