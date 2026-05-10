# Fullstack E-Commerce App

A complete **full-stack e-commerce application** with a .NET Core backend API and Angular frontend — featuring product browsing, basket management, order checkout, and user authentication.

## Tech Stack

**Backend:** ASP.NET Core Web API, Entity Framework Core (SQL Server), ASP.NET Identity + JWT, Redis (basket), AutoMapper, Swagger

**Frontend:** Angular

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

1. Configure SQL Server connection string, JWT secret, and Redis in `appsettings.json`.
2. Apply migrations:
   ```bash
   dotnet ef database update --context StoreContext
   dotnet ef database update --context AppIdentityDbContext
   ```
3. Run the API (auto-seeds on first run): `dotnet run --project API`
4. Start Angular: `cd client && npm install && ng serve`
