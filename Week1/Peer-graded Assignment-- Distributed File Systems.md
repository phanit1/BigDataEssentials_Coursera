**Estimate minimum Namenode RAM size for HDFS with 1 PB capacity, block size 64 MB, average metadata size for each block is 300 B, replication factor is 3. Provide the formula for calculations and the result.**

    1PB/(64MB*3) * 300B = 10^15 / (64*10^6*3)*300B = 10^9/(64*3)*300B = 1 562 500 000B = 1.6GB

**HDDs in your cluster have the following characteristics: average reading speed is 60 MB/s, seek time is 5 ms. You want to spend 0.5 % time for seeking the block, i.e. seek time should be 200 times less than the time to read the block. Estimate the minimum block size.**

    tread/tseek = 200

    tread = 200 * tseek

    tseek = 5ms = 0.005s

    vread = 60MB/s

    tread = size/vread

    size = vread * tread = vread * 200 * tseek = 60MB/s * 200 * 0.005s = 60MB

**To complete this task use the 'HDFS CLI Playground' item.

Create text file ‘test.txt’ in a local fs. Use HDFS CLI to make the following operations:

    * сreate directory ‘assignment1’ in your home directory in HDFS (you can use a      relative path or prescribe it explicitly "/user/  jovyan/...")
    * put test.txt in it
    * output the size and the owner of the file
    * revoke ‘read’ permission for ‘other users’
    * read the first 10 lines of the file
    * rename it to ‘test2.txt’.

Provide all the commands to HDFS CLI.**


    $ hdfs dfs -mkdir assignment1

    $ hdfs dfs -put test.txt assignment1/

    $ hdfs dfs -ls assignment1/test.txt or hdfs dfs -stat "%b %u" assignment1/test.txt

    $ hdfs dfs -chmod o-r assignment1/test.txt

    $ hdfs dfs -cat assignment1/test.txt | head -10

    $ hdfs dfs -mv assignment1/test.txt assignment1/test2.txt

**To complete this task use the 'HDFS CLI Playground' item.Use HDFS CLI to investigate the file ‘/data/wiki/en_articles_part/articles-part’ in HDFS:

    * get blocks and their locations in HDFS for this file, show the command without an output
    * get the information about any block of the file, show the command and the block locations from the output
**

    hdfs fsck /data/wiki/en_articles_part/articles-part -files -blocks -locations

    hdfs fsck /data/wiki/en_articles_part/articles-part -blockid(blk_1045267296)

**Show the total capacity of this HDFS installation, used space and total data nodes in the cluster.**

    Total capacity: 2.14 TB

    Used space: 242.12 GB (=DFS Used) or 242.12+35.51 = 277.63 GB (=DFS Used + Non DFS Used) - the latter answer is more precise, but the former is also possible

    Data nodes in the cluster: 4