# Lock-Free Circular Queue

Lock-Free Circular Queue is a queue including lock-free mechanism for enqueuing and dequeuing operations.
It is used on consumer-producer scenarios, which need no locking rules, therefore no latency occurs.

# Implementation Details

The project is implemented with using help of atomic concept of C++ programming language. In case of
enqueuing and dequeuing occuring at same time, resource, namely the queue may likely cause race condition.
Meanwhile, enqueuing and dequeuing are competitors each others, they must be synchronized. However, the
latency mostly occurs when using a locking mechanism, because dequeuing and enqueuing have to wait each
others. The atomic concept solves concurrent access without any latency, but for the sake of performance,
data-lost may occur.

The head, tail and size fields of lock-free circular buffer are atomic variables.
