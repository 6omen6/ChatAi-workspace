# ChatAI - Conversational AI Prototype

This project is a prototype of a conversational AI chatbot application with real-time## Running the Application

### Option 1: Running backend and frontend separately

1. Start the backend:
```
cd backend
dotnet run
```

2. Start the frontend:
```
cd web
npm start
```

### Option 2: Using Visual Studio Code Tasks and Run & Debug

The project includes predefined tasks in Visual Studio Code that can be used to build and run the application:

1. Press `Ctrl+Shift+B` to see available build tasks
2. Select one of the available tasks:
   - `build` - Builds the backend project
   - `watch` - Runs the backend in watch mode for development
   - `clean` - Cleans the backend project
   - `publish` - Publishes the backend project

Alternatively, you can use the Run & Debug functionality in VS Code:

1. Open the Run & Debug panel (`Ctrl+Shift+D`)
2. Select the appropriate launch configuration
3. Press F5 or click the green play button to start debugging

All backend tasks can also be executed from the Terminal menu in VS Code (Terminal → Run Task...).

### Option 3: Building for productionses and a feedback system. The application is built using .NET 6 for the backend API and Angular for the frontend.

## Project Structure

The project consists of two main parts:

1. **Backend** - ASP.NET Core Web API with Entity Framework Core
2. **Frontend** - Angular application with Angular Material UI components

## Features

- 💬 Real-time chat interface
- ⚡ Streaming AI responses with Server-Sent Events (SSE)
- 👍👎 Feedback system for rating AI responses
- 🧵 Support for conversation threads
- ⏹️ Ability to cancel AI response generation
- 📱 Responsive design

## Technologies Used

### Backend
- ASP.NET Core 6.0
- Entity Framework Core 6.0
- MediatR (CQRS pattern implementation)
- FluentValidation
- SQL Server (LocalDB)
- Swagger/OpenAPI

### Frontend
- Angular 20.3.0
- Angular Material 20.2.2
- RxJS
- TypeScript

## Prerequisites

- .NET 6.0 SDK
- Node.js (v16+) and npm
- SQL Server LocalDB or SQL Server instance
- Visual Studio 2022, Visual Studio Code, or any preferred IDE

## Setup and Installation

### Database Setup

1. The project uses Entity Framework Core with Code First approach
2. Database connection string is configured in `backend/appsettings.json`
3. The application will create the database on first run if it doesn't exist

### Backend Setup

1. Navigate to the backend folder:
```
cd backend
```

2. Restore NuGet packages:
```
dotnet restore
```

3. Update the database with the latest migrations:
```
dotnet ef database update
```

4. Build the project:
```
dotnet build
```

5. Run the API:
```
dotnet run
```

The API will be available at:
- HTTPS: https://localhost:7050
- HTTP: http://localhost:5083
- Swagger documentation: https://localhost:7050/swagger

### Frontend Setup

1. Navigate to the web folder:
```
cd web
```

2. Install npm packages:
```
npm install
```

3. Start the Angular development server:
```
npm start
```

The frontend application will be available at http://localhost:4200

## API Configuration

The backend API can be configured through the `appsettings.json` file:

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=(localdb)\\MSSQLLocalDB;Database=ChatAiDb;Trusted_Connection=True;MultipleActiveResultSets=true"
  },
  "AIServiceOptions": {
    "Provider": "Mock",
    "ApiKey": "your-api-key",
    "Endpoint": "https://api.openai.com/v1",
    "DeploymentOrModelName": "gpt-3.5-turbo",
    "MaxTokens": 2000,
    "Temperature": 0.7,
    "MaxHistoryMessages": 10,
    "UseMockAI": false
  }
}
```

- To use a mock AI service, set `UseMockAI` to `true`
- To use a real AI service (e.g., OpenAI), update the API key and other settings
- **Important**: Never commit real API keys to the repository. Use the template file `appsettings.template.json` as a reference and store your actual keys in `appsettings.Development.json` which is excluded from git

## Running the Application

### Option 1: Running backend and frontend separately

1. Start the backend:
```
cd backend
dotnet run
```

2. Start the frontend:
```
cd web
npm start
```

### Option 2: Using Visual Studio Code .NET Core Launch

You can run the backend directly from Visual Studio Code using the built-in .NET Core Launch functionality:

1. Open the Run and Debug panel in VS Code (Ctrl+Shift+D or click the play button with bug icon in the sidebar)
2. Select ".NET Core Launch (web)" from the dropdown menu at the top
3. Click the green play button or press F5 to start the backend with debugging
4. The backend will start and automatically open a browser window to the Swagger UI

This method allows you to set breakpoints, inspect variables, and debug your application in real-time. You can see all available breakpoint configurations in the Debug panel, including options for "All Exceptions" and "User-Unhandled Exceptions".

### Option 3: Building for production -> to do

## Project Architecture

### Backend Architecture

The backend follows Clean Architecture principles with:

- **Controllers** - Handle HTTP requests and responses
- **Features** - Organized by domain with Commands and Queries (CQRS)
- **Services** - Business logic implementation
- **Repositories** - Data access layer
- **Models** - Domain entities
- **Migrations** - Database schema changes

### API Endpoints

- `GET /api/threads` - Get all conversation threads
- `GET /api/threads/{id}` - Get a specific thread
- `POST /api/threads` - Create a new thread
- `GET /api/messages/{threadId}` - Get messages for a thread
- `POST /api/messages` - Send a new message
- `POST /api/rating` - Rate a message
- `GET /api/streaming/{threadId}` - Stream AI responses (SSE)

## Testing

1. Backend unit tests -> to do
2. Frontend unit tests -> to do

## Contributors

This project was developed as a prototype for an AI chatbot application.

## License

This project is proprietary and confidential.
