# Salon Appointment Scheduler

Welcome to the **Salon Appointment Scheduler** project! This project involves creating a PostgreSQL database for managing customer appointments in a salon. You'll also develop a Bash script that interacts with the database to schedule appointments based on user input.

## Project Structure

1. **Create the Database**
   - Start by creating a database named `salon`.
   - Define the necessary tables (`customers`, `appointments`, and `services`) with appropriate columns and constraints.

2. **Develop the Bash Script**
   - Create a Bash script named `salon.sh` that will interact with the database to manage appointments.
   - The script will prompt users to select a service, enter their phone number, name, and appointment time.

3. **Version Control**
   - Use Git for version control, ensuring you commit your work with clear and descriptive messages.

## Getting Started

### Prerequisites

- PostgreSQL installed and running on your system.
- Git installed and configured.
- Basic knowledge of SQL and Bash scripting.

### Instructions

1. **Connect to PostgreSQL**
   - Start by connecting to the PostgreSQL server:
     ```bash
     psql --username=freecodecamp --dbname=postgres
     ```
   - Create a new database named `salon`:
     ```sql
     CREATE DATABASE salon;
     ```

2. **Create Tables**
   - Connect to the `salon` database:
     ```bash
     psql --username=freecodecamp --dbname=salon
     ```
   - Create the necessary tables:
     - `customers` table with columns: `customer_id`, `phone`, and `name`.
     - `services` table with columns: `service_id` and `name`.
     - `appointments` table with columns: `appointment_id`, `customer_id`, `service_id`, and `time`.
   - Ensure primary keys auto-increment and that foreign keys are correctly set up.

3. **Develop the Script**
   - Create a script file named `salon.sh` in the project folder:
     ```bash
     touch salon.sh
     ```
   - Make sure the script is executable:
     ```bash
     chmod +x salon.sh
     ```
   - The script should:
     - Display a numbered list of services.
     - Prompt users to enter a service ID, phone number, name (if not already a customer), and appointment time.
     - Add new customers to the `customers` table if they are not already present.
     - Schedule an appointment by adding a new entry to the `appointments` table.
     - Output a confirmation message after successfully scheduling an appointment.

4. **Database Backup**
   - To save your database, create a dump:
     ```bash
     pg_dump -cC --inserts -U freecodecamp salon > salon.sql
     ```
   - This dump file can be used to restore the database later:
     ```bash
     psql -U postgres < salon.sql
     ```

## Usage

- Running the script without any arguments should prompt the user to select a service and enter the necessary information to schedule an appointment.
  
- Example interaction:
  ```
  Welcome to My Salon, how can I help you today?
  1) cut
  2) color
  3) perm
  Please select a service by entering the corresponding number: 1
  Please enter your phone number: 555-555-5555
  I don't have a record for that phone number, what's your name? Fabio
  What time would you like your cut, Fabio? 10:30
  I have put you down for a cut at 10:30, Fabio.
  ```

## Notes

- Ensure that your script finishes running after completing tasks, or tests won't pass.
- The script should not use the `clear` command or other commands that might erase the output.
- The tests may add data to your database, feel free to delete any test data.

## Completion

- Make sure all tasks are complete, your database is backed up, and your script is functioning correctly.
- Commit all changes to Git with clear and descriptive messages.
- Submit the URL to your public repository on freeCodeCamp.org.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
