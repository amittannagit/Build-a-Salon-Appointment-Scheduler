```markdown
# Salon Appointment Scheduler

## Description
This project is a simple command-line salon appointment scheduling system. It uses a PostgreSQL database to store customer information, services offered, and appointments. The system allows users to select a service, enter their phone number, and schedule an appointment.

## Features
- Display a list of available services
- Add new customers to the database
- Schedule appointments for existing and new customers
- Validate user inputs
- Provide confirmation of scheduled appointments

## Prerequisites
- PostgreSQL
- Bash shell

## Setup
1. Create the salon database:
   ```
   psql --username=freecodecamp --dbname=postgres -c "CREATE DATABASE salon;"
   ```

2. Connect to the salon database and create the necessary tables:
   ```
   psql --username=freecodecamp --dbname=salon
   ```
   Then run the SQL commands to create tables (customers, services, appointments) and insert initial services data.

3. Make the script executable:
   ```
   chmod +x salon.sh
   ```

## Usage
Run the script from the command line:
```
./salon.sh
```

Follow the prompts to schedule an appointment:
1. Select a service from the list
2. Enter your phone number
3. If you're a new customer, enter your name
4. Enter the desired appointment time

## File Structure
- `salon.sh`: The main Bash script for the appointment scheduler
- `salon.sql`: SQL file containing database schema and initial data (if you choose to create one)

## Database Schema
- `customers`: Stores customer information (id, name, phone)
- `services`: Stores available services (id, name)
- `appointments`: Stores appointment details (id, customer_id, service_id, time)

## Maintenance
To backup your database, you can use:
```
pg_dump -cC --inserts -U freecodecamp salon > salon.sql
```

To restore from a backup:
```
psql -U postgres < salon.sql
```

## Contributing
This project is for educational purposes. Feel free to fork and modify for your own learning.

## License
This project is open source and available under the [MIT License](LICENSE).
```
