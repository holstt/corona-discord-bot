# Discord Corona Bot
![dotnet](https://img.shields.io/badge/asp--net--core-3.1-blue)
![nodejs](https://img.shields.io/badge/node--js-10-green)

Discord bot that generates and shows the latest corona charts for every country.

## About

The Discord bot is developed as a microservice architecture: 

### Microservice: corona-data-service

RESTful webservice that collects and stores data about COVID-19. 

The service uses the [disease.sh API](https://corona.lmao.ninja/) to get the latest data about COVID-19. This data is retrieved and stored in a Postgres database and can to be consumed by the service's RESTful interface. It is possible to retrieve this data for any country.

However, the disease.sh API only provides a few key figures. For Denmark, it is possible to get additional data as the service uses the [Statistics Denmark Databank API](https://www.dst.dk/en/Statistik/brug-statistikken/muligheder-i-statistikbanken/api) and scrapes the [SST](https://www.sst.dk/da/corona/Status-for-epidemien/tal-og-overvaagning) website. 

This service only collects, scrapes and stores data. 

### Microservice: chart-service

Node.js service using the popular chart.js library to construct and render charts server side. Gets data from **corona-data-service**. 

### Microservice: discord-bot

Responsible for recieving discord commands, forward the request to **chart-service** and finally returning the result to the client (discord guild).  

> TODO: 
> - Describe architecture 

## Getting Started

Running the bot requires a Discord Bot Token. It is recommended to obtain a two tokens (development and production). 

### Configuration

Place the tokens in `appsettings.Production.json` and `appsettings.Development.json` respectively. Alternatively set the token as an environment variable. 

Logging is performed through Serilog and can be configured in `appsettings.json`. However, you can leave this configuration as is.

### Running the bot

The easiest way to run the bot is using Docker Compose. A `docker-compose.yml` is provided together with a `Dockerfile` for all three services.

Clone the project: 
1. `git clone https://github.com/roedebaron/discord-corona-bot.git`
2. `cd discord-corona-bot

#### Running with Docker Compose 🐳
3. Run `docker-compose up .` to build and run all services


> TODO: 
> - Configure frequency in corona-stats-service
> - Confgigure db credentials
> - Running from source

## Usage

> TODO: 
> - Images of command + charts


## Project TODO
- [ ] Push code to repo
- [ ] Migrate to .NET 5
- [ ] Consider using another Node version of chart.js. Currently it does not run on Windows. 
