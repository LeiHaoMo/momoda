# Design

## Data Storage

The system relies on external database system to provides distributed and reliable data storage

- metrcis are stored in Cassendra using KairosDB　(may switch to ScyllaDB)
- log are stored and indexed in Elasticsearch, also, Elasticsearch provides search for name and tags in KairosDB

## Collector

To avoid direct connection with data storage from machine or application. The collector collect all the data in its machine
and make sure they are sent to the data storage, it is able to do some simple aggregate and compress to reduce network traffic,
also it took cares of network failure.

- collect machine hardware information
- montior process using pid or using process description ( see sigar documentation )
- web interface to know local and remote status.

## Job

In order to improve query speed and remove useless data, it provides a job system to operate against data storage.

- user can specify rules for how to pre-aggregate data and how to deal with old data
- pre-aggregate metrics
- run prediction

## Alert

The alert is based on threshold and prediction, provides webhook. 

- prediction for hardware metrics is provided using plugin system to support custom algorithm 

## Web App

- Front end is a SPA (Single page application) using RESTful API
- Backend use Spring
- Custom graphs
- Metrcis and Log can be showed in one screen to provide better insight