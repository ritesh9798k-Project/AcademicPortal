# Academic Chatbot Portal — Local Setup

This project is the Academic Portal scaffold using plain ADO.NET for data access and a floating chatbot widget.

Quick start

1. Restore and build the solution in Visual Studio (target .NET 8 / .NET Core as the project indicates).
2. Run the SQL script `SQL/init_schema.sql` against your SQL Server instance to create schema and seed data.
3. Ensure the connection string named `DatabaseConnection` is present in `Web.config` and points to your SQL Server. Example already present in repository.
4. Start the web project and open `https://localhost:{port}/Account/Login`.
5. Login with seeded admin (if present) or create a user record in the `Users` table.

Notes
- All database access is implemented in `Services/DataAccessService.cs` using parameterized SQL. No Entity Framework is used.
- The floating chatbot widget posts messages to `/Chatbot/SendMessage` and performs a simple search against the `Policies` table.
