# sendfile
PC微信机器人接口api之实战分析发送文件连续call
Q：2645542961
今天主要讲解一下微信发文件call以及连续call我们怎么确定？如何写？怎么找这个call呢，其实这个call就是发送文本的附近的，发文本的call以前已经讲过，在OD里发文本的call下一个断点，
![image](https://user-images.githubusercontent.com/73727649/123534395-847b6680-d74f-11eb-882b-7b883553761c.png)
然后怎么找到那个发文件的call呢，	不管是文件，图片，还是其他的信息，都能在发消息的call前面断下来，然后发现他传了两个参数，一个是消息类型，一个是文件路径，如果把这个类型改变一下，那么他就会以别的消息类型发出去，继续向下走，还有一个就是发送给谁，把这个微信id，改成另外一个人的，然后继续走，发现是发给另外一个人了，说明这个地方就是接收人的call，
![image](https://user-images.githubusercontent.com/73727649/123534401-8b09de00-d74f-11eb-9554-1f44ca924674.png)
找到这些call后，我们把一下不用的参数nop掉，然后走一遍，如果不崩溃的话，就不用写了，如果崩溃说明写代码的时候还需要。找到四个call，一个是文件路径，一个是接收者wxid，一个是组合发送文件数据的缓冲区，一个是发送文件的函数。这个连续call都是一个一个试的，把最终不崩溃有用的留下。
![image](https://user-images.githubusercontent.com/73727649/123534406-9230ec00-d74f-11eb-86ca-acc31d8cc7d0.png)

目前已经实现了很多有趣的功能，运行稳定，比如：发各种消息，
接收各种消息，群管，下载文件，加好友，检测僵尸粉等等功能，
可提供接口，方便各种语言二次开发，欢迎技术交流，Q：2645542961
，请勿用于商业用途。
![image](https://user-images.githubusercontent.com/73727649/123534423-affe5100-d74f-11eb-9d77-f67466ced79d.png)
