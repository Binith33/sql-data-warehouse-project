# SQL Data Warehouse Project

This project implements a Data Warehouse using a Medallion Architecture (Bronze, Silver, Gold layers). It contains the necessary scripts to extract, load, and transform data, as well as data catalogs and architecture diagrams.

## Project Structure

- **`datasets/`**: Source datasets (e.g., CRM and ERP data) used for the data warehouse.
- **`docs/`**: Documentation including data architecture diagrams (`.drawio` & `.png`), data catalogs, and naming conventions.
- **`scripts/`**: SQL scripts for initializing the database and managing the different layers:
  - **`bronze/`**: Raw data ingestion scripts (DDL and procedures).
  - **`silver/`**: Data cleansing, validation, and transformation scripts.
  - **`gold/`**: Business-level aggregations and dimensional modeling scripts.
- **`tests/`**: Data quality checks for the Silver and Gold layers.

## Architecture

The Data Warehouse follows the Medallion Architecture:
1. **Bronze Layer**: Stores raw, unvalidated data directly from the source systems.
2. **Silver Layer**: Cleansed and conformed data. This layer resolves data quality issues and standardizes formats.
3. **Gold Layer**: Business-ready data models (star schema with Fact and Dimension tables) optimized for reporting and analytics.

## Getting Started

1. **Database Initialization**: Run `scripts/init_database.sql` to set up the necessary databases and schemas.
2. **Table Creation**: Execute the DDL scripts in `scripts/bronze`, `scripts/silver`, and `scripts/gold` to create the tables.
3. **Data Loading**: Use the stored procedures to load data layer by layer.
4. **Testing**: Run the queries in the `tests/` directory to ensure data quality and integrity across the Silver and Gold layers.
