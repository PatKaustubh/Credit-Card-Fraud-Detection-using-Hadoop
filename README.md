# Credit Card Fraud Detection using Hadoop

## Overview
This project aims to detect fraudulent credit card transactions in real-time using a Big Data processing pipeline. The solution integrates various technologies, including Hadoop, MongoDB, Kafka, and Spark Streaming, to ensure fast and reliable fraud detection.

## Architecture
1. **Data Storage**: 
   - Cardholder and credit score data stored in AWS RDS (exported to Hadoop).
   - Historical transactions stored in MongoDB.
   
2. **Real-Time Streaming**:
   - POS transaction data ingested via Kafka.
   - Spark Streaming processes the data and validates transactions.
   
3. **Fraud Detection Rules**:
   - **Upper Control Limit (UCL)**: Identifies unusual transaction amounts.
   - **Credit Score Check**: Blocks transactions from users with scores below 200.
   - **ZIP Code Analysis**: Flags geographically improbable transactions.
   
4. **Transaction Processing**:
   - Genuine transactions update historical data.
   - Fraudulent transactions trigger alerts.
   
## Tasks
1. **Load Transaction Data into MongoDB**
   - Import `card_transactions.csv` into MongoDB.

2. **Ingest Data from AWS RDS to Hadoop**
   - `card_member.csv` and `member_score.csv` are loaded into Hadoop.

3. **Create a Lookup Table in MongoDB**
   - Stores key details for quick fraud detection.

4. **Load Data into the Lookup Table**
   - Populate with transaction and credit score data.

5. **Stream Processing with Kafka & Spark**
   - Validate transactions against fraud rules.

6. **Update Transaction Status**
   - Store results in `card_transactions` table.

7. **Update Lookup Table for Genuine Transactions**
   - Maintain latest transaction details for each card.

## Data Sources
- **Card Member Data**: [Download Here](https://cdn.upgrad.com/uploads/production/1022ae5a-d405-4208-9fa3-1bbac2a7db5f/card_member.csv)
- **Card Transactions Data**: [Download Here](https://cdn.upgrad.com/UpGrad/temp/32de2936-42f9-412f-a00c-2a0f400873cf/card_transactions.csv)
- **Member Score Data**: [Download Here](https://cdn.upgrad.com/uploads/production/2b45fb43-2792-47cc-b4bc-d298a5946e69/member_score.csv)
- **Distance Utility (Geo Map)**: [Download Here](https://cdn.upgrad.com/uploads/production/f3195e8c-d692-4dd1-a605-e540484657aa/geo_map.py)

## Resources
- [Processing MongoDB in AWS EMR with Python](https://stackoverflow.com/questions/31972780/processing-mongodb-in-aws-emr-with-python)
- [Hadoop and MongoDB Download Guide](https://www.mongodb.com/resources/products/compatibilities/hadoop-and-mongodb)

## Technologies Used
- **Hadoop**: Data storage & processing
- **MongoDB**: NoSQL database
- **Kafka**: Message queue for real-time transactions
- **Spark Streaming**: Real-time data processing
- **AWS EMR**: Cloud-based big data processing

## Setup Instructions
1. Install Hadoop, MongoDB, Spark, and Kafka.
2. Load data into respective databases.
3. Configure Kafka to ingest POS transactions.
4. Run Spark Streaming job for real-time fraud detection.

