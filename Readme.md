# WeatherForecast Web API

This is a simple ASP.NET Core Web API project that provides a weather forecast for a given location. The API uses an external weather data service to retrieve the current weather conditions for the location and returns the data in JSON format.

## Getting Started

To get started with the WeatherForecast Web API, you will need to have the following installed on your system:

* .NET 7 SDK

Once you have these installed, you can clone the repository and run the project using the following commands:

```bash
git clone https://github.com/r3adm3/dotnet-helloworld-service.git
cd dotnet-helloworld-service
dotnet run
```

This will start the API on http://localhost:5029

## API Endpoints

The WeatherForecast Web API provides a single endpoint for retrieving weather data for a location:

GET /weatherForecast
Retrieves the weather data for the specified location. The {location} parameter should be a URL-encoded string representing the location.

Example Request

```http
GET /weatherforecast HTTP/1.1
Host: localhost:5029
```

Example Response

```json
{
    {"date":"2023-04-15","temperatureC":0,"temperatureF":32,"summary":"Scorching"},{"date":"2023-04-16","temperatureC":33,"temperatureF":91,"summary":"Scorching"},{"date":"2023-04-17","temperatureC":11,"temperatureF":51,"summary":"Cool"},{"date":"2023-04-18","temperatureC":44,"temperatureF":111,"summary":"Scorching"},{"date":"2023-04-19","temperatureC":-1,"temperatureF":31,"summary":"Scorching"}
}
```

Swagger Definition

```http
GET /swagger/index.html HTTP/1.1
```
## Container Image Build

To build this project as an image ready for containerisation, ensure docker is installed on your development environment and do:

```bash
docker build -t dotnet-helloworld-service:latest .
```

## Running Container 

To run the container in docker (exposed on localhost:9000):

```bash
docker container run -p 9000:80 dotnet-helloworld-service:latest 
```

to run the container in kubenetes (exposed on port 30680):

```bash
kubectl apply -f kube-deploy.yaml 
```

## Dependencies

The WeatherForecast Web API relies on the following external libraries:

* Microsoft.AspNetCore.Mvc
* Newtonsoft.Json
* RestSharp
* License

The WeatherForecast Web API is released under the MIT License.