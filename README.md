# Football Ticket Booking System

A PostgreSQL database for managing football fans, matches, and ticket bookings. It includes the table design, sample data, and SQL queries for a database assignment.

## Features

- Users with roles (`Ticket Manager`, `Football Fan`)
- Matches with tournaments, ticket prices, and availability status
- Bookings linking users to matches, with seat and payment tracking
- Constraints for primary keys, foreign keys, unique emails, and value checks
- Queries covering filtering, pattern matching, NULL handling, joins, subqueries, and sorting

## Database Schema

| Table      | Primary Key  | Foreign Keys                                |
| ---------- | ------------ | ------------------------------------------- |
| `Users`    | `user_id`    | None                                        |
| `Matches`  | `match_id`   | None                                        |
| `Bookings` | `booking_id` | `user_id` → `Users`, `match_id` → `Matches` |

### Relationships

- One user can have many bookings (**one-to-many**).
- One match can have many bookings (**one-to-many**).
- Each booking links exactly one user to one match.

### Allowed Values

- `role`: `Ticket Manager`, `Football Fan`
- `match_status`: `Available`, `Selling Fast`, `Sold Out`, `Postponed`
- `payment_status`: `Pending`, `Confirmed`, `Cancelled`, `Refunded`

## Project Structure

## Getting Started

### Prerequisites

- PostgreSQL 12 or later
- [Beekeeper Studio](https://www.beekeeperstudio.io/)

### Setup

1. Open Beekeeper Studio and create a new PostgreSQL connection with your host, port, username, and password.
2. Create a database named `football_booking` and connect to it.
3. Open a new SQL editor tab and paste the contents of `QUERY.sql`.
4. Run the whole script (**Run All** or `Ctrl+Enter` / `Cmd+Enter`).

The script drops any existing tables, creates the three tables, inserts the sample data, and runs the queries.

## Sample Queries

| #   | Description                                              | Concepts                 |
| --- | -------------------------------------------------------- | ------------------------ |
| 1   | Available Champions League matches                       | `WHERE`, `AND`           |
| 2   | Users whose names start with "Tanvir" or contain "Haque" | `ILIKE`                  |
| 3   | Bookings with missing payment status                     | `IS NULL`, `COALESCE`    |
| 4   | Booking details with user names and fixtures             | `INNER JOIN`             |
| 5   | All users with their bookings, including those with none | `LEFT JOIN`              |
| 6   | Bookings costing more than the average                   | Subquery, `AVG`          |
| 7   | Top 2 matches by price, excluding the most expensive     | Subquery, `MAX`, `LIMIT` |

## ERD

[View the ERD](https://drive.google.com/file/d/1QRo5nL0rbtwnefP8oGbMCgMVM087fhDx/view?usp=sharing)

## Author

**Sayeed**
