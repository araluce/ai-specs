# Development Guide

This guide provides step-by-step instructions for setting up the development environment and running tests for Ruby on Rails apps.

## 🚀 Setup Instructions

### Prerequisites

Ensure you have the following installed:
- **Yarn** (v1.22 or higher)
- **Git**

### 1. Clone the Repository

```bash
git clone git@github.com:araluce/ai-specs.git
cd ai-specs
```

### 2. Environment Configuration

Create environment file for backend:

**Backend Environment** (`backend/.env`):
```env
# MySQL Database Configuration
DB_HOST=localhost
DB_PORT=3306
DB_USERNAME=root
DB_PASSWORD=
DB_NAME=

# Rails Environment
RAILS_ENV=development
PORT=3000
```


### 3. Database Setup (MySQL)

Install and start MySQL server locally. Ensure the following configuration:

- **Host**: `localhost`
- **Port**: `3306`
- **Database**: ``
- **Username**: `root`
- **Password**:


### 4. Backend Setup (Ruby on Rails)

```bash
# Navigate to backend directory
cd backend

# Install dependencies
gem install bundler
bundle install

# Set up the database
rails db:create
rails db:migrate

# (Optional) Seed the database with sample data
rails db:seed

# Start the Rails development server
rails server -p 3000
```

The backend API will be available at `http://localhost:3000`




## 🧪 Testing

### Backend Testing (Ruby on Rails)

```bash
cd backend

# Run all tests
rails test

# If using RSpec
bundle exec rspec

# Run tests with coverage (if SimpleCov is set up)
COVERAGE=true rails test
```



