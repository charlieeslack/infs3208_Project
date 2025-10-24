# Queensland Road Traffic and Crash Data Insights 2021-2024

University of Queensland INFS3208 Individual Project - Charles Slack 47473289

## Data Links - Download as CSV files.
**QLD Crash Location Data - (File Name: "1_crash_locations.csv")**
https://www.data.qld.gov.au/dataset/crash-data-from-queensland-roads/resource/e88943c0-5968-4972-a15f-38e120d72ec0


**QLD Road Location and Traffic Data - (File Name: "road-location-and-traffic-data_20250629.csv")**
https://www.data.qld.gov.au/dataset/road-location-and-traffic-data/resource/daab3617-077f-450a-a1c0-57c26d8ba47c

**QLD Road Census Data (File Name: "aadt_2014_2024.csv")**
https://www.data.qld.gov.au/dataset/traffic-census-for-the-queensland-state-declared-road-network/resource/b856deab-ab20-48f1-85c6-2715e3a1d42c?inner_span=True

**QLD Traffic Data Average By Hour By Day:**
**File Name: "qld-traffic-data-average-by-hour-by-day-2021_updated.csv" -** https://www.data.qld.gov.au/dataset/queensland-traffic-data-averaged-by-hour-of-day-and-day-of-week/resource/44fe23b4-8519-4b3f-a24c-6a76b0076c81?inner_span=True

**File Name: "qld-traffic-data-average-by-hour-by-day-2022.csv" -** https://www.data.qld.gov.au/dataset/queensland-traffic-data-averaged-by-hour-of-day-and-day-of-week/resource/4d70bf41-d61e-40c6-86ce-9e61565483a4?inner_span=True

**File Name: "qld-traffic-data-average-by-hour-by-day-2023.csv" -** https://www.data.qld.gov.au/dataset/queensland-traffic-data-averaged-by-hour-of-day-and-day-of-week/resource/d2428b1b-8e3c-4850-828a-f356c5387a0b?inner_span=True

**# Must be downloaded as XLSX and converted to CSV**
**File Name: "qld-traffic-data-average-by-hour-by-day-2024.csv" -** https://www.data.qld.gov.au/dataset/queensland-traffic-data-averaged-by-hour-of-day-and-day-of-week/resource/ef3b4602-696a-4a8b-9934-c1f76e147834


## Setup: 
Enter GCP VM running Ubuntu 22.04 Jammy 75GiB (n2-standard-4)

`Clone Project GitHub Repository` \
git clone https://github.com/charlieeslack/infs3208_Project.git 

***Import data files through SSH-in-browser terminal***

`Moves imported data files to nbs folder for HDFS` \
mv *.csv infs3208_Project/nbs/

`Open project directory` \
cd infs3208_Project

`Runs docker-compose.yml - setting up Spark Cluster, Hadoop DFS, Jupyter Notebook` \
docker compose up -d

`Enter namenode container's bash` \
docker exec -it namenode bash

`Create nbs directory inside HDFS`
hdfs dfs -mkdir -p /nbs/

`Copy data csv files from local system to HDFS`
hdfs dfs -put /home/nbs/*.csv /nbs/
