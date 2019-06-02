# Streaming Reactive Systems & Data Pipes w. Squbs

https://www.infoq.com/presentations/squbs

Streams can be used for any process

### Linear stages: Source, Flow, Sink

Source is where the info sources in from. The source could be connected to a message bus that is connected to kafka or anything else (even HTTP).

In the middle we have flow stages that could do maps which are transformations or filters.

The sink is where the data flows to that can write to kafka or http or terminating or doing a reduction.

### Non-Linear Stages: Fan-In & Fan-Out

We use Fan-In/Fan-Out allow you to create more complex, non-linear stream paths. You can even have loop-backs in your streams.

### BidiFlow

The BidiFlow can be used as a protocol handler or a gating component that allows two streams to go in different ways.

### Materializer

Having our Source, Flow, and Sink is great but that is still just a stream that doesn't run. The Materializer creates a network of running entities. A stream is just a template, but it isn't until we materialize it that it becomes a stream that connects all the nodes together. The result of the stream will be *Materialized Values* which could be the value you get like a word count for example. 

### Back-Pressure

When you have stream components and they each have a buffer they will blow up. You will use up memory. We want the downstream to signal back saying it can handle more or it cannot handle more. Those are the attributes of back-pressure. 

***

Stream declarations are immutable templates that can be produced from a function, can be materialized multiple times, and the parts are immutable and composable. 

You may setup a pipeline that takes data from the internet and then sends it to Kafka. However, Kafka might not always be ready to receive that data and we cannot back-pressure the internet with all of its data. So we can create a buffer to manage the data while it waits fro kafka.
