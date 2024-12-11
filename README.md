# Real-Time Data Pipeline with GCP Pub/Sub and Dataflow

## Overview

This project demonstrates a real-time data pipeline using Google Cloud Platform's (GCP) services, specifically **Pub/Sub** for message ingestion and **Dataflow** for stream processing. The data originates from a virtual store application built with **Dash**, which simulates real-time transactions and events.

## Architecture

### Components:
- **Dash Virtual Store**: A web application that generates mock data simulating customer interactions in a store.
- **Pub/Sub**: Acts as the messaging service where the Dash application publishes transaction data.
- **Dataflow**: Processes the incoming stream of data, performs transformations, and prepares it for analysis or storage.

### Flow:
1. **Data Generation**: 
   - The Dash application generates real-time data (e.g., purchases, stock updates, user interactions).
   - This data is published to a Pub/Sub topic.

2. **Data Ingestion**:
   - Pub/Sub receives and queues the data.

3. **Stream Processing**:
   - Dataflow job subscribes to the Pub/Sub topic.
   - Dataflow processes the data stream, possibly for aggregation, filtering, or transformation.
   - The processed data can be further routed to BigQuery for analytics, Cloud Storage for long-term storage, or other services.

## Setup

### Prerequisites
- Google Cloud SDK installed and configured with appropriate permissions.
- Python 3.7+ (for Dash application)
- [Google Cloud Pub/Sub API enabled](https://console.cloud.google.com/apis/library/pubsub.googleapis.com)
- [Google Cloud Dataflow API enabled](https://console.cloud.google.com/apis/library/dataflow.googleapis.com)

### Installation

```sh
# Install necessary Python packages
pip install dash gunicorn flask google-cloud-pubsub google-cloud-dataflow
