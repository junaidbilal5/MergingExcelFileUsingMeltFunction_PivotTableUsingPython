# MergingExcelFileUsingMeltFunction_PivotTable
Excel to Parquet Converter
Overview
This Python script converts data from multiple sheets in an Excel file to a single Parquet file. The script is designed to handle Excel files where each sheet represents data for a specific month. It uses the pandas library to read Excel sheets, process the data, and then concatenate them into a single DataFrame. Finally, the combined data is saved as a Parquet file.

Requirements
Python 3.x
pandas library
numpy library
Usage
Ensure that you have Python installed on your system.
Install the required libraries by running the following command:

pip install pandas numpy

Modify the path variable in the script to point to your Excel file. You can either directly set the path or use the input prompt (commented lines).

path = 'your_excel_file.xlsx'

Run the script. It will read data from each sheet in the Excel file, melt the DataFrame, concatenate them vertically, reset the index, and save the result as a Parquet file.

python excel_to_parquet_converter.py

Script Explanation
Import Libraries:

The script uses the pandas and numpy libraries for data manipulation.
Set Display Options:

Display options for pandas are set to show all rows (display.max_rows).
Read Excel File:

The script reads an Excel file specified by the path variable using the pandas ExcelFile object.
Loop Through Sheets:

Sheets in the Excel file are read into separate DataFrames and stored in a dictionary (sheet_data).
Melt DataFrames:

Each DataFrame is melted to convert it from wide to long format, and the melted DataFrames are stored in a new dictionary (final).
Concatenate DataFrames:

Melted DataFrames are concatenated vertically into a single DataFrame (combined_df).
Reset Index:

The index of the combined DataFrame is reset.
Convert Date Format:

The 'Date' column is converted to datetime and then only the date part is retained.
Save as Parquet:

The final DataFrame is saved as a Parquet file (daily_sell_thru_forecast_20231121.parquet).
Notes
Ensure that the Excel file is structured such that each sheet represents data for a specific month with consistent column names.
The Parquet file will be saved in the same directory as the script.