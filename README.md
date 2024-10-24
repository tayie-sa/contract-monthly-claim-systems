# Contract Monthly Claim System (CMCS)

## Overview
The **Contract Monthly Claim System (CMCS)** is a web-based application developed using **C#** and the **MVC pattern** in **.NET Core**. It helps manage and automate the monthly claim submissions for contracts, allowing contractors to  submit claims, view history, and track payment statuses.

## Features
- **User Authentication**: Secure login system with role-based access (Admin, Contractor, and Manager).
- **Contractor Dashboard**: Contractors can submit monthly claims and view claim history.
- **Manager Dashboard**: Managers can approve or reject claims.
- **Admin Panel**: Admin users can manage users, contracts, and view overall claim statistics.
- **Email Notifications**: Automatic notifications when claims are submitted, approved,  or rejected.
- **Responsive UI**: User-friendly  interface that works on both desktop and mobile devices.
- **Reports**: Generate PDF or Excel reports on contract claims.

## Technologies Used
- **.NET Core**: Framework for building the backend.
- **C#**: Programming language for the application logic.
- **ASP.NET Core MVC**: For building the Model-View-Controller architecture.
- **Entity Framework Core**: ORM for database management.
- **SQL Server**: Database to store user and claim data.
- **Bootstrap**: Front-end framework for responsive design.
- **Identity Framework**: For authentication and authorization.

## Prerequisites
Before you begin, ensure you have the following installed:
- **.NET Core SDK**: Version 3.1 or later.
- **SQL Server**: Local or cloud-based database.
- **Visual Studio**: Version 2019 or later (or Visual Studio Code).

## Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/CMCS.git
cd  CMCS
```

### 2. Setup Database Connection
1. Open the `appsettings.json` file.
2. Modify the `ConnectionStrings` section to point to your SQL Server instance.
```json
"ConnectionStrings": {
    "DefaultConnection": "Server=your_server_name;Database=CMCSDB;Trusted_Connection=True;"
}
```

### 3. Migrate the Database
To set up the database schema, run the following commands:
```bash
dotnet ef migrations add InitialCreate
dotnet ef database update
```

### 4. Run the Application
Once the database is set up, you can start the application using the following command:
```bash
dotnet run
```


### 5. Access the Application
Open your browser and navigate to `http://localhost:5000` to view the application.

## Project Structure
The application follows the **MVC** design pattern:
- **Models**: Represents the application's data and business logic.
  - Example: `Claim.cs`, `Contract.cs`, `User.cs`
- **Views**: The user interface of the application.
  - Example: `Views/Claim/Index.cshtml`, `Views/Contractor/Dashboard.cshtml`
- **Controllers**: Handles user interaction, updates the model, and returns views.
  - Example: `ClaimController.cs`, `ContractorController.cs`

## Key Components
- **Authentication**: Uses ASP.NET Core Identity for secure user authentication.
- **Authorization**: Role-based authorization with three roles: Admin, Manager, and Contractor.
- **Error Handling**: Custom error pages for 404 and 500 errors.
- **Validation**: Server-side validation using Data Annotations for form inputs.

## Development Notes
- **Seeding Data**: The application seeds initial data such as admin users and default contracts. To reset and re-seed data, delete the database and re-run the migration.
- **Testing**: Unit tests can be written using xUnit or MSTest. To run tests:
```bash
dotnet test
```

## Future Enhancements
- **API Integration**: Future plans include developing an API for external contract management systems to submit claims directly.
- **Payment Integration**: Integration with a payment gateway to track claim payments.
- **Customizable Roles**: Allow users to define custom roles and permissions.

## Contributing
Contributions are welcome! Please follow these steps:
1. Fork the project.
2. Create your feature branch (`git checkout -b feature/your-feature-name`).
3. Commit your changes (`git commit -m 'Add some feature'`).
4. Push to the branch (`git push origin feature/your-feature-name`).
5. Open a Pull Request.
