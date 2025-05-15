### 1. What is amqp?

"In event-driven architecture, we create a system that consists of several independent programs. Those programs communicate by sending data. We call the data an event. The data or event is not directly sent to another, but it is sent to a message broker. We use RabbitMQ as the message broker."

Advanced Message Queuing Protocol (AMQP) is the protocol that is used when publisher and subscriber program want to send data or event to a message broker

### 2. What does it mean? guest:guest@localhost:5672 , what is the first guest, and what is the second guest, and what is localhost:5672 is for? 

the line above is used on the part of the program that use the amqp to establish connection to the message broker

"let listener = CrosstownBus::new_queue_listener("amqp://guest:guest@localhost:5672".to_owned()).unwrap();"

the line above connect our program to our message broker, with the first guest as the username, the second guest as the password for the username "guest", localhost is where the message broker is running (in this case, is on local enviorement/our pc), and 5672 is the port that our message broker listen to for an amqp connection

### slowSubscriber

![](slowSubscriber.png)

why the total number of queue is 26?

I ran the slowed-down subscriber program, and then i ran the publisher program 6 times, because each have 5 message sent to the message broker, the message broker recieved a total of 30 message which is being processed one by one by the subscriber, but because the subscriber is slowed-down, by the time the RabbitMQ message broker updates, the subscriber could only process 4 message which leave behind the other 26 message in queue which is represented by the chart.