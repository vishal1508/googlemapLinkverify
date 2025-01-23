# Excel Google Maps Validator

This is a Flask-based web application for processing Excel files. The application reads an uploaded Excel file, validates URLs in a `Reference Link` column to check if they are valid Google Maps addresses, and appends a new column, `Valid Map Address`, with `True`, `False`, or blank values based on the validation.

---

## Features

- Upload an Excel file.
- Validate URLs in the `Reference Link` column.
- Append a new column named `Valid Map Address` with validation results:
  - **True**: The link is a valid Google Maps address with coordinates.
  - **False**: The link is not a valid Google Maps address.
  - **Blank**: The `Reference Link` column is empty for the row.
- Download the processed Excel file.

---

## Requirements

- Python 3.8 or higher
- Flask
- pandas
- openpyxl
- xlrd

---

## Installation

1. **Clone the repository**:
    ```bash
    git clone https://github.com/yourusername/excel-google-maps-validator.git
    cd excel-google-maps-validator
    ```

2. **Set up a virtual environment** (optional but recommended):
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3. **Install dependencies**:
    ```bash
    pip install -r requirements.txt
    ```

4. **Create necessary directories**:
    ```bash
    mkdir uploads processed
    ```

---

## Usage

1. **Start the Flask server**:
    ```bash
    python app.py
    ```

2. **Open your browser** and go to:
    ```
    http://127.0.0.1:5000/
    ```

3. **Upload an Excel file**:
    - The file must have a column named `Reference Link`.

4. **Download the processed file**:
    - The processed file will contain a new column named `Valid Map Address`.

---

## Directory Structure

