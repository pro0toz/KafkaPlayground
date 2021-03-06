# The Flash seeker

Two hours ago the speed force barrier exploded and some unknown force affected The Flash. We don't know where this new force comes from, we only know this speed force is called "the negative speed force". Since then The Flash is missing. Every day our we receive messages from people who have seen The Flash, but when Kid Flash tries to catch The Flash we always miss him. Barry is still the fastest man alive.

![negativeFlash](../art/flashNegativeSpeedForce.png)

Thanks our to friends at Star Labs we've created a program that let us know when a Tweet about the Flash has been published. However, we don't know how these tweets are related our friend and where these tweets where published. We need your help to post all these tweets into our Kafka cluster so our machine learning experts can study and find any pattern trying to predict the next The Flash location.

Using just the command line and some Scala code, could you perform the following tasks?

* Start a Kafka cluster using the docker instalation and the Kafka cli client.
* Create two new topics with 6 partitions named ``the-flash-tweets-with-location`` and ``the-flash-tweets``.
* Complete the Kafka producer implementation named ``TheFlashTweetsProducer`` posting a new message into two different topics based on the tweet content. If the tweet contains geo-location info, use the topic named ``the-flash-tweets-with-location``. If the tweet has no geo-location info, use the topic named ``the-flash-tweets``. The second topic messages should contain only the tweet text. The first topic messages should use this JSON format:

```json
{
  "latitude": 12.0,
  "longitude": 11.0,
  "id": "1",
  "message": "I've seen the fastest man alive!"
}
```
* Once you've implemented the Kafka producer, start the program using the main class named ``TheFlashSeeker`` and 4 Kafka console consumers listening at the different topics we've already created. Two consumers for each topic.

