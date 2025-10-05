# Cocopilot CSV Manager - API Documentation

## Overview
The Cocopilot CSV Manager provides a simple and efficient way to manage CSV files in Android applications.

## Core Classes

### CsvManager
Main class for CSV operations.

#### Methods
- `loadCsvFile(String filename)` - Load CSV file
- `validateData()` - Validate CSV data
- `getData()` - Get processed data
- `saveCsvFile(String filename)` - Save CSV file

### CsvValidator
Validates CSV data integrity.

#### Methods
- `validateHeaders(String[] headers)` - Validate column headers
- `validateRows(String[][] data)` - Validate data rows
- `checkDataTypes()` - Check data type consistency

### CsvProcessor
Processes CSV data.

#### Methods
- `parseCsv(String content)` - Parse CSV content
- `formatCsv(String[][] data)` - Format data as CSV
- `filterData(String[][] data, String filter)` - Filter data

## Usage Examples

### Basic CSV Loading
```java
CsvManager csvManager = new CsvManager();
csvManager.loadCsvFile("data.csv");
boolean isValid = csvManager.validateData();
```

### Data Validation
```java
CsvValidator validator = new CsvValidator();
String[] headers = {"Name", "Age", "City"};
boolean validHeaders = validator.validateHeaders(headers);
```

### Data Processing
```java
CsvProcessor processor = new CsvProcessor();
String[][] data = processor.parseCsv(csvContent);
String[][] filtered = processor.filterData(data, "Age > 25");
```

## Error Handling
All methods throw `CsvException` for error conditions.

### Common Exceptions
- `InvalidCsvFormatException` - Invalid CSV format
- `FileNotFoundException` - CSV file not found
- `ValidationException` - Data validation failed

## Configuration
Configure the CSV manager using the `CsvConfig` class:

```java
CsvConfig config = new CsvConfig()
    .setDelimiter(',')
    .setQuoteChar('"')
    .setSkipEmptyLines(true);
```

## Performance Tips
- Use streaming for large files
- Enable caching for frequently accessed data
- Use appropriate data types
- Validate data early in the process

## Best Practices
1. Always validate data before processing
2. Use appropriate error handling
3. Consider memory usage for large files
4. Implement proper logging
5. Use consistent data formats
