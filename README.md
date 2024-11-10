# Cloud-based-Real-Time-Traffic-Monitoring
 The goal of this project is to build a cloud-based traffic analysis system that can analyze the traffic data from historic data. The big data is processed through Kafka and analyzed through Spark framework to provide the analysis. 
# Traffic Analysis System

## Overview
This project is a cloud-based traffic analysis system that uses Kafka and Spark to process and analyze real-time traffic data. It ingests data from a Kafka producer, processes it with Spark Structured Streaming, and outputs real-time analytics on vehicle counts from various directions at different junctions.

This project is set up on **Windows 11 using WSL (Windows Subsystem for Linux)**, allowing us to run Linux-based applications like Kafka and Spark on Windows.

## Project Structure
- **Kafka Producer**: A Python script that reads traffic data from a CSV file and sends it to a Kafka topic.
- **Spark Consumer**: A Spark job that consumes data from the Kafka topic, processes and aggregates it, and outputs analytics.
- **Configuration Files**:
  - `getting-started.ini`: Configuration file for the Kafka producer, specifying Kafka connection settings.
  - `VEHICLES-DATA.csv`: Sample CSV file containing traffic data to be ingested.

## Components

### 1. Kafka Producer
The producer reads data from `VEHICLES-DATA.csv` and sends it to a Kafka topic (`kansasData`). 

#### Files:
- `producer_script.py`: Python script for the Kafka producer.
- `getting-started.ini`: Configuration file for producer settings.

#### Key Libraries:
- `confluent_kafka`: Used to integrate the Python producer with Confluent Kafka.

#### Running the Producer
To run the Kafka producer, use the following command:
```bash
python producer_script.py getting-started.ini


## Setup Instructions

### Installing WSL (Windows Subsystem for Linux)
1. **Enable WSL**: Open PowerShell as Administrator and run:
   ```bash
   wsl --install
This will enable WSL on Windows. You might need to restart your machine.

Install Ubuntu:

Open the Microsoft Store and search for "Ubuntu".
Install the latest version of Ubuntu.
After installation, launch the Ubuntu terminal and set up a username and password.
Check WSL version: Once Ubuntu is installed, check the version by running:


wsl --list --verbose
Ensure Ubuntu is installed properly: Open the Ubuntu terminal and ensure you can run basic commands like ls and pwd.

Installing Confluent Kafka
Download and install Confluent Kafka: Confluent Kafka is the distribution of Kafka with additional tools and features.

First, install Confluent’s platform repository on Ubuntu:

wget https://packages.confluent.io/archive/6.1/confluent-6.1.0.tar.gz
tar -xvf confluent-6.1.0.tar.gz
export CONFLUENT_HOME=~/confluent-6.1.0
export PATH=$CONFLUENT_HOME/bin:$PATH

Start Confluent services: Once Confluent Kafka is installed, you can start the Confluent services (including Kafka and Zookeeper) by running:

Run the following command to start up all of the Confluent components:

confluent local services start
