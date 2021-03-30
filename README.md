# CoronaStats
![dotnet](https://img.shields.io/badge/asp--net--core-3.1-blue)
RESTful webservice that collects and stores data about COVID-19. 

## About

The service uses the [INSERT REF] API to get the latest data about COVID-19. This data is retrieved and stored in a Postgres database and can to be consumed by the service's RESTful interface. It is possible to retrieve this data for any contry. 

However, [INSERT REF] API only provides a few key figures. For Denmark, it is possible to get additional data as the service uses the [INSERT DST] API and scrapes the [INSERT CoronaWebsite] website. 

This service only collects and stores data. By using [REF TO CHARTSERVICE] it is possible to visualize the data in beautiful charts! 

## Getting Started

Either run the project natively or use the provided Dockerfile.

> TODO: 
> - Native + Docker command
> - Configure frequency
> - Confgigure db

## Project TODO
- [ ] Push code to repo
- [ ] Migrate to .NET 5
