# BuildTrack SmartSite Management System

A comprehensive web application for tracking and managing construction or project sites.

## Features

- **Site Management**: Create, view, update, and delete construction sites
- **Project Tracking**: Manage projects associated with specific sites
- **Task Management**: Assign and track tasks related to projects
- **Milestone Tracking**: Set and monitor project milestones
- **Dashboard Overview**: View summary statistics, recent tasks, and upcoming milestones

## Tech Stack

- **Frontend**: React, TypeScript, TailwindCSS, shadcn/ui
- **Backend**: Node.js, Express
- **Database**: PostgreSQL with Drizzle ORM
- **API**: RESTful API with React Query for data fetching

## Getting Started

1. Clone the repository
2. Install dependencies:
   ```
   npm install
   ```
3. Set up your PostgreSQL database and update the DATABASE_URL in environment variables
4. Run database migrations:
   ```
   npm run db:push
   ```
5. Start the application:
   ```
   npm run dev
   ```

## Environment Variables

Create a `.env` file in the root directory with the following variables:

```
DATABASE_URL=postgresql://username:password@hostname:port/database
```

## Project Structure

- `/client`: Frontend React application
- `/server`: Backend Express server
- `/shared`: Shared code and database schema