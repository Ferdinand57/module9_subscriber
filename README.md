### 1. What is amqp?

"In event-driven architecture, we create a system that consists of several independent programs. Those programs communicate by sending data. We call the data an event. The data or event is not directly sent to another, but it is sent to a message broker. We use RabbitMQ as the message broker."

Advanced Message Queuing Protocol (AMQP) is the protocol that is used when publisher and subscriber program want to send data or event to a message broker

### 2. What does it mean? guest:guest@localhost:5672 , what is the first guest, and what is the second guest, and what is localhost:5672 is for? 

the line above is used on the part of the program that use the amqp to establish connection to the message broker

"let listener = CrosstownBus::new_queue_listener("amqp://guest:guest@localhost:5672".to_owned()).unwrap();"

the line above connect our program to our message broker, with the first guest as the username, the second guest as the password for the username "guest", localhost is where the message broker is running (in this case, is on local enviorement/our pc), and 5672 is the port that our message broker listen to for an amqp connection