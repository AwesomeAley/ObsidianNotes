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
