<details>
<summary>Module 8</summary>

1. How many data your publlsher program will send to the message broker in one run?

My publisher program will send 5 messages to the message broker in one run. Each publish_event call sends one message, and there are 5 such calls in your main function.

Because the code have 5  calls in this

= p.publish_event("user_created".to_owned(), UserCreatedEventMessage { user_id: "1".to_owned(), user_name: "2206083470-Amir".to_owned() });
    _ = p.publish_event("user_created".to_owned(), UserCreatedEventMessage { user_id: "2".to_owned(), user_name: "2206083470-Budi".to_owned() });
    _ = p.publish_event("user_created".to_owned(), UserCreatedEventMessage { user_id: "3".to_owned(), user_name: "2206083470-Cica".to_owned() });
    _ = p.publish_event("user_created".to_owned(), UserCreatedEventMessage { user_id: "4".to_owned(), user_name: "2206083470-Dira".to_owned() });
    _ = p.publish_event("user_created".to_owned(), UserCreatedEventMessage { user_id: "5".to_owned(), user_name: "2206083470-Emir".to_owned() });

2. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?

The URL "amqp://guest:guest@localhost:5672" is the address of the message broker. Both the publisher and subscriber programs use this URL to connect to the same message broker. The publisher sends messages to the broker, and the broker then distributes these messages to the subscribers. The fact that they are using the same URL means they are communicating through the same message broker.


Commit 3 :
![docker1](image.png)

Commit 4 :
When cargo run is executed twice in the publisher, then the subscriber will catch it and output the messages
![alt text](image-1.png)

Publisher:
![alt text](image-2.png)

Commit 5:
When cargo run is executed several times in the publisher, there will be an increase in message rates. After a while, there will be a spike increase in publish
![alt text](image-3.png)


</details>