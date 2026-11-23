# Booking API ETL Pipeline

Jupyter notebooks that pull bookings from a school-management REST API, flatten the nested JSON and load it into SQL Server for reporting.

## Flow
1. `01_extract_booking_list/` pages through the bookings endpoint, saves raw JSON per page and combines the pages.
2. `02_extract_booking_details/` fetches the detail record for each booking.
3. `Bookings_ETL.ipynb` normalises students, courses, agents and prices with pandas and writes them to SQL Server through SQLAlchemy.

## Setup
```bash
pip install pandas numpy requests sqlalchemy pyodbc jupyter
export API_TOKEN=...          # bearer token, never commit it
export SQL_SERVER='localhost\SQLEXPRESS'
```
Edit `BASE_URL` in the extract notebooks to point at your own instance. Notebook outputs are cleared, and no real data is included.

License: MIT
