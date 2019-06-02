# Flink Research

Flink has four levels of abstractions: 

1. SQL - High-Level Language
2. Table API - Declarative DSL
3. DataStream/DataSet API - Core APIs
4. Stateful Stream Processing - Low-level building block (Streams, state, event time)

### Stateful Streaming

The lowest level abstraction simply offers stateful streaming. It is embedded into the DataStream API via the Process Function. It allows users freely process events from one or more streams, and use consistent fault tolerant state. In addition, users can register event time and processing time callbacks, allowing programs to realize sophisticated computations.