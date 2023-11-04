- Seek time- Time it takes for read/write head to be over right track
- Head switch time- Time required to electrically switch from one head to another
- Latency- Time it takes for sector to be in position. Depends on the rotational speed of the disk
- Access time- Seek time + Head switch time + Latency

## Example Problem

Suppose I have a 250 GB hard disk that spins at 7200 rpm.  It has 1024 cylinders and 4platters. The worst case seek time is 0.1 second. If the head is currently sitting on platter 1, track 1, sector 1, how long will it take to move to platter 1, track 512, sector60000?

**Solution - Seek Time**
Reminder: seek time is the time it takes for read/write head to beover right track
  
Problem: 250 GB hard disk that spins at 7200 rpm.• It has 1024 cylinders and worst case seek time is 0.1 second.• Head is currently sitting on platter 1, track 1 and need to move to platter 1, track 512• Seek time: 0.1 seconds / 2 = 0.05

**Solution - Latency**

We must get to sector 60000
• How many sectors are there on the disk?
	• 250 GB and 4 platters
	• 250 GB = 268,435,456,000 bytes
	• 268,435,456,000/ 512 bytes-per-sector= 524,288,000 sectors
	• 524,288,000 / 4 platters = 131,072,000 sectors / platter.
• How many sectors per track?
	• 1024 cylinders = 1024 tracks per platter
	• 131,072,000/1024 = 128,000 sectors per track

How many revolutions to get to sector 60,000
	• 60,000/128,000 = 0.46875 revolutions.
• How long does that take?
	• A 7200-rpm disk makes 7200/60 = 120 revolutions per second
	• 0.46875 / 120 = 0.00390625 seconds of rotational latency


**Solution - Total Access Time
  
Total Access Time = Seek Time + Head Switch Time + Latency• 0.05390625 seconds
	• seek time: 0.05 seconds
	• head switch time: 0 seconds
	• latency: 0.00390625 seconds