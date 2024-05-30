# Spark Log Analysis

This project is focused on analyzing server log data using Apache Spark. The code processes log data to extract valuable insights, such as frequent hosts, most requested URLs, and HTTP status code distributions.

## Requirements

- Python 3.x
- Apache Spark
- PySpark
- Pandas
- Matplotlib
- Seaborn

## Setup

1. **Install Apache Spark**: Follow the instructions on the [official Spark website](https://spark.apache.org/downloads.html) to install Spark on your system.

2. **Install Python Dependencies**:
   ```sh
   pip install pyspark pandas matplotlib seaborn
   ```

## Data

The data used in this project includes:
- A sample log file from a specified URL.
- A local log file located at `./logs.txt`.

## Process Overview

1. **Spark Session Initialization**: Create a Spark session and context.
2. **Data Loading**: Load the log data from a remote URL and a local file.
3. **Data Schema Inspection**: Inspect and display the schema of the loaded data.
4. **Log Parsing**: Extract various fields (host, timestamp, method, endpoint, protocol, status, content size) from the log entries using regular expressions.
5. **Data Cleaning**: Identify and handle missing values.
6. **Data Aggregation and Analysis**:
   - Compute the most requested URLs.
   - Count occurrences of different HTTP status codes.
   - Identify frequent hosts.

## Analysis Steps

1. **Extract Hosts**: Identify the host part of each log entry.
2. **Extract Methods, URIs, Protocols**: Parse the request method, URI, and protocol from the log entries.
3. **Extract Status Codes**: Extract HTTP status codes.
4. **Create DataFrame**: Assemble the parsed data into a structured DataFrame.
5. **Compute Statistics**:
   - Most requested URLs
   - Frequency of HTTP status codes
   - Frequent hosts

6. **Visualization**: Plot the distribution of HTTP status codes using Matplotlib and Seaborn.

## Example Usage

```python
from pyspark.sql import SparkSession

# Initialize Spark session
spark = SparkSession.builder.master("local").appName("Spark log analysis").getOrCreate()

# Load data and perform analysis
# [See full script for detailed steps]
```

## Results

- **Top 5 Requested URLs**: Lists the endpoints with the highest number of requests.
- **HTTP Status Code Distribution**: Shows the frequency of each HTTP status code in the logs.
- **Frequent Hosts**: Identifies the hosts making the most requests.

## Visualization

The project includes visualizations for the distribution of HTTP status codes. The following libraries are used for creating plots:
- Matplotlib
- Seaborn

## Conclusion

This project demonstrates how to use Apache Spark for large-scale log data analysis, showcasing the capabilities of PySpark for data processing, cleaning, and aggregation, along with Pandas and Seaborn for visualization.

## License

This project is licensed under the MIT License.
