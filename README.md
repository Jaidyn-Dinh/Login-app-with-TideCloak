# Login App with TideCloak

A basic authentication application built with **Next.js** and **TideCloak**. This project demonstrates user registration, login, logout, and access to a protected dashboard.

## Features

- User account creation
- User login
- User logout
- Protected dashboard
- Unauthenticated users are redirected to login
- TideCloak authentication
- DPoP-bound access tokens

## Technologies

- Next.js 16
- TypeScript
- TideCloak
- Docker
- Node.js / npm

## Prerequisites

Before running the project, ensure you have:

- Node.js installed
- npm installed
- Docker Desktop installed and running
- A local TideCloak instance configured

## Installation

Clone the repository and install the dependencies:

```bash
git clone https://github.com/Jaidyn-Dinh/Login-app-with-tidecloak.git
cd Login-app-with-tidecloak
npm install
```

## Environment Configuration

Create a local `.env` file from the provided example:

```bash
Copy-Item .env.example .env
```

Configure the required values in `.env`.

Do not commit the `.env` file because it may contain credentials or other sensitive configuration.

## TideCloak Setup

Start Docker Desktop and initialise the local TideCloak instance:

```bash
.\scripts\init-tidecloak.ps1
```

TideCloak will be available at:

`http://localhost:8080`

Configure the TideCloak client for the application to use:

- Application URL: `http://localhost:3000`
- Valid redirect URIs: `http://localhost:3000/*`
- Web origin: `http://localhost:3000`
- User registration enabled
- DPoP-bound access tokens enabled

Download the Tide adapter configuration from TideCloak and place it at:

```text
data/tidecloak.json
```

## Running the Application

Start the development server:

```bash
npm run dev
```

Open the application at:

`http://localhost:3000`

## Authentication

Users can create an account or sign in through TideCloak.

After successful authentication, users can access:

`http://localhost:3000/dashboard`

Users who attempt to access the dashboard without being authenticated are redirected to the TideCloak login page.

## Security

Sensitive environment configuration is excluded from Git through `.gitignore`.

Do not commit:

- `.env`
- Admin passwords
- Access tokens
- Other private credentials

## Purpose

This project was created as a basic demonstration of integrating TideCloak authentication with a Next.js application.
