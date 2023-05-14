# AMQP Workout

A Docker implementation of the first 3 RabbitMQ tutorials.  

[https://www.rabbitmq.com/getstarted.html](https://www.rabbitmq.com/getstarted.html)

## Common instructions

Change to tutorial directory, then
```
docker compose up --remove-orphans
```

## Management console
[http://localhost:15672](http://localhost:15672)  
un: `guest`  
pw: `guest`


## 1. Hello World

### terminal 1
```
docker compose exec producer bash
cd Send
dotnet run
```

### terminal 2
```
docker compose exec consumer bash
cd Receive
dotnet run
```

## 2. Work Queues

### terminal 1
```
docker compose exec producer bash
cd NewTask
dotnet run
dotnet run "message"
dotnet run "message.."
dotnet run "message...."
dotnet run "message........"
```

### terminal 2
```
docker compose exec consumer-a bash
cd Worker
dotnet run
```

### terminal 3
```
docker compose exec consumer-b bash
cd Worker
dotnet run
```

## 3. Publish/Subscribe

### terminal 1
```
docker compose exec producer bash
cd EmitLog
dotnet run
```

### terminal 2
```
docker compose exec consumer-a bash
cd ReceiveLogs
dotnet run
```

### terminal 3
```
docker compose exec consumer-b bash
cd ReceiveLogs
dotnet run
```
