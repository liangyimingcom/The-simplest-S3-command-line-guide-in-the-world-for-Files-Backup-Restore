# 世界上最简单的S3命令行说明(文件备份与恢复) The simplest S3 command line guide in the world for Files Backup/Restore



## 入门教程

### (1) 技术实现 – 文件服务器备份至AWS

![image-20210511104150604](https://raw.githubusercontent.com/liangyimingcom/storage/master/uPic/image-20210511104150604.png)

**一条AWS CLI命令行完成备份**

$ aws s3 sync /backups s3://mybucket

;备份与同步backup目录到AWS云端S3



$ aws s3 sync /backups s3://mybucket --delete

;备份与同步backup目录到AWS云端S3，并删除S3已不存在的文件



$ aws s3 sync /backups s3://mybucket --delete --storage-class STANDARD_IA

;备份与同步backup目录到AWS云端S3，并删除S3已不存在的文件，同时更改备份介质为S3 IA



## (2) 技术实现 – 文件备份从AWS恢复

![image-20210511104253691](https://raw.githubusercontent.com/liangyimingcom/storage/master/uPic/image-20210511104253691.png)

**一条AWS CLI命令行完成还原**

**到本地数据中心或者AWS的EC2上**

$ aws s3 sync s3://mybucket /backups

; 从云端S3恢复与同步到backup目录



$ aws s3 sync s3://mybucket /backups --delete

;从云端S3恢复与同步到backup目录，并删除backup目录中已不存在的文件



## (3) 前提条件

1、https://aws.amazon.com/cn/cli/看这个教程，安装AWS CLI后，运行命令就可以用S3了

2、完整的awscli s3 命令行看这里：https://docs.amazonaws.cn/cli/latest/userguide/cli-services-s3-commands.html

![image-20210511105358852](https://raw.githubusercontent.com/liangyimingcom/storage/master/uPic/image-20210511105358852.png)





## 进阶教程

### BC/DR之备份恢复关键技术堆栈

![image-20210511105454377](https://raw.githubusercontent.com/liangyimingcom/storage/master/uPic/image-20210511105454377.png)

![image-20210511105522657](https://raw.githubusercontent.com/liangyimingcom/storage/master/uPic/image-20210511105522657.png)

![image-20210511105543444](https://raw.githubusercontent.com/liangyimingcom/storage/master/uPic/image-20210511105543444.png)



### 技术实现 – TB/PB级的海量文件备份至AWS

![image-20210511105634443](https://raw.githubusercontent.com/liangyimingcom/storage/master/uPic/image-20210511105634443.png)

### 技术实现 – TB/PB级的海量文件备份从AWS恢复

![image-20210511105606254](https://raw.githubusercontent.com/liangyimingcom/storage/master/uPic/image-20210511105606254.png)



### 在AWS云端可以保留多少个备份副本？

![image-20210511105709858](https://raw.githubusercontent.com/liangyimingcom/storage/master/uPic/image-20210511105709858.png)



### 在AWS云端如何降低存储成本？

![image-20210511105727578](https://raw.githubusercontent.com/liangyimingcom/storage/master/uPic/image-20210511105727578.png)





