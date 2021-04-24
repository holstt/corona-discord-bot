# Corona Stats
![dotnet](https://img.shields.io/badge/asp--net--core-3.1-blue)
![csharp](https://img.shields.io/badge/C%23-8-blue)
![ide](https://img.shields.io/badge/IDE-vs2019-blue)

RESTful webservice that collects and stores data about COVID-19. 

## About

The service uses the [disease.sh API](https://corona.lmao.ninja/) to get the latest data about COVID-19. This data is retrieved and stored in a Postgres database and can to be consumed by the service's RESTful interface. It is possible to retrieve this data for any country.

However, the disease.sh API only provides a few key figures. For Denmark, it is possible to get additional data as the service uses the [Statistics Denmark Databank API](https://www.dst.dk/en/Statistik/brug-statistikken/muligheder-i-statistikbanken/api) and scrapes the [SST](https://www.sst.dk/da/corona/Status-for-epidemien/tal-og-overvaagning) website. 

This service only collects, scrapes and stores data. By using the [chart-service](https://github.com/roedebaron/chart-service), it is possible to visualize the data in beautiful charts! 

> TODO: 
> - Describe architecture 

## Getting Started

Either run the project natively or use the provided Dockerfile to run it in Docker.

Clone the project: 
1. `git clone https://github.com/roedebaron/corona-stats.git`
2. `cd aau-schedule-scraping/CoronaStats.Api`

#### Native
3. Run `dotnet run`. This will automatically download all dependencies, build the project and then run the service. 
4. If no other port has been specified in the configuration, the service is now running on port 5000. 

#### Using Docker 🐳
3. Run `docker build -t corona-stats .` to build the image with name `corona-stats`
4. Run `docker run -dp 5000:5000 corona-stats` to start a container from the image. This will map your local port (e.g. 5000) to the port that the service is listening on (default is 5000). 


> TODO: 
> - Configure frequency
> - Confgigure db
> - Docker Compose with chart service 
> - Discord bot integration?

## Project TODO
- [ ] Push code to repo
- [ ] Migrate to .NET 5
