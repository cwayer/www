安装到docker上：
```xml
docker run -id --name=rabbitmq  -p 5671:5671 -p 5672:5672  -p 15672:15672 -p 15671:15671  -p 25672:25672  -v /data/rabbitmq-data/:/var/rabbitmq/lib   rabbitmq:3.7.3-management
```

