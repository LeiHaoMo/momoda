# Documentation

- [system design](design.md)

## Framework

- use spring boot, see https://spring.io/
- https://www.consul.io/ for service discovery and config
- use Akka for TCP server

## Modules

- dbproxy, serve as a proxy for query and insert into KairosDB. due to some features are not implemented in KairosDB
and we may switch to other time series database
- collector, collect hardware metrics using sigar, work as a TCP server to receive probe information
- web, provide RESTful API and front end for management and graphs