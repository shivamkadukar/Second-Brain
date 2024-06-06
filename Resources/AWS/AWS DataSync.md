
- Move large amount of data to and from 
- On-premises / other cloud to AWS (NFS, SMB, HDFS, S3 API…) – needs agent 
- AWS to AWS (different storage services) – no agent needed 
- Can synchronize to: 
	- Amazon S3 (any storage classes – including Glacier) 
	- Amazon EFS 
	- Amazon FSx (Windows, Lustre, NetApp, OpenZFS...) 
- Replication tasks can be scheduled hourly, daily, weekly 
- __File permissions and metadata are preserved__ (NFS POSIX, SMB…) 
- One agent task can use 10 Gbps, can setup a bandwidth limit

__On premise to AWS DataSync__

![[aws datasync with agent.png]]

__DataSync Between AWS Services__

![[datasync between services.png]]