使用foxglove自瞄可视化辅助调试

此方案适用于视觉板性能不够的情况，通过ssh连接，实现远程辅助调试

**第一步**

下载ssh

```
sudo apt install openssh-server
```

```
sudo apt install openssh-client
```

**第二步**

在/home/.ssh中找到known_hosts

![image](https://github.com/user-attachments/assets/4f78fdba-dc54-4a25-a0b1-03233e64797c)

**第三步**

在/home目录创建一个这样的.sh脚本文件

![image](https://github.com/user-attachments/assets/08bd7255-8d11-4ea0-b2cb-ac83f92c7030)

**第四步**

对于ma战队的同学，直接进入该文件复制以下内容，并保存

```
ssh-keygen -f "/home/aubrey/.ssh/known_hosts" -R "192.168.2.1"
ssh -L 8765:192.168.2.1:8765 ma@192.168.2.1
```

注意这里/home/aubrey/.ssh/known_hosts替换为第二步中复制的路径

![image](https://github.com/user-attachments/assets/138ad783-bfd0-4014-879f-91b46267b7b8)

**第五步**

对该脚本文件赋权

```
chmod +x connect_fox.sh
```

![image](https://github.com/user-attachments/assets/410db31d-2f6d-4b06-86f3-6fe627c53cc9)


**第六步**

在视觉板跑自瞄代码以及foxglove

![image](https://github.com/user-attachments/assets/7f7ed0e7-8afe-416e-b252-f84739ce6ffd)

![image](https://github.com/user-attachments/assets/4c4790b9-da6c-43c7-b4f7-8170d415311c)

**第七步**

运行脚本文件,然后直接yes，然后输入视觉板密码

![image](https://github.com/user-attachments/assets/da33d906-6b03-4a17-a2b9-1ebd0b5443d6)

如下图显示则连接成功

![image](https://github.com/user-attachments/assets/7d8a8089-2549-47b9-93ac-bc0e509e03f2)

**第八步**

进入自己电脑的foxglove软件，点Open connection,然后直接open就连上了

![image](https://github.com/user-attachments/assets/545cafdf-9b01-4f5e-8168-1312f46d5ca7)
![image](https://github.com/user-attachments/assets/e5b2f1a3-7d44-452e-8ffb-35f605050037)









