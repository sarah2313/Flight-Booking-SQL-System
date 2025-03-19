# Flight Booking System

## Project Overview
The **Flight Booking System** is an SQL-based project that manages flight bookings, passengers, airlines, and ticketing details. This system allows users to retrieve and manage flight schedules, bookings, and customer details efficiently.

## Features
- Manage flight details (airlines, routes, schedules)
- Book, update, and cancel reservations
- Retrieve passenger and booking information
- Perform analytical queries on flight data

## Database Schema
The project consists of multiple tables, including:
- **Flights**: Stores flight information (flight number, departure, destination, etc.)
- **Passengers**: Stores customer details
- **Bookings**: Manages ticket reservations
- **Airlines**: Details of different airlines operating flights
- **Payments**: Stores payment transaction details

## How to Run
1. Install MySQL or any SQL-compatible database.
2. Open the SQL terminal or any database management tool.
3. Execute the `FlightBookingSystem.sql` script to create tables and insert sample data.
4. Run queries to test the functionality.

## Screenshots
Screenshots of query results and database structure are stored in the `screenshots/` folder.

## Sample Queries
Here are some example SQL queries you can run:
```sql
-- Retrieve all available flights
SELECT * FROM Flights WHERE departure_date > CURDATE();

-- Find all bookings for a specific passenger
SELECT * FROM Bookings WHERE passenger_id = 1;

-- Get revenue per airline
SELECT Airlines.name, SUM(Payments.amount) AS total_revenue
FROM Payments
JOIN Bookings ON Payments.booking_id = Bookings.id
JOIN Flights ON Bookings.flight_id = Flights.id
JOIN Airlines ON Flights.airline_id = Airlines.id
GROUP BY Airlines.name;
```

## License
This project is open-source and available under the [MIT License](LICENSE).

## Contributing
Feel free to fork this repository, open issues, and submit pull requests.

## Contact
For any questions or suggestions, reach out via GitHub Issues.

