# Ramdisk_mq

This project's aim is evaluate multi queue block layer(blk-mq)'s scalability. <br/>
Ramdisk_MQ is Ram based block device which can make faster for latency than non volatile device for processing intense IO from CPU using blk-mq to parallel process for CPU scalability. 

Ramdisk is already exist but can not use for evaluate blk-mq's scalablilty. Because this is implemented under single queue block layer.
For evaluate blk-mq's scalability, need to implement new Ram based block device using blk-mq. 
As a result, We are implementing Ramdisk_MQ.

We eliminate critical bugs and porting the kernel version from 4.4 to 5.0 on mybrd code which merged ramdisk and block layer mutli queue referenced by null_blk, brd and blk-mq.

reference : https://github.com/gurugio/mybrd/

# Usage

command :
sudo modprobe ramdisk_mq bs=x queue_mode=x size=x <br/>
bs : Block size(Kb)<br/>
queue mode : 0-bio, 1-single queue, 2-multi queue<br/>
size : Module size(Mb)<br/>
