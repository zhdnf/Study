# ssh 实现免密

- 生成公私钥 ssh key-gen -t rsa     

- 方法一
    1. scp ~/.ssh/xxx.pub dst_ip 
    2. dst_ip: touch ~/.ssh/authorized.keys
    3. cat xxx.pub >> authorized.keys

- 方法二
    1. ssh-copy-id ~/.ssh/xxx.pub dst_ip

