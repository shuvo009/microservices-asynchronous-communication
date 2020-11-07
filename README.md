# Microservices asynchronous communication
Exchange data between client application to microservices using service bus via api gateway,  

## Scenario 
Microservices are comminicating with ApiGateway over message bus but client application comminicating over Http or Socket with ApiGateway. Here I demonstrated how client application exchange data from microservices using Http or Socket over ApiGateway.

![diagram](https://github.com/shuvo009/microservices-asynchronous-communication/blob/main/diagram%20.png)

## Technologies
* Asp.net Core 3.1 (ApiGateway)
* .NET Core Web Job (Microservice)
* Angular 10 (Client Application)
* SignalR (Web Socket. Client to ApiGateway communication) 
* HTTP (GET, POST. Client to ApiGateway communication)

## Azure Services
* Service Bus (STANDARD)
* App Service

## Common setup
Step 1: Clone the repo
```
git clone https://github.com/shuvo009/microservices-asynchronous-communication.git

```
Step 2: Set you Azure Service bus connection string at 
```
ApiGateway/appsettings.json
MicroserviceOne/appsettings.json
MicroserviceTwo/appsettings.json
```
Step 3: Please make sure following Queues are exist at Azure service bus
```
FileBrowser
ReadCsvFile
```
Step 4: Go to AngularClient
```
npm install
```
Step 5: Rull all together

## How it works

### ApiGateway to Miceroservice
Step 1: Request receive from client

Step 2: Create a temporary queue at azure service bus.

Step 3: Set temporary queue at ReplyTo of Message.

Step 4: Send this message to a predefine queue.

Step 5: Start listening at temporary queue.

