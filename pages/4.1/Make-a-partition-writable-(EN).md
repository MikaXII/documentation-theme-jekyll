---
layout: page
title: Make a partition writable (EN)
wikiPageName: Make-a-partition-writable-(EN)
menu: wiki
---

Since version 4.0.0, the system partition was modified to limit corruption of your microSD.
Therefore, the following partitions are accessible only in reading:    


You may need to modify files in 2 partitions recalboxOS 
 boot partition  `/boot`    
system partition `/  `  

`mount -o remount,rw /boot`   
ou   
`mount -o remount,rw /`   

Partition will be given read-only on the next system restart.   


###Winscp in console

Clicksur Console icon then enter the command to write the partition.   
<a href="http://www.zimagez.com/zimage/winscp01.php" target="_blank" title="Visionner l'image"><img src="http://www.zimagez.com/miniature/winscp01.png" alt="Visionner l'image" /></a>   
   

