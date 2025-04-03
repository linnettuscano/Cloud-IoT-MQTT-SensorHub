
This project demonstrates how to use AWS IoT and MQTT to collect and publish sensor data (temperature, humidity, and CO2 levels) to AWS IoT, and then store the data in an S3 bucket. The system uses a Python script to simulate sensor readings and send them to AWS IoT using MQTT. An AWS IoT rule then stores the incoming data into an S3 bucket.

Steps for Setup

1. Prerequisites
   - AWS Account
   - Python 3.x
   - Required Python libraries:
     - `paho-mqtt`

2.Configure AWS IoT and S3
   - AWS IoT: Set up AWS IoT core with a specific topic for receiving sensor data.
   - S3 Bucket: Create an S3 bucket to store the sensor data.
   - create an AWS IoT Rule: 
     - The rule will trigger whenever data is received on the topic and store the data in the S3 bucket. The message format will be a JSON object containing sensor readings.

3. AWS IoT Certificates and Permissions
   - Make sure that the AWS IoT policy and the necessary certificates are configured properly.
   - Attach the required IAM role and permissions to allow the rule to access the S3 bucket.

4. Run the Python Script
   - The script simulates sensor data and publishes it to the topic in AWS IoT. It will continue to publish data at regular intervals
   - The script will publish simulated data to AWS IoT, which will then be stored in the configured S3 bucket.

5. Monitor S3 Bucket
   - After running the script, check the S3 bucket for the stored JSON files. Each file will contain the sensor data, with the filename containing a timestamp (e.g., `1616161616.json`).
