[Performance vs Scalability](https://blog.professorbeekums.com/performance-vs-scalability/)
[A word on scalability](https://www.allthingsdistributed.com/2006/03/a_word_on_scalability.html)

_A service is said to be scalable if when we increase the resources in a system, it results in increased performance in a manner proportional to resources added._
Increasing performance in general means serving more units of work, but it can also be to handle larger units of work, such as when datasets grow.

_An always-on service is said to be scalable if adding resources to facilitate redundancy does not result in a loss of performance_.

applications and platforms to be designed with scaling in mind, such that adding resources actually results in improving the performance or that if redundancy is introduced the system performance is not adversely affected.

growing a system through scale-out generally results in a system that has to come to terms with heterogeneity. Heterogeneity means that some nodes will be able to process faster or store more data than other nodes in a system and algorithms that rely on uniformity either break down under these conditions or underutilize the newer resources.

 For the systems we build we must carefully inspect along which axis we expect the system to grow, where redundancy is required, and how one should handle heterogeneity in this system,