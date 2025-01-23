# Excel Google Maps Validator

This Flask-based web application processes Excel files by validating URLs in the `Reference Link` column. It adds a new column, `Valid Map Address`, indicating whether the URL is a valid Google Maps address.

---

## Features

- Upload an Excel file for processing.
- Validate URLs in the `Reference Link` column:
  - **True**: A valid Google Maps address with coordinates.
  - **False**: Not a valid Google Maps address.
  - **Blank**: Empty or missing values in the `Reference Link` column.
- Preserve all other columns in the original Excel file.
- Download the processed file.

---

## Requirements

- Python 3.8 or higher
- Flask
- openpyxl

---

## Installation

1. **Clone the repository**:
    ```bash
    git clone https://github.com/vishal1508/googlemapLinkverify.git
    cd excel-google-maps-validator
    ```

2. **Set up a virtual environment** (optional but recommended):
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3. **Install dependencies**:
    ```bash
    pip install flask openpyxl
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

2. **Access the application in your browser**:
    ```
    http://127.0.0.1:5000/
    ```

3. **Upload an Excel file**:
    - Ensure the file contains a column named `Reference Link`.

4. **Download the processed file**:
    - After processing, the file will include a new column, `Valid Map Address`.

---

## Project Structure


---

## Example Input and Output

### Input Excel File

| Reference Link                              | Column A | Column B |
|---------------------------------------------|----------|----------|
| https://maps.google.com/maps?q=37.7749,-122.4194 | Data1    | Data2    |
| https://maps.google.com/maps@40.7128,-74.0060 | Data3    | Data4    |
|                                             | Data5    | Data6    |
| https://example.com/random-url              | Data7    | Data8    |

### Output Excel File

| Reference Link                              | Column A | Column B | Valid Map Address |
|---------------------------------------------|----------|----------|-------------------|
| https://maps.google.com/maps?q=37.7749,-122.4194 | Data1    | Data2    | True              |
| https://maps.google.com/maps@40.7128,-74.0060 | Data3    | Data4    | True              |
|                                             | Data5    | Data6    |                   |
| https://example.com/random-url              | Data7    | Data8    | False             |

---

## How It Works

1. **Upload File**:
    - Users upload an Excel file via the web interface.

2. **Process File**:
    - The app reads the `Reference Link` column.
    - It validates URLs using the following logic:
      - Checks if the domain contains `google.com`.
      - Confirms the URL path includes `maps`.
      - Validates the presence of latitude and longitude in the URL.

3. **Download File**:
    - The processed file, with the `Valid Map Address` column, is provided for download.

---

## Validation Logic

1. **Domain Check**:
    - Verifies that the domain includes `google.com`.

2. **Path Check**:
    - Confirms the URL path contains `maps`.

3. **Coordinate Extraction**:
    - Extracts latitude and longitude from the URL.

4. **Result**:
    - `True` if valid coordinates are found.
    - `False` otherwise.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Contact

For questions or feedback, contact **yourname@example.com**.
