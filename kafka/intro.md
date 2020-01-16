#  Introduction
A streaming platform has three key capabilities:

* Publish and subscribe to streams of records, similar to a message queue or enterprise messaging system.
* Store streams of records in a fault-tolerant durable way.
* Process streams of records as they occur.

## Concepts
* The Kafka cluster stores streams of records in categories called topics.
* Each record consists of a key, a value, and a timestamp.

Kafka has four core APIs:

* Producer:
* Consumer:
* Streams:
* Connector: 

A partition can only be worked on by one consumer in a consumer group at a time. Consumers can run in their own process or their own thread. If a consumer stops, Kafka spreads partitions across the remaining consumer in the same consumer group.
The record is considered “committed” when all ISRs for partition wrote to their log. Only committed records are readable from consumer. A

## Consumer
Consumers label themselves with a consumer group name

Kafka handles this differently. Our topic is divided into a set of totally ordered partitions, each of which is consumed by exactly one consumer within each subscribing consumer group at any given time. This means that the position of a consumer in each partition is just a single integer, the offset of the next message to consume. This makes the state about what has been consumed very small, just one number for each partition. This state can be periodically checkpointed. This makes the equivalent of message acknowledgements very cheap.

## Connect
Kafka Connect is a tool for scalably and reliably streaming data between Apache Kafka and other systems.

Kafka sinks: A sink connector delivers data from Kafka topics into other systems, 

Kafka sources: A source connector collects data from a system. 

### Core Conecpt
#### Connectors and Tasks
To copy data between Kafka and another system, users create a Connector for the system they want to pull data from or push data to. SourceConnectors and SinkConnectors.

Connectors do not perform any data copying themselves: their configuration describes the data to be copied, and the Connector is responsible for breaking that job into a set of Tasks that can be distributed to workers. SourceTask and SinkTask.

## Stream
### Stream Processing Topology
A stream processing application is any program that makes use of the Kafka Streams library. It defines its computational logic through one or more processor topologies, where a processor topology is a graph of stream processors (nodes) that are connected by streams (edges).

A stream processor is a node in the processor topology

A processor topology is merely a logical abstraction for your stream processing code. At runtime, the logical topology is instantiated and replicated inside the application for parallel processing (see Stream Partitions and Tasks for details).

### Stream partitions and tasks
Kafka Streams uses the concepts of *partitions* and *tasks* as logical units of its parallelism model based on Kafka topic partitions. There are close links between Kafka Streams and Kafka in the context of parallelism:

* Each stream partition is a totally ordered sequence of data records and maps to a Kafka topic partition.
* A data record in the stream maps to a Kafka message from that topic.
* The keys of data records determine the partitioning of data in both Kafka and Kafka Streams, i.e., how data is routed to specific partitions within topics.