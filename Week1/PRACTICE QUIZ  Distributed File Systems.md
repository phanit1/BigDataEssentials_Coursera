Distributed File Systems
1. 
Question 1
What fact is more relevant to the horizontal scaling of the filesystems than to the vertical scaling?

Usage of commodity hardware

Correct
Yes, it's possible to use simple and commodity hardware

2. 
Question 2
The operation 'modify' files is not allowed in distributed FS (GFS, HDFS).  What was NOT a reason to do it?

Increasing reliability and accessibility

Correct
Yes, it was not a reason, because reliability and accessibility are mostly achieved by the replication

3. 
Question 3
How to achieve uniform data distribution across the servers in DFS?

By splitting files into blocks

Correct
Yes, splitting large files into blocks increases data items granularity and allows to fill the servers more evenly

4. 
Question 4
What does a metadata DB contain?

Location on the file blocks

Correct
Yes, locations of the blocks are administrative information about a file, they are stored in the metadata DB


File creation time

Correct
Yes, file creation time is administrative information about a file, it is stored in the metadata DB


File permissions

Correct
Yes, permissions are administrative information about a file, they are stored in the metadata DB

5. 
Question 5
Select the correct statement about HDFS:

A client requires access to all the servers to read files

Correct
Yes, a client reads directly from the server with the required block

6. 
Question 6
If you have a very important file, what is the best way to protect it in HDFS?

Both ways are allowed and implemented in HDFS

Correct
Yes, a replication is used for better reliability and you should also remember about the appropriate access to your data. 

7. 
Question 7
You were told that two servers in HDFS were down: Datanode and Namenode, your reaction:

Restore Namenode first

Correct
Namenode is a master server, so it should be restored first

8. 
Question 8
What the block size in HDFS does NOT depend on?

The block size on the local Datanodes filesystem

Correct
Yes, HDFS block size mostly depends on Namenode RAM amount and Datanode disks performance