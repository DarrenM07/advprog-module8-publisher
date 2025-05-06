## How much data your publisher program will send to the message broker in one run?

*Answer:* The publisher program sends only one message to the message broker in a single run. This message typically includes an event name like "user_created" and a payload containing details such as a user_id and a user_name. Assuming the message is serialized using a common format like JSON or Borsh, the total size of the data sent would be relatively small—approximately 40 to 60 bytes. This estimate includes the string values as well as serialization overhead. Therefore, in one execution, the publisher sends a lightweight message suitable for efficient communication with the message broker.


## The url of: `mqp://guest:guest@localhost:5672` is the same as in the subscriber program, what does it mean?

*Answer:* The URL `amqp://guest:guest@localhost:5672` used in both the publisher and subscriber programs indicates that they are connecting to the same RabbitMQ message broker. This URL specifies the AMQP protocol, uses the default guest user credentials, and connects to a server running locally on port 5672, which is RabbitMQ's default port for AMQP. By sharing the same connection settings, both programs interact with the same broker instance—enabling the publisher to send messages and the subscriber to receive them in real time. This shared configuration is essential for enabling proper communication between services in a message-driven architecture.

## Running RabbitMQ as message broker.
<img src="img/ss1.png">

## Sending and processing event.
<img src="img/ss2.png">

## Monitoring chart based on publisher.
<img src="img/ss3.png">