# Airbnb Data Pipeline

This project demonstrates a real-time data pipeline for processing Airbnb booking data using AWS services.

## Components

1. **Amazon SQS**:
   - **Queue**: `AirbnbBookingQueue`
   - **Dead Letter Queue (DLQ)**: `AirbnbBookingDLQ` (for messages that fail after 3 retries)

2. **AWS Lambda Functions**:
   - **Producer**: `ProduceAirbnbBookingData` – Generates and sends mock booking data to `AirbnbBookingQueue`.
   - **Consumer**: `ProcessFilteredBookings` – Processes filtered messages and stores them in an S3 bucket.

3. **EventBridge Pipes**:
   - Filters messages from `AirbnbBookingQueue` based on booking duration and routes them to the consumer Lambda function.

4. **S3 Bucket**:
   - **Bucket Name**: `airbnb-booking-records`

5. **CI/CD**:
   - Automated deployment using AWS CodeBuild linked to a GitHub repository.

## Setup

1. **Create SQS Queues**:
   - Set up `AirbnbBookingQueue` and `AirbnbBookingDLQ` in the AWS SQS Console.

2. **Deploy Lambda Functions**:
   - Implement and deploy `ProduceAirbnbBookingData` and `ProcessFilteredBookings`.

3. **Configure EventBridge Pipes**:
   - Set up a pipe to filter and route messages from `AirbnbBookingQueue` to the consumer Lambda function.

4. **Create S3 Bucket**:
   - Create an S3 bucket named `airbnb-booking-records` for storing processed booking records.

## License

Specify the license for your project here.
