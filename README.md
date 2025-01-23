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

---

## Example Input and Output

### Input Excel

| Reference Link                              | Column A | Column B |
|---------------------------------------------|----------|----------|
| https://maps.google.com/maps?q=37.7749,-122.4194 | Data1    | Data2    |
| https://maps.google.com/maps@40.7128,-74.0060 | Data3    | Data4    |
|                                             | Data5    | Data6    |
| https://maps.google.com/maps?q=34.0522,-118.2437 | Data7    | Data8    |

### Output Excel

| Reference Link                              | Column A | Column B | Valid Map Address |
|---------------------------------------------|----------|----------|-------------------|
| https://maps.google.com/maps?q=37.7749,-122.4194 | Data1    | Data2    | True              |
| https://maps.google.com/maps@40.7128,-74.0060 | Data3    | Data4    | True              |
|                                             | Data5    | Data6    |                   |
| https://maps.google.com/maps?q=34.0522,-118.2437 | Data7    | Data8    | True              |

---

## How It Works

1. **Upload File**:
    - Users upload an Excel file through the web interface.

2. **Process File**:
    - The application reads the `Reference Link` column.
    - It validates each URL to check if it is a Google Maps link with coordinates.
    - A new column, `Valid Map Address`, is appended with the validation results.

3. **Download File**:
    - The processed file is made available for download.

---

## Validation Logic

The URL validation logic includes:
1. Checking if the domain contains `google.com`.
2. Verifying that the URL path contains `maps`.
3. Extracting coordinates from the URL after `@` or `q=`.
4. Ensuring the coordinates are valid latitude and longitude values.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Contribution

Feel free to open issues or submit pull requests to improve the application.

---

## Contact

For questions or feedback, contact **yourname@example.com**.

