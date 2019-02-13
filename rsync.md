# rsync：实现两端主机的文件同步

## rsync实现的3种方式

1. 本地方式

` Local:  rsync [OPTION...] SRC... [DEST] `
 
2. 远程shell
``` 
    Access via remote shell:
	Pull: rsync [OPTION...] [USER@]HOST:SRC... [DEST]
	Push: rsync [OPTION...] SRC... [USER@]HOST:DEST 
```
  
3. socket（远程rsync服务）	
``` 
    Access via rsync daemon:
	Pull: rsync [OPTION...] [USER@]HOST::SRC... [DEST]
	      rsync [OPTION...] rsync://[USER@]HOST[:PORT]/SRC... [DEST]
	Push: rsync [OPTION...] SRC... [USER@]HOST::DEST
              rsync [OPTION...] SRC... rsync://[USER@]HOST[:PORT]/DEST 
```
		

## rsync 简单实例
- rsync /etc/fstab /tmp                # 在本地同步
- rsync -r /etc 172.16.10.5:/tmp       # 将本地/etc目录拷贝到远程主机的/tmp下，以保证远程/tmp目录和本地/etc保持同步
- rsync -r 172.16.10.5:/etc /tmp       # 将远程主机的/etc目录拷贝到本地/tmp下，以保证本地/tmp目录和远程/etc保持同步
- rsync /etc/                          # 列出本地/etc/目录下的文件列表
- rsync 172.16.10.5:/tmp/              # 列出远程主机上/tmp/目录下的文件列表

## 详细介绍 
- https://www.cnblogs.com/f-ck-need-u/p/7220009.html
