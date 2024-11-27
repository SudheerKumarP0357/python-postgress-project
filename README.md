# Python + PostgreSQL Application

This project is a 3-tier web application built using Python for the backend, with PostgreSQL as the database. The application consists of a presentation layer, a business logic layer, and a data access layer.

## Prerequisites
Before setting up the project, ensure you have the following installed on your machine:

- Ubuntu (or another compatible Linux distribution)
- Python 3.12 or higher
- PostgreSQL

## Installation
### 1. Installing PostgreSQL

To install and set up PostgreSQL, follow these steps:

1. **Install PostgreSQL and additional tools:**

   ```bash
   sudo apt-get install postgresql postgresql-contrib

   # Start & enable the PostgreSQL service
   sudo systemctl start postgresql
   sudo systemctl enable postgresql

   ```

### 2. Setting Up PostgreSQL Database

1. **Run the following commands to switch user to postgres**
   ```bash
   sudo -i -u postgres

   # once you switched to postgres user, run the below cmd
   psql
   ```

2. **Create a new PostgreSQL user:**

   ```sql
   CREATE USER root WITH PASSWORD 'root';
   ALTER USER root CREATEDB;

   -- Create the db with your_choice
   CREATE DATABASE my_database;

   --Grant all privileges on the database to the new user
   GRANT ALL PRIVILEGES ON DATABASE my_database TO root;

   --Connect to the new database
   \c my_database;

   --Grant all privileges on the public schema & database to the user
   GRANT ALL PRIVILEGES ON SCHEMA public TO root;
   GRANT CREATE ON DATABASE my_database TO root;

   --quit the psql
   \q
   ```

### 2. Setting Up Python Virtual Environment

1. **Install the Python 3.12 virtual environment package & pip:**

   ```bash
   sudo apt update
   sudo apt install python3.12-venv python3-pip -y
   ```

2. **Create a virtual environment:**

   ```bash
   # Create the virtual environment
   python3 -m venv myenv
   
   # Activate the virtual environment
   source myenv/bin/activate
   ```

3. **Install required Python libraries from `requirements.txt`:**

   ```bash
   pip3 install -r requirements.txt
   ```


## Running the Application

Once the environment and database are set up, you can run the application with the following steps:

4. **Run the application:**

   ```bash
   python run.py
   ```
   The application will start, and you can access it via the specified host and port in your configuration.