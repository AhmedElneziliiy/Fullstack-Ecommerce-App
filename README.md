# Fullstack E-Commerce App

A complete **full-stack e-commerce application** with a .NET Core backend API and Angular frontend — featuring product browsing, basket management, order checkout, and user authentication.

## What it does

A production-style online store where users can browse products, add items to a Redis-backed basket, place orders, and manage their account. The API follows clean architecture with separate data and identity contexts.

## Tech Stack

**Backend**
- **ASP.NET Core Web API** (.NET)
- **Entity Framework Core** — SQL Server (product store) + separate identity DB
- **ASP.NET Identity** — JWT authentication
- **Redis** — basket/cart storage
- **AutoMapper**
- **Swagger / OpenAPI**

**Frontend**
- **Angular** — SPA with lazy-loaded modules

## Key Features

- Product catalog with filtering and sorting
- Redis-backed shopping basket (persists across sessions)
- Order creation with delivery address
- JWT authentication and user profile management
- Generic error handling middleware
- Seeded product and identity data on startup

## API Endpoints

| Controller | Responsibility |
|---|---|
| `ProductsController` | Browse and filter products |
| `BasketController` | Add/update/delete basket items |
| `OrdersController` | Create and retrieve orders |
| `AccountController` | Register, login, profile |

## Getting Started

1. Configure your SQL Server connection string, JWT secret, and Redis connection in `appsettings.json`.
2. Apply migrations:
   ```bash
   dotnet ef database update --context StoreContext
   dotnet ef database update --context AppIdentityDbContext
   ```
3. Run the API (auto-seeds data on first run):
   ```bash
   dotnet run --project API
   ```
4. Start the Angular client:
   ```bash
   cd client && npm install && ng serve
   ```
