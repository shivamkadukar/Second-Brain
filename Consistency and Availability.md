## CAP Theorem

[https://robertgreiner.com/cap-theorem-revisited/](https://robertgreiner.com/cap-theorem-revisited/)
[http://ksat.me/a-plain-english-introduction-to-cap-theorem](http://ksat.me/a-plain-english-introduction-to-cap-theorem)

Its states that, when you are designing a distributed system you can get cannot achieve all three of Consistency, Availability and Partition tolerance. You can pick only two.

Given that networks aren't completely reliable, you must tolerate partitions in a distributed system, period.

**CP** - Consistency/Partition Tolerance - Wait for a response from the partitioned node which could result in a timeout error. The system can also choose to return an error, depending on the scenario you desire. Choose Consistency over Availability when your business requirements dictate atomic reads and writes
	[[Consistency Pattern in Distributed Systems]]

**AP** - Availability/Partition Tolerance - Return the most recent version of the data you have, which could be stale. This system state will also accept writes that can be processed later when the partition is resolved. Choose Availability over Consistency when your business requirements allow for some flexibility around when the data in the system synchronizes. Availability is also a compelling option when the system needs to continue to function in spite of external errors (shopping carts, etc.)
	[[Availability Pattern]]
	

