
# 📘 BlogPortal API

## Overview

The **BlogPortal API** is a backend application built using **ASP.NET Core**. It provides RESTful endpoints for managing:

- Announcements
- User Authentication
- Blogs and Blog Posts
- User Feedback

It leverages **Entity Framework Core**, **ASP.NET Identity**, **JWT Authentication**, and **Dependency Injection** to create a secure and scalable API.

---

## 🚀 Features

- 🔐 JWT-based user authentication
- 📢 Announcement management (admin and public views)
- 📝 Blog and blog post CRUD operations
- 💬 Feedback submission
- 📧 Email service integration
- 📄 Swagger UI for API documentation

---

## 🛠 Technologies Used

- ASP.NET Core
- Entity Framework Core
- ASP.NET Identity
- JWT Bearer Authentication
- SQL Server
- Swagger/OpenAPI
- SignalR (configured)
- CORS

---

## 📁 Project Structure

```
Controllers/
    AnnouncementsController.cs
    AuthenticationController.cs
    BlogController.cs
    BlogPostController.cs
    FeedbackController.cs
Data/
    ApplicationDbContext.cs
    SeedData.cs
Models/
    Announcement.cs
    ApplicationUser.cs
    Blog.cs
    BlogPost.cs
    Feedback.cs
Services/
    AuthService.cs
    EmailService.cs
    Interfaces/
        IAuthService.cs
        IEmailService.cs
Program.cs
appsettings.Development.json
appsettings.json
```

---

## 📂 Component Breakdown

### 🔧 Controllers

- **AnnouncementsController**: Admin CRUD + public view of active announcements.
- **AuthenticationController**: Handles registration, login, and JWT token generation.
- **BlogController**: Manages blog creation and updates.
- **BlogPostController**: Handles blog post operations.
- **FeedbackController**: Accepts and stores user feedback.

### 🧩 Models

- **Announcement**: Title, content, expiration.
- **ApplicationUser**: Extends IdentityUser with profile info.
- **Blog**: Blog metadata and user association.
- **BlogPost**: Post content, author, timestamps.
- **Feedback**: User-submitted feedback.

### 🗃 Data Access

- **ApplicationDbContext**: EF Core context with DbSets.
- **SeedData**: Role and user seeding logic.

### 🧰 Services

- **IAuthService / AuthService**: JWT-based authentication logic.
- **IEmailService / EmailService**: Email sending functionality (stubbed).

### ⚙ Configuration

- **appsettings.json / appsettings.Development.json**: Connection strings, JWT config.
- **Program.cs**: Service registration, middleware setup, Swagger, CORS, SignalR.

---

## 🧪 Setup Instructions

1. **Clone the repository**:
   ```bash
   git clone <repo-url>
   cd BlogPortal
   ```

2. **Configure the database**:
   Update `DefaultConnection` in `appsettings.Development.json`.

3. **Set JWT values**:
   Add `Jwt:Key`, `Jwt:Issuer`, and `Jwt:Audience` in config files.

4. **Run EF Core migrations**:
   ```bash
   dotnet ef database update
   ```

5. **Build and run the project**:
   ```bash
   dotnet build
   dotnet run
   ```

6. **Access Swagger UI**:
   Navigate to `https://localhost:<port>/swagger` to test endpoints.

---
