# ETL Project

This project implements an ETL (Extract, Transform, Load) process to extract data from various file formats, transform the data, and load it into a target CSV file. The project also logs the progress of the ETL process. This project was created as part of the Course: [https://www.coursera.org/learn/python-project-for-data-engineering](https://www.coursera.org/learn/python-project-for-data-engineering)

## Project Structure

- `source/` - Directory containing the source data files (CSV, JSON, XML).
- `log_file.txt` - Log file that records the progress of the ETL process.
- `transformed_data.csv` - Target CSV file that stores the transformed data.

## Prerequisites

To run this project, you need to have the following Python packages installed:

- `pandas`
- `xml`
- `glob`
- `datetime`

You can install the required packages using `pip`:

```sh
pip install pandas
```
## Usage

1. Download and Extract Source Files:
Ensure that your source files are placed in the source directory.

2. Run the ETL Script:

Run the ETL script to extract data from the source files, transform the data, and load it into the target CSV file:
```sh
python etl_script.py
```

# ETL Process

## Extract
The script extracts data from the following file formats located in the source directory:

- CSV files
- JSON files
- XML files

## Transform
The extracted data is transformed by:

- Converting heights from inches to meters (rounded to two decimal places)
- Converting weights from pounds to kilograms (rounded to two decimal places)

## Load
The transformed data is loaded into the target CSV file transformed_data.csv.

## Logging
The progress of the ETL process is logged into the log_file.txt file with timestamps.

## Script Explanation
The script contains the following functions:

- extract_from_csv(file_to_process): Extracts data from a CSV file and returns a DataFrame.
- extract_from_json(file_to_process): Extracts data from a JSON file and returns a DataFrame.
- extract_from_xml(file_to_process): Extracts data from an XML file and returns a DataFrame.
- extract(): Extracts data from all source files and combines them into a single DataFrame.
- transform(data): Transforms the extracted data.
- load_data(target_file, transformed_data): Loads the transformed data into a target CSV file.
- log_progress(message): Logs the progress of the ETL process.

## Example Output
After running the script, the transformed_data.csv file will contain the transformed data, and the log_file.txt file will contain log entries similar to the following:
```sh
2024-Jul-14-12:34:56,ETL Job Started
2024-Jul-14-12:34:56,Extract phase Started
2024-Jul-14-12:34:58,Extract phase Ended
2024-Jul-14-12:34:58,Transform phase Started
Transformed Data
       name  height  weight
0      John    1.75    70.3
1      Jane    1.62    55.8
...
2024-Jul-14-12:35:00,Transform phase Ended
2024-Jul-14-12:35:00,Load phase Started
2024-Jul-14-12:35:01,Load phase Ended
2024-Jul-14-12:35:01,ETL Job Ended
```

# License
This project is licensed under the MIT License. See the `LICENSE.txt` file for more details.
