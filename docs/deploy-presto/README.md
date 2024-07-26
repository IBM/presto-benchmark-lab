# Deploying Presto with Docker Compose

## Prerequisites

- Git
- Docker
- Docker Compose

## 1. Set Up

### 1.1 Pull images

Pull the Presto images first to allow time for downloading.

```bash
docker pull prestodb/presto:latest
docker pull public.ecr.aws/oss-presto/presto-native:0.289-ubuntu-arm64
```

### 2.1 Clone repo

Clone the prestodb/prestorials repository which contains the Docker Compose files used for deploying Presto.

```bash
git clone https://github.com/prestodb/prestorials.git
```

Then change directory into the cloned repository.

```bash
cd prestorials
```

## 2. Set Up Data

### 2.1 Download data

Download the data.tar file [here]().

This file contains the TPC-DS and TPCH tables needed to set up a local Hive metastore.

### 2.2 Prepare data

After downloading, we need to move the data to the directories needed for Presto to detect them.

Copy the data.tar file to the following directories (within `prestorials`) and extract:

```
docker-compose
docker-compose-native/prestissimo
```

After extracting, you should see the data directories created:

```
docker-compose/data
docker-compose-native/prestissimo/data
```

The `tpcds` and `tpch` directories should also be created in the `/data` directories.
The `data.tar` file can then be deleted as it is no longer needed.

## 3. Deploying Presto

Now that setup is complete, we can run the docker compose file and use Presto CLI to run queries.

### 3.1 Deploying Presto C++

Change into the `docker-compose-native` directory in `prestorials` and run the `docker compose`
command to start the Presto C++ cluster. We specify the Docker Compose file with `-f docker-compose-arm64.yml`.

```bash
cd docker-compose-native
docker compose -v -f docker-compose-arm64.yml up
```

You should now see the logs of the Presto coordinator and worker starting up. The cluster is ready once
you see something similar to the following log messages:

```
coordinator  | 2024-07-25T23:48:15.077Z	INFO	main	com.facebook.presto.server.PrestoServer	======== SERVER STARTED ========
worker_2     | I0725 23:48:39.584002     8 PeriodicServiceInventoryManager.cpp:118] Announcement succeeded: HTTP 202. State: active.
worker_1     | I0725 23:48:41.484305     8 PeriodicServiceInventoryManager.cpp:118] Announcement succeeded: HTTP 202. State: active.
```

### 3.2 Deploying Presto Java

If you just finished Step 3.1 and have a Presto C++ cluster running, skip to the next steps on using Presto CLI and running pbench.
Return to this step after running pbench and obtaining TPC-DS benchmark times for Presto C++.

Deploying Presto Java is very similar to Presto C++. We just use the Docker Compose file in the `docker-compose` directory of
`prestorials`.

```bash
cd docker-compose
docker compose -v -f docker-compose-arm64.yaml up
```

## 4 Using Presto CLI

After deploying a Presto cluster and confirming that the server started, run the Presto CLI from the coordinator container:
```bash
docker exec -it coordinator /opt/presto-cli
```
While in Presto CLI, verify that the schemas exist and use hive.tpcds for example:
```mysql
SHOW schemas in hive;
USE hive.tpcds;
SHOW tables;
```