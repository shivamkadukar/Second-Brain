
[https://cs.fyi/guide/consistency-patterns-week-strong-eventual](https://cs.fyi/guide/consistency-patterns-week-strong-eventual)

A distributed system is a system whose components are located on different networked computers, which communicate and coordinate their actions by passing messages to one another. The components interact with one another in order to achieve a common goal.

### Consistency Patterns
Consistency patterns refer to the ways in which data is stored and managed in a distributed system and how that data is made available to users and applications

- Strong Consistency
	After an update is made to the data, it will be immediately visible to any subsequent read operations. The data is replicated in a synchronous manner, ensuring that all copies of the data are updated at the same time.
	
	In a strong consistency system, any updates to some data are immediately propagated to all locations. This ensures that all locations have the same version of the data, but it also means that the system is _not highly available and has high latency_.

- Weak Consistency
	After an update is made to the data, it is not guaranteed that any subsequent read operation will immediately reflect the changes made. The read **may or may not** see the recent write.
	
	In a weakly consistent system, updates to the data may not be immediately propagated. This can lead to inconsistencies and conflicts between different versions of the data, but it also allows for **high availability and low latency**.

- Eventual Consistency
	Eventual consistency is a form of Weak Consistency. After an update is made to the data, it will be eventually visible to any subsequent read operations. The data is replicated in an asynchronous manner, ensuring that all copies of the data are eventually updated.
	
	In an eventually consistent system, data is typically stored in multiple locations, and updates to that data are eventually propagated to all locations. This means that the system is highly available and has low latency, but it also means that there may be inconsistencies and conflicts between different versions of the data.