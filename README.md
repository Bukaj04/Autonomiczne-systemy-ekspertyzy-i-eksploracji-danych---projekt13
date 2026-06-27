# Project goal
- fetch the wind data from the REST API,
- aggregate the data by hours/stations,
- present the risk analysis results

# Execution steps
1. Fetch data from the REST API and save it as raw_data.json in the Amazon S3 bucket
2. Process the raw data, validate it, ensure that there are no impossible or empty values and save it as validated_data.csv in the Amazon S3 bucket
3. Fetch the validated_data.csv, aggregate it by hours and stations, calculate the important parameters (mean, max wind speed)
4. Analyze the data and return a proper risk score for each activity, station and hour
5. Present the results in a table and on the hourly heatmap

# File structure
```text
aws-logs-003693136002-us-east-1/  #Bucket S3
│
├── raw/
│   └── raw_data.json               # Surowe dane z REST API
│
├── validated/
│   └── validated_data.csv          # Dane oczyszczone i sprawdzone
│
└── final/
    └── final_data.csv              # Końcowe wyniki
