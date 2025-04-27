# Deployment Guide for BuildTrack SmartSite Management System

This guide provides step-by-step instructions for deploying the BuildTrack SmartSite Management System in various environments.

## Prerequisites

- Node.js (v16 or later)
- npm (v7 or later)
- PostgreSQL database

## Local Development Deployment

1. Clone the repository:
   ```
   git clone <repository-url>
   cd buildtrack-smartsite
   ```

2. Install dependencies:
   ```
   npm install
   ```

3. Set up environment variables:
   Create a `.env` file in the project root with:
   ```
   DATABASE_URL=postgresql://username:password@hostname:port/database
   ```

4. Initialize the database:
   ```
   npm run db:push
   ```

5. Start the application in development mode:
   ```
   npm run dev
   ```

6. Access the application at `http://localhost:5000`

## Production Deployment

### Preparing for Production

1. Build the frontend:
   ```
   npm run build
   ```

2. Set up a production database:
   Ensure your PostgreSQL database is properly configured for production use with appropriate security measures.

3. Configure environment variables:
   Set the following environment variables in your production environment:
   ```
   NODE_ENV=production
   DATABASE_URL=postgresql://username:password@hostname:port/database
   ```

### Deployment Options

#### Option 1: Traditional Server

1. Transfer the built project to your server
2. Install dependencies:
   ```
   npm install --production
   ```
3. Start the application:
   ```
   npm start
   ```

#### Option 2: Docker Deployment

1. Build the Docker image:
   ```
   docker build -t buildtrack-smartsite .
   ```
2. Run the container:
   ```
   docker run -d -p 5000:5000 --env-file .env buildtrack-smartsite
   ```

#### Option 3: Platform as a Service (PaaS)

The application can be deployed to platforms like Heroku, Render, or Railway:

1. Connect your repository to the platform
2. Configure the environment variables
3. Deploy using the platform's deployment process

## Database Migration in Production

When updating your application with schema changes:

1. Test migrations locally first
2. Back up your production database
3. Run migrations in production:
   ```
   npm run db:push
   ```

## Troubleshooting

- **Database Connection Issues**:
  - Verify DATABASE_URL is correct
  - Check network connectivity to the database server
  - Ensure the database user has appropriate permissions

- **Application Not Starting**:
  - Check server logs for error messages
  - Verify all environment variables are properly set
  - Confirm Node.js version compatibility