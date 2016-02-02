# momoda
A distributed application performance monitor


NOTE: don't believe the readme  

This system aim to provide montior for applications and machines across datacenters

- collector runs on single (virtual)machine, collect hardware metrics and provide API/Console for 
machine and application status. ~~(It is written in go, for better deploy and low oeverhead)~~
- for storage, it uses KairosDB (use Cassandra) for metrcis and Elasticsearch for log. It provides a proxy 
to query from both backend
- It provides distributed background jobs to run tasks like roll up on KairosDB and Elasticsearch to improve 
query speed
- A alert system that supports webhook, email, sms

## About the name

- LeiHaoMo means How you doing in Chinese
- momoda is e .... momoda